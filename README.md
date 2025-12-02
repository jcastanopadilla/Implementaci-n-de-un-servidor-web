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

<img width="649" height="518" alt="Captura de pantalla 2025-11-15 125029" src="https://github.com/user-attachments/assets/ac2ea172-648b-4cb8-8a91-cb31aae6ee48" />

Luego de finalizar el proceso de instalación de forma correcta, en la siguiente ventana, el instalador preguntara si deseas iniciar virtualBox, en este caso desmarcamos la opción.

<img width="650" height="513" alt="Captura de pantalla 2025-11-15 125103" src="https://github.com/user-attachments/assets/99ceb959-86fc-473a-9c63-7af06f6cc2a3" />

Posteriormente de desmarcar la opción, damos clic en el botón Finish

<img width="655" height="515" alt="Captura de pantalla 2025-11-15 125132" src="https://github.com/user-attachments/assets/17c98684-cdaa-488a-a89e-457f167d2024" />

Al terminar, nos dirigimos al escritorio de nuestro ordenador y damos clic en el icono de VirtualBox.

<img width="1365" height="725" alt="Captura de pantalla 2025-11-15 125259" src="https://github.com/user-attachments/assets/839269ce-6374-492c-8cb5-8d7e308ee398" />

Como podemos observar ya se encuentra correctamente instalado virtualBox, listo para virtualizar cualquier sistema operativo.

<img width="1364" height="724" alt="Captura de pantalla 2025-11-15 125736" src="https://github.com/user-attachments/assets/0a59ecfd-75c1-4008-b9b9-36ce7e9773bc" />

Una vez realizado el apartado anterior, nos dirigimos a la página de descargas en la web de Ubuntu.

Donde hacemos clic en el botón verde que aparece.

<img width="1365" height="679" alt="Captura de pantalla 2025-11-15 130249" src="https://github.com/user-attachments/assets/94a32f44-d49f-45a4-9251-5128f3952048" />


<img width="1365" height="677" alt="Captura de pantalla 2025-11-15 130548" src="https://github.com/user-attachments/assets/b2fdf033-0690-45cd-be0d-4bc22be1c0e6" />

Para crear la máquina virtual procedemos a agregar una nueva, desde la vista principal de VirtualBox, haciendo clic en el botón correspondiente como se observa en la figura.

<img width="1363" height="720" alt="Captura de pantalla 2025-11-15 130927" src="https://github.com/user-attachments/assets/e0621bc6-002f-4942-be4b-4dadf088d569" />

Posteriormente crearemos la maquina con los parámetros que deseemos como el nombre, en este caso Ubuntu Server, no se debe seleccionar la ISO en este paso.

<img width="829" height="553" alt="Captura de pantalla 2025-11-15 131502" src="https://github.com/user-attachments/assets/6d73d741-6478-4a6b-b76d-ec6fbc05122c" />

Luego, haremos clic en Hardware para asignarle algunos recursos a la máquina y asignaremos valores acordes a la maquina teniendo en cuenta las recomendaciones dadas en este capítulo.

<img width="831" height="555" alt="Captura de pantalla 2025-11-15 132201" src="https://github.com/user-attachments/assets/84b834ca-1dde-4638-bddd-b78c24bf05e4" />

Asignar al procesador más de 4 núcleos.
## Recomendaciones:

La guía de Ubuntu para Instalar Microstack [3], recomienda asignar más de 8Gb de la memoria ram, pero esto es subjetivo si le asignamos más del 65% del que tenemos disponible para este ejemplo (8GB), puede hacer colapsar el sistema y producir el famoso “Kernel Panic”, debemos de tener mucha precaución con este procedimiento porque en ocasiones este incidente daña la máquina virtual.

Posteriormente haremos clic en terminar y culminaremos la creación de la máquina virtual.

## Configuración Máquina virtual:

Ahora procederemos a configurar la máquina virtual antes de Iniciarla. Para ello seleccionaremos la máquina virtual y haremos clic en el botón configuración.

<img width="1365" height="767" alt="Captura de pantalla 2025-11-15 133010" src="https://github.com/user-attachments/assets/1f38104f-108c-476e-b8e0-e61de9a28f39" />

