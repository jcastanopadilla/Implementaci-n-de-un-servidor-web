# Implementación de un servidor web 
Asignatura: Configuración de redes
Tema: 
-	OpenStack
-	Instalar y configurar Apache o Nginx.
-	Desplegar una aplicación web sencilla.
## Jose Miguel Castaño Padilla

OpenStack 
Objetivo: Desplegar servicios de red en la nube mediante el framework OpenStack.
## ¿Qué es OpenStack?
Es una plataforma de software libre y de código abierto utilizada para crear y gestionar infraestructuras de computación en la nube, tanto nubes privadas como públicas. Funciona agrupando recursos físicos (computación, red y almacenamiento) y asignándolos como recursos virtuales que los usuarios pueden autogestionar a través de APIs o un panel de control.
## ¿Para qué sirve OpenStack?
El propósito principal de OpenStack es proporcionar una base para la Infraestructura como Servicio (IaaS), permitiendo a las organizaciones:

-	Crear y gestionar nubes privadas: Las empresas pueden construir su propia infraestructura de nube utilizando hardware estándar, manteniendo el control total sobre sus datos y operaciones.
-	Ofrecer servicios de nube pública: Los proveedores de servicios pueden utilizar OpenStack para ofrecer servicios de nube a clientes externos.
-	Automatizar el aprovisionamiento de recursos: Permite a los usuarios solicitar y gestionar automáticamente máquinas virtuales, almacenamiento y redes según sus necesidades, sin intervención manual del personal de TI.
-	Simplificar el despliegue en la nube: El proyecto tiene como objetivo principal simplificar el despliegue y proporcionar una buena escalabilidad para diversas cargas de trabajo.
-	Soportar diversas tecnologías: Es compatible con una variedad de hipervisores (como KVM, VMware) y puede gestionar tanto máquinas virtuales como contenedores.
## Componentes clave:
OpenStack está compuesto por una serie de proyectos o herramientas, cada uno encargado de un servicio específico:
- Nova (Computación): Gestiona las instancias de máquinas virtuales, permitiendo su creación, redimensionamiento y eliminación.
- Neutron (Redes): Proporciona servicios de red definidos por software, permitiendo a los usuarios definir sus propias topologías de red.
- Swift y Cinder (Almacenamiento): Swift se encarga del almacenamiento de objetos (altamente escalable para petabytes de datos), mientras que Cinder gestiona el almacenamiento en bloques (similar a los discos duros tradicionales).
- Keystone (Identidad): Es el servicio de directorio centralizado que gestiona usuarios, roles y permisos.
- Glance (Imágenes): Gestiona las plantillas de imágenes de sistemas operativos que se utilizan para desplegar las máquinas virtuales.
- Horizon (Panel de control): Proporciona una interfaz gráfica de usuario (dashboard) para interactuar con los servicios de OpenStack, aunque también se puede gestionar mediante APIs.
<img width="1024" height="1024" alt="ChatGPT Image 15 nov 2025, 11_47_32" src="https://github.com/user-attachments/assets/d871d138-b911-406a-a0f4-c929eeca526d" />

## INSTALACIÓN Y DESPLIEGUE
En este capítulo se abordará la instalación de los SO, softwares y componentes necesarios para el desarrollo de esta guía.
## REQUERIMIENTOS PREVIOS:
Para el adecuado desarrollo de esta guía recomendamos satisfacer los siguientes aspectos:
- Tener una conexión a internet
- Procesador con más de 4 núcleos superior a los 2 GHZ
- 8 GB de RAM o mas
- 50 GB de espacio en almacenamiento o más
## VIRTUAL BOX:
En esta sección se realizará la correcta instalación de la máquina virtual Virtualbox y la creación de otras máquinas virtuales.
## INSTALACIÓN:
Para empezar, ingresa en el navegador la página web de virtual box.
<img width="1365" height="719" alt="Captura de pantalla 2025-11-15 120140" src="https://github.com/user-attachments/assets/daa41ce2-6550-4f07-b322-8d0d874fbed3" />
