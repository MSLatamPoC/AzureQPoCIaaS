# Azure Quick PoC (QPoC)

Bienvenidos al repositorio en GitHub para QPoC, un QPoC es una Prueba de Concepto simple de Azure ofrece todo lo que necesitas para explorar y experimentar el potencial de la infraestructura de Azure  través de casos de pruebas preconstruidos y sin incurrir en costos iniciales por medio de las sucripciones Azure Free y los servicios que no consumen costos del saldo inicial [cuenta gratuita de Azure](https://azure.microsoft.com/es-es/free/search/?ef_id=_k_d8823ae07f14192268345f37dc19bc1b_k_&OCID=AIDcmm3804ythc_SEM__k_d8823ae07f14192268345f37dc19bc1b_k_&msclkid=d8823ae07f14192268345f37dc19bc1b).

> [!NOTE]
>Las suscripción Azure Free puede requerir una tarjeta de crédito para su activación

Este repositorio contiene un ARM template que despliega una arquitectura simple con Windows Server, un ARM template es una forma declarativa de definir los recursos que se requiere crear y configurar en Azure. Con un ARM template, puedes automatizar y simplificar el proceso de implementación, y asegurarte de que tus recursos se crean de forma consistente y repetible.

## Descripcion del escenario 
Este escenario tiene como objetivo probar algunas de las capacidades de infraestructura de Azure como:
- Redes virtuales, segmentación de redes, separación de recursos, flitrado de puertos, publicación de recursos
- Capacidad de procesamiento, administración de SO
- Velocidad en almacenamiento

## Arquitectura de la solucion

[![simple-iaas.jpg](https://i.postimg.cc/P58vKMNP/simple-iaas.jpg)](https://postimg.cc/HrdLkXwg)
Arquitectura de referencia en donde se implementa  un VNET con dos subredes (Frontend y Backend), ambas maquinas con Windows Server 
No se incluye el despligue de DB

## Parametros
Los parámetros permiten modificar la configuración del ARM Template para QPoC estos son algunos de los parámetros a tener en cuenta si se quiere modificar el despliegue:
-	Nombres: se encuentran dos tipos de nombre según sea la máquina virtual "virtualMachineName1" (VM-FRONT, VM-BACK) a la que están asociados de esta forma vamos a ver que recursos como las tarjetas de red "networkInterfaceName1", network security group "networkSecurityGroupName1", ip públicas  "publicIpAddressName1" entre otros.
-	Redes: la VNET se llama VNET-POC y esta segmentada por defecto Enel parámetro “addressPrefixes” 192-18.0.0/16 también se crean dos subnets "subnets" SUBNET-FRONT 192.168.10.0/24 y SUBNET-BACKEND 192.168.20.0/24.
-	Tipo de máquina virtual: el tamaño de las máquinas virtuales puede cambiarse en el parámetro “virtualMachineSize", 
Nota: por defecto está configurado Standard_B1s este SKU es gratuito por 750 horas mensuales
-	Usuario y contraseña: el parámetro "adminUsername" es el nombre del usuario administrador de Windows, por defecto es Adminpoc, "adminPassword" la clafe de Windows por defecto es MSLatam2024*/
-	Auto apagado: para optimizar los recursos limitados las maquinas virtuales tienen configurado un auto apagado los parámetros a tener en cuenta son “autoShutdownTime" la hora del apagado es 20:00 8:00pm, "autoShutdownTimeZone" zona horaria algunas zonas horarias son:
  --SA Pacific Standard Time: 	(UTC-05:00) Bogota, Lima, Quito, Rio Branco
o	Central Standard Time (Mexico): (UTC-06:00) Guadalajara, Mexico City, Monterrey
o	Pacific SA Standard Time: (UTC-04:00) Santiago
![Lista de zonas horarias](https://learn.microsoft.com/en-us/azure/azure-sql/managed-instance/timezones-overview?view=azuresql#list-of-supported-time-zones )