Ahora se montará la imagen ISO del servidor de Ubuntu (de no hacerse de esta forma VirtualBox suele crearle un usuario sin permisos de super usuario y debe asignarlo manualmente). Para ello iremos a la sección de almacenamiento, luego en el controlador IDE que se encuentra vacío haremos clic, en la parte lateral de la pestaña denominada atributos haremos clic en el icono del CD y finalmente en la opción “Choose a disk file…”.

<img width="1069" height="468" alt="Captura de pantalla 2025-11-15 133400" src="https://github.com/user-attachments/assets/2c405cdc-47e3-418f-aff2-ba4cffb8f559" />

Se abrirá una nueva ventana donde debemos buscar la ISO del servidor Ubuntu, previamente obtenida, cuando se encuentre se selecciona y haremos clic en el botón abrir que se encuentra en la parte inferior.

<img width="812" height="500" alt="Captura de pantalla 2025-11-15 134610" src="https://github.com/user-attachments/assets/ecbea6a5-288c-4062-a83d-cd3f4f50dac0" />

<img width="808" height="475" alt="Captura de pantalla 2025-11-15 135112" src="https://github.com/user-attachments/assets/d9b4ace5-6957-4024-b49d-42c927a931dc" />

En la misma ventana procedemos a abrir la sección denominada red, situándonos en la pestaña del adaptador (1) o primer adaptador, estableceremos la configuración de adaptador puente, seleccionaremos la tarjeta de red con la cual tengamos acceso a internet (en caso de tener dos “Wifi o Ethernet”) y finalmente clic al botón aceptar.

<img width="781" height="458" alt="imagen" src="https://github.com/user-attachments/assets/5ac9c090-ab43-4773-833a-cc9ee96755e3" />


## Instalación de la Imagen de Ubuntu Server
Al encender la maquina esperaremos un momento y nos saldrá el siguiente menú donde deberemos escoger el idioma del sistema, en este caso el español y presionamos la tecla enter.

<img width="1172" height="716" alt="Captura de pantalla 2025-11-15 142915" src="https://github.com/user-attachments/assets/7df24284-f3ab-459b-91df-fb63f998c3d9" />

Se procede a configurar el teclado, si usted conoce su teclado puede asignarlo manualmente, en caso contrario muévase con las flechas de su teclado a la opción (Identificar teclado), presione la tecla enter, siga las instrucciones que aparecen en pantalla, finalmente muévase a la opción hecho y presione la tecla enter.

<img width="583" height="497" alt="imagen" src="https://github.com/user-attachments/assets/348e7781-6e5f-437d-b0e4-e9880aa8c644" />

En el tipo de instalación escogeremos la opción de Ubuntu server, para instalar completamente el sistema para tener una “mejor experiencia”, tal como lo indica el instalador.

<img width="589" height="506" alt="imagen" src="https://github.com/user-attachments/assets/9eda337d-7f5d-4339-b057-30037bf5ae49" />

Para las conexiones de red no realizaremos ningún ajuste, solo seleccionaremos hecho.

<img width="648" height="554" alt="Captura de pantalla 2025-11-15 181959" src="https://github.com/user-attachments/assets/21fe2f11-66ac-427b-b28b-74f79a05b395" />

No se configurará un proxy, por lo tanto, solo seleccionaremos hecho.

<img width="593" height="504" alt="Captura de pantalla 2025-11-15 182053" src="https://github.com/user-attachments/assets/f9a2b4dd-b0c4-4cc0-a229-30900a4bf215" />

En este nuevo paso se deja tal cual como viene por defecto (No modificar) y seleccionaremos hecho

<img width="585" height="502" alt="Captura de pantalla 2025-11-15 182133" src="https://github.com/user-attachments/assets/efc058a6-369f-4af6-b3c7-319e2ee5ecea" />

Para la configuración del almacenamiento optaremos por usar el disco entero, para automatizar la distribución de las particiones de este.

