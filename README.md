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

Luego nos aparecerá la siguiente ventana, donde se puede observar la última versión de VirtualBox, que actualmente es la de 7.2.4, damos clic en (Download) que está marcado con la línea roja.

<img width="1365" height="676" alt="Captura de pantalla 2025-11-15 121145" src="https://github.com/user-attachments/assets/ba76b098-ae98-44ea-8d48-6812a5e76cc4" />

Una vez damos clic mostrara lo siguiente y daremos clic donde está marcado Windows hosts y automática mente descarga.

<img width="1363" height="681" alt="Captura de pantalla 2025-11-15 121811" src="https://github.com/user-attachments/assets/b3cc284c-e10b-4ae5-9194-afd0264f2a3f" />
Luego de haber seleccionado Windows hosts, empieza el proceso de descarga de VirtualBox.
<img width="1365" height="675" alt="Captura de pantalla 2025-11-15 122536" src="https://github.com/user-attachments/assets/c0f0d7cf-1903-4f6b-9084-8cdb14e82fea" />

Posteriormente cuando finalice la descarga iniciamos nuestra instalación.
A continuación, se observa la imagen de bienvenida. Posteriormente damos clic, en el botón Next.
<img width="648" height="513" alt="Captura de pantalla 2025-11-15 124328" src="https://github.com/user-attachments/assets/fc41c894-c5bf-45fe-8142-b75fb4818b4c" />

En esta nueva ventana nos muestra las diversas herramientas que nos brinda VirtualBox.

<img width="648" height="514" alt="Captura de pantalla 2025-11-15 124635" src="https://github.com/user-attachments/assets/ed902414-e2d3-47c9-9886-d1c4c08a5660" />

Se deja todo por defecto para que nuestras maquinas virtuales, tengan todas las características que ofrece VirtualBox y damos clic en el botón Next.

En esta nueva ventana, nos muestra una advertencia de que va a instalar una interfaz de red, debido a que prácticamente genera un adaptador de red adicional para las máquinas virtuales, para la correcta instalación, damos clic en el botón Yes.

<img width="651" height="517" alt="Captura de pantalla 2025-11-15 124838" src="https://github.com/user-attachments/assets/ee365913-12f6-446a-92c7-d796114019f9" />

Igualmente, en esta nueva ventana damos clic en Yes.

<img width="650" height="518" alt="Captura de pantalla 2025-11-15 124918" src="https://github.com/user-attachments/assets/4cd3a0a6-e54b-4fce-a7b3-ad81aff1d4db" />

En esta nueva ventana damos clic en Install, si queremos ejecutar la instalación.

<img width="649" height="521" alt="Captura de pantalla 2025-11-15 124957" src="https://github.com/user-attachments/assets/23864410-8ef9-42e7-b46d-9be3e7dd8f18" />

Esperamos que termine de cargar el proceso de instalación.
