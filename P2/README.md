# Práctica 2: Dominios en WS mediante powershell:

## Por: Naim y Iván
_______________________________________________
_______________________
Índice:
1. ¿Qué es un controlador de dominio y qué funciones principales tiene?
	- FSMO
	- Catálogo global
2. Herramientas de administración de dominios
	- Herramientas vistas en clase
	- Agrupación de herramientas
3. Dominio y controlador de dominio (powershell)
	- Instalación de un dominio básico
	- Promover el dominio a controlador de dominio
	- Degradar el controlador de dominio

____
____
IVÁN:

## 1. ¿Qué es un controlador de dominio y qué funciones principales tiene?:

Un controlador de dominio es un servidor que gestiona las solicitudes de autenticación de los usuarios de una empresa.

### FSMO: 

Es un contenedor de rol capacitado para analizar las peticiones del grupo RID y estos roles no dejan que sucedan problemas en la clonación, esto es, en ciertas funciones, como cambio de contraseña, actualización de objeto, creación de la unidad organizativa, etc. Cuando en alguna de estas variables exista un conflicto, el controlador de dominio se ocupará de solucionarlo dando prioridad al último cambio qué se haya hecho.

### Catálogo Global:

Deja que los usuarios y aplicaciones busquen objetos en un árbol de dominio de Active Directory.

_____
_____

NAIM:

# 2. Herramientas de administración de dominios:
## 2.1 Herramientas vistas en clase
### -Liberador de espacio de disco:
La herramienta *Liberador de espacio de disco*, se dedica a borrar los archivos innecesarios en Windows Server, como archivos basura, archivos grandes, desinstalar programas, archivos temporales, papelera de reciclaje...
Esto es útil para que podamos encontrar nuestros archivos con mayor facilidad o aumentar la velocidad de lectura del disco.

![captura1](/P2/images/Captura1.PNG)

### -Centro de administración de Active directory:
Es una herramienta que permite administrar multitud de aspectos como los usuarios, grupos, unidades organizativas, dominios, equipos... Además podemos incluir en su diseño la mayoría de las tareas que necesitemos para poder acceder a ellas de la forma más rápida.

![captura2](/P2/images/Captura2.PNG)

### -Configuración del sistema:
Es una herramienta que permite seleccionar distintos procesos de inicio, controlar los servicios, opciones avanzadas de arranque, y además, nos permite iniciar herramientas que pueden diagnosticar problemas o conflictos de software.

![captura3](/P2/images/Captura3.PNG)

### -Administración de equipos:
Esta consola nos permite administrar servicios, dispositivos y usuarios entre otras tareas.

![captura4](/P2/images/Captura4.PNG)

## 2.2 Agrupación de herramientas
Podemos utilizar el complemento MMC (Microsoft Management Console) para agrupar las herramientas más utilizadas y que sea más cómodo su uso. Éstas se llaman consolas y se guardan en archivos con extensión .msc.
	
_____

# 3.Dominio y controlador de dominio (powershell)
## Instalación de un dominio básico.
+ Para la instalación de un dominio básico desde powershell primero necesitaremos abrir la misma línea de comandos como administrador:

![capturaA1](/P2/images/CapturaA1.PNG)

+ Instalar los servicios de Dominio de Active Directory con el comando:
`Install-WindowsFeature -Name AD-Domain-Services -IncludeManagementTools`

![capturaA2](/P2/images/CapturaA2.PNG)

+ Una vez instalado, ejecutar el siguiente para que el servidor pase a controlador de dominio:
`Install-ADDSForest -DomainName "NaimyIvan" -ForestMode "Windows2016Forest" -DomainMode "Windows2016Domain" -InstallDNS -NoRebootOnCompletion`

![capturaA3](/P2/images/CapturaA3.PNG)

A mi no me ha funcionado, y no sé muy bien la causa, pero es exactamente dicho comando y debería de salir bien.

## Promover el dominio a controlador de dominio.
+Podemos promover el servidor a controlador de dominio con el comando: 
`Install -ADDSDomainController -DomainName "NaimyIvan" -InstallDNS -Credential (Get-Credential)`

![capturaA4](/P2/images/CapturaA4.PNG)
![capturaA5](/P2/images/CapturaA5.PNG)

Me salió de nuevo un error, por mucho que lo intente persiste, aunque se supone que debería de ser de ese modo.

## Degradar el controlador de dominio.
+Para degradar el controlador de dominio necesitaremos reiniciar al acabar el proceso, por lo que debemos acabar nuestras tareas antes de ello, simplemente debemos escribir el siguiente comando para importar el módulo de AD DS:
`Import-Module ADDSDeployment`
	
+Una vez hecho esto, ejecutamos el comando para degradar:
`Uninstall-ADDSDomainController -Force -DemoteOperationMasterRole`

![capturaA6](/P2/images/CapturaA6.PNG)

Tampoco me salió, no se porque falla las credenciales, pero esta, repito, es la forma correcta de hacerlo por powershell
No he podido practicarlo más hasta que se realice correctamente debido a falta de tiempo personal, disculpe profesor.