<img width="586" height="503" alt="imagen" src="https://github.com/user-attachments/assets/042cc943-6c03-418f-af43-08ddbf3af8b6" />

Este nuevo paso es solo informativo, nos mostrara la distribución de las particiones del disco, el cual con anterioridad ha sido seleccionado para que tomara todo el disco y asignara automáticamente los tamaños apropiados; solo seleccionaremos hecho.

<img width="588" height="504" alt="Captura de pantalla 2025-11-15 182757" src="https://github.com/user-attachments/assets/a08f52d1-4407-468b-9776-75390daf810d" />

Posteriormente nos solicitara una confirmación, seleccionaremos continuar.

<img width="589" height="502" alt="Captura de pantalla 2025-11-15 182910" src="https://github.com/user-attachments/assets/4c518a76-c52b-47a2-afe7-25bc3402ff56" />

Procederemos a configurar el perfil del servidor, colocaremos nuestro nombre, el nombre del servidor (con este nombre se reconoce el equipo en la red).

<img width="590" height="503" alt="imagen" src="https://github.com/user-attachments/assets/ed7fb542-2fb1-4820-a818-864b918a3c83" />

## Recomendaciones:

Tratar de usar nemotecnia para el nombre del servidor y de usuario, estos serán importantes más adelante.

Use una contraseña corta para que pueda desarrollar con facilidad esta guía.

Instalaremos un servidor SSH, por si se siente más cómodo para trabajar remotamente en el servidor con una herramienta como Putty, para ello seleccionaremos la opción (Instalar servidor OpenSSH) y culminaremos seleccionando hecho.

<img width="592" height="496" alt="imagen" src="https://github.com/user-attachments/assets/4308bcb6-3ef9-47d2-8401-a717eff031e5" />

No se agregarán características adicionales, por lo tanto, se descartan y se selecciona hecho.

<img width="590" height="501" alt="Captura de pantalla 2025-11-15 184738" src="https://github.com/user-attachments/assets/b976a32d-e8ae-4657-a6f9-9201985bafc4" />

Se inicia el proceso de instalación, al finalizar todo el proceso quedara un registro de las acciones detalladas, debemos seleccionar (Reiniciar ahora).

<img width="590" height="505" alt="Captura de pantalla 2025-11-15 184905" src="https://github.com/user-attachments/assets/ee7dbeab-d710-4e5e-a6ed-d2b0510dc2a4" />

Al iniciar nos pedirá el usuario y contraseña, que hemos puesto con anterioridad, de esta forma habremos culminado la instalación satisfactoriamente.


<img width="585" height="329" alt="imagen" src="https://github.com/user-attachments/assets/b94b0448-3168-48af-afc4-4ff7307ff7ea" />

## Microstack (OpenStack)

Procederemos a instalar Microstack
- sudo su
- apt update && apt upgrade


<img width="589" height="331" alt="imagen" src="https://github.com/user-attachments/assets/2b1d9765-8400-4ac5-9195-32ca55507583" />

- snap install microstack –-beta


<img width="730" height="411" alt="imagen" src="https://github.com/user-attachments/assets/86bcb976-a19b-4d8b-8ed0-420feb622f2d" />

## Inicialización de microstack

Para poder usar todo el ecosistema de openstack, debemos inicializar microstack, este procedimiento solo se debe realizar una sola vez, puede demorar entre 10 a 60 minutos dependiendo del equipo.

- sudo microstack init --auto –control


<img width="731" height="409" alt="imagen" src="https://github.com/user-attachments/assets/daffb4df-1fbb-463f-9209-8113d57a484e" />

## Recomendaciones

En esta etapa no sobrecargue el sistema de la maquina anfitrión (la computadora donde ejecuta VirtualBox), el computador tratara de consumir todos los recursos.

## XFCE

Para poder hacer una gestión del sistema de forma visual procederemos a instalar XFCE, el cual es un entorno grafico ligero para poder simular más un entorno de producción en nuestro servidor Ubuntu, para ello ejecutaremos la siguiente instrucción como super usuario (si estas en una sesión como super usuario ignora sudo).

- sudo apt install -y xfce4


