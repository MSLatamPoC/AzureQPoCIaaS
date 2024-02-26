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

## Contenido 
