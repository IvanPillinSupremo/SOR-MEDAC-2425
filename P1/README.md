# MANUAL DE WINDOWS SERVER
## Por Naim y Iván 
___
______

### Indice:
+ 1. Características y requisitos del sistema operativo
+ 2. Creación, configuración de la máquina virtual y instalación del sistema operativo.
+ 3. Configuración básica
   - 3.1 Personalización del entorno del servidor
   - 3.2 Configuración de red
+ 4. Conexión de equipos (Active Directory)
+ 5. Cortafuegos

____





## 1. Características y requisitos del sistema operativo Windows Server 2019

Windows Server está desarrollado en C++ y Asambler, una de sus características más destacadas para equipos de trabajo es que es un sistema multiusuario, además las ventajas que ofrece como sistema operativo son relevantes para favorecer el trabajo de los programadores y desarrolladores, tiene una administración muy sencilla para manejar de forma rápida, flexible y eficiente.

Requisitos de hardware para **Windows Server 2019**:
+ Memoria RAM: 512MB (Se recomienda 2048MB)
+ Procesador: 64 bits a 1,4GHz
+ ROM: 32GB
+ Adaptador de red: Ethernet
+ Resolución de pantalla: 1024 x 768 píxeles.

![WindowsServer](/P1/imagenes/WINDOWSSERVER.png)
___

## 2. Creación y configuración de la máquina virtual

Para la creación y configuración de la máquina virtual primero debemos dirigirnos a **"Herramientas"** desde nuestra máquina virtual y clickar sobre **"Nueva"**.
![captura0](/P1/imagenes/Captura.PNG)

+ Una vez dentro, nos aparecerá un panel donde debemos poner la ruta de nuestra ISO del sistema operativo, y luego seleccionar la edición con **"Experienia de escritorio"**, posteriormente le damos a siguiente.
![captura1](/P1/imagenes/Captura1.PNG)

+ En la siguiente sección, debemos poner nuestro nombre de usuario junto a la contraseña deseada y el nombre que queremos para la máquina, le damos a siguiente una vez lo completemos.
![captura2](/P1/imagenes/Captura2.PNG)

+ En la sección de **"Hardware"** seleccionaremos la RAM y los núcleos que le queremos dedicar a nuestra máquina virtual, en nuestro caso, le dedicaremos 12GB de RAM y 3 núcleos del procesador:
![captura3](/P1/imagenes/Captura3.PNG)

+ Una vez pulsamos siguiente, configuraremos el espacio de nuestra ROM que queremos dedicarle, le daremos 45GB como se nos indica:
![captura4](/P1/imagenes/Captura4.PNG)

+ Por ultimo, nos aparecerá un resumen para que podamos visualizar la configuración deseada, y una vez conformes, podremos pulsar sobre finalizar para crear la máquina virtual.
![captura5](/P1/imagenes/Captura5.PNG)
![captura6](/P1/imagenes/Captura6.PNG)

_______

## 3. Configuración básica

 + 3.1 Personalización entorno del servidor:

 En la personalización, modificaremos el nombre del servidor a **"WIN2019S-G6"** como se nos indica, y la zona horaria **"Madrid"**
 Para ello:
   - Nos dirigimos a **"Configurar este servidor local"** desde la ventana que se nos abre nada mas iniciar el software
   ![captura8](/P1/imagenes/Captura8.PNG)

   - Una vez dentro, debemos pulsar en el nombre del equipo **"WINDOWS-SERVER"**.
   ![captura9](/P1/imagenes/Captura9.PNG)

   - Una vez dentro, desde la sección **"Nombre del equipo"**, clickamos en **Cambiar>*Introducimos nombre deseado>Aceptar"**
   ![captura10](/P1/imagenes/Captura10.PNG)

   - Nos dirá que para aplicar los cambios, debemos reiniciar el servidor, seleccinamos **"Reiniciar más tarde"**, para seguir configurando, y nos dirigimos a la Zona horaria
   ![captura11](/P1/imagenes/Captura12.PNG)

   - Finalmente, seleccionamos la deseada tras pulsar sobre **"Cambiar zona horaria..."**
   ![captura12](/P1/imagenes/Captura13.PNG)

 + 3.2 Configuración de red:

 Para la configuración de red, indicaremos nuestra dirección IP, máscara de red, gateway, y asignaremos una DNS primaria y secundaria sacados de la web OpenDNS:
 Para ello:
   - Click derecho sobre el simbolo de **"Conexión ethernet"** en la esquina inferior derecha, y seleccionamos **"Abrir Configuración de red e Internet"**
   ![captura14](/P1/imagenes/Captura14.PNG)

   - Una vez dentro, nos vamos a la sección **"Ethernet"** y pulsamos sobre **"Cambiar opciones del adaptador"**
   ![captura16](/P1/imagenes/Captura16.PNG)

   - **Click derecho sobre ethernet>Propiedades**
   ![captura17](/P1/imagenes/Captura17.PNG)

   - Una vez dentro, seleccionamos el **"Protocolo de Internet versión 4 TCP/IPv4"** y clickamos sobre **"Propiedades"**, seguidamente asignamos los datos indicados y finalizamos aceptando la configuración:
   ![captura19](/P1/imagenes/Captura19.PNG)
   >La dirección DNS fué concedida por la web **"OpenDNS"**
   ![captura18](/P1/imagenes/Captura18DNS.PNG)

___

## 4. Conexión de equipos (Active Directory)

+ Para habilitar la conexión de equipos con "Active Directory" debemos diriginos hacia la sección **"Roles y características"** ubicada abajo del todo de las opciones del **"Servidor Local"**, seguidamente pulsamos sobre **"Tareas"** y clicamos sobre **"Agregar roles y características"**
![captura20](/P1/imagenes/Captura20.PNG)

   - Una vez dentro, seleccionamos el tipor de instalación basada en características o en roles:
   ![captura21](/P1/imagenes/Captura21.PNG)

   - Seleccionamos nuestro servidor:
   ![captura22](/P1/imagenes/Captura22.PNG)

   - Seleccionamos el **"Servicio de dominio de Active Directory"** agregando dichas características:
   ![captura23](/P1/imagenes/Captura23.PNG)

   - Y tras presionar siguiente, sólo nos queda instalar lo seleccionado:
   ![captura25](/P1/imagenes/Captura25.PNG)
   ![captura26](/P1/imagenes/Captura26.PNG)

___

## 5. Firewall

Para poder configurar nuestro firewall, debemos de abrir nuestro **Panel de control** y dirigirnos a **Sistema y seguridad**
![captura27](/P1/imagenes/Captura27.PNG)
 
Clickamos sobre **"Firewall de Windows Defender"**:
![captura28](/P1/imagenes/Captura28.PNG)

Y una vez dentro, tendremos distintas opciones como desactivar el firewall del servidor incluso según qué red, cambiar la configuración de notificaciones, o opciones más avanzadas:
![captura29](/P1/imagenes/Captura29.PNG)