<img width="730" height="411" alt="imagen" src="https://github.com/user-attachments/assets/a431320c-9b8a-4212-a5b1-01ec295df3b7" />

Después de instalado, para abrir XFCE debemos ejecutar la siguiente instrucción (no es necesario lanzarlo como super usuario):

startx

<img width="1280" height="960" alt="image" src="https://github.com/user-attachments/assets/4e37e205-8e5d-49be-a1f7-99df49502969" />

## Recomendaciones
En producción no es recomendable usar entornos gráficos.
## Firefox
Procederemos a instalar el navegador web Firefox, ver figura 46; para ello abrimos la consola y ejecutamos el siguiente comando:

sudo apt -y install firefox

<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/3ed6e954-ae8d-4ac0-8425-0390da845734" />

Una vez culminada la instalación, podremos ver algo similar a la siguiente figura:

<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/3cc310b4-d6ac-41cd-b1ea-106deea1ef7a" />

## Ejecución y configuración

En esta sección se abordará la ejecución de openstack, donde se observará como entrar como administrador y configurar el entorno completo.

## Panel principal (Dashboard).

Para abrir el dashboard de openstack principalmente debemos conocer la IP en la cual se encuentra montado el servidor para posteriormente abrir Firefox y colocar la IPV4 encontrada en la URL. Para ello ejecutaremos el siguiente comando:

ip a s

Posteriormente ejecutado el comando buscaremos la interfaz denominada br-ex, copiaremos su IPV4 de acceso y abriremos el navegador.

<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/d56868bf-3ecd-4866-bd26-ce018c21bc38" />

Una vez abierto el navegador en la IPV4 encontrada, nos puede salir una advertencia, Para abrirla haremos clic en (avanzado) y luego en (aceptar el riesgo y continuar).

<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/16e6fe51-ef90-4f9a-9e32-3bd289c3c565" />

Nos pedirá un nombre de usuario y contraseña.

<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/381813d8-4d14-475a-a4ba-3a619488da99" />

Para encontrar la contraseña del dashboard usamos el siguiente comando:

sudo snap get microstack config.credentials.keystone-password

<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/15cb7149-6d3e-4900-beb1-a3f3fd053123" />

Posteriormente ingresamos esta contraseña con el usuario “admin”, estas son las credenciales para ingresar al dashboard de openstack.

<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/073ece89-fc48-410d-a50f-a4460ba0ae64" />

<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/b2e71cd6-3e4a-4ea0-8c0f-d462686ce32f" />

## Descripción del panel de gestión general.

Dentro del dashboard encontraremos diferentes opciones que pueden llegar a confundir en una primera impresión, por ello debemos tener en cuenta que openstack es muy amplio y podemos tener proyectos, que tienen diferentes desarrollos, arquitecturas y requerimientos. Para el desarrollo de esta guía trabajaremos con el proyecto que se incluye por defecto, no obstante, hay dos paneles de gestión, donde se puede gestionar el proyecto en cuestión o todos.

<img width="536" height="328" alt="Captura de pantalla (3)" src="https://github.com/user-attachments/assets/a75412cb-f660-49af-be01-8a53bdf971bb" />

## GESTIÓN DE GRUPOS DE SEGURIDAD

En esta sección se procederá a la realización de la creación de un grupo de seguridad.

## CREACIÓN DE UN GRUPO DE SEGURIDAD

Para crear un grupo de seguridad debemos situarnos dentro del proyecto, en la sección de Network (red), la pestaña de Security Groups (Grupos de seguridad). Posteriormente debemos hacer clic sobre Create Security Group (Crear grupo de seguridad), eso nos desplegara un modal.

<img width="902" height="466" alt="Captura de pantalla (4)" src="https://github.com/user-attachments/assets/47f8432e-dc91-4f5e-9d39-95fa273d37a1" />

Posteriormente se llenarán los campos requeridos como el nombre, la descripción es opcional, pero en un ambiente profesional es recomendable dejar un comentario de su funcionalidad de recordatorio o para que otro administrador comprenda que hace este y al culminar se hará clic sobre Create Security Group (Crear grupo de seguridad).

