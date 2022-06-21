# GiT y GiTHuB
-----

Sistema de control de versiones
: Es un **sistemas que registra los cambios realizados sobre un archivo o conjunto de archivos** a lo largo del tiempo, de nodo que se pude observar el ciclo de vida del archivo


El sistemas de control de versiones más popular es GIT, el cual nos ayuda a guardar el historial de cambios y crecimiento de los archivos de nuestros proyectos.

# ¿Qué es Git y GitHub?
----
Es un software de control de versiones encargado de llevar un registro de todos los cambios realizados a tus archivos al crear un repositorio en la carpeta de tu archivo.

Es una plataforma de desarrollo colaborativo para alojar proyectos utilizando el sistema de control de versiones Git. Se emplea principalmente para la creación de código fuente de programas de computadora.

Se puede conectar tu repositorio a un servidor remoto como GITHUB y así trabajar con muchas personas en el mismo proyecto
si tu o alguien más se equivoca en el archivo, se pude regresar a la versión anterior.

Github puede considerarse como la red social de código para los programadores y en muchos casos es visto como tu curriculum vitae, pues aquí guardas tu portafolio de proyectos de programación.

## Lineas de comandos 
----
Las lineas de comando  nos permiten interactuar con nuestros computadores sin necesidad de utilizar una interfaz gráfica. Sin embargo, las computadoras emplean distintos sistemas de archivos y manejan diferentes comandos, dependiendo del sistema operativo que utilice

### Diferencias entre la estructura de archivos de Windows, Mac o Linux

* La ruta principal en Windows es C:\, en UNIX es solo /.
* Windows no hace diferencia entre mayúsculas y minúsculas pero UNIX sí.
  
Recuerda que GitBash usa la ruta /c para dirigirse a C:\ (o /d para dirigirse a D:\) en Windows. Por lo tanto, la ruta del usuario con el que estás trabajando es /c/Users/Nombre de tu usuario

### Comando básicos en terminal

**Acrónimos**

+ **cd** = change directory
+ **ls** = list
+ **mkdir** = make directory
+ **pwd** = print working directory
+ **rm** = remove
+ **cat** = concatenate (tiene sentido porque este comando nos permite crear archivos, ver su contenido y concatenarlos)

**Comandos**

+ **pwd**: Nos muestra la ruta de carpetas en la que te encuentras ahora mismo.
+ **mkdir**: Nos permite crear carpetas (por ejemplo, mkdir Carpeta-Importante).
+ **touch**: Nos permite crear archivos (por ejemplo, touch archivo.txt).
+ **rm**: Nos permite borrar un archivo o carpeta (por ejemplo, rm archivo.txt). Mucho cuidado con este comando, puedes borrar todo tu disco duro.
+ **cat**: Ver el contenido de un archivo (por ejemplo, cat nombre-archivo.txt).
+ **ls**: Nos permite cambiar ver los archivos de la carpeta donde estamos ahora mismo. Podemos usar uno o más argumentos para ver más información sobre estos archivos (los argumentos pueden ser -- + el nombre del argumento o - + una sola letra o shortcut por cada argumento).
  - **ls -a**: Mostrar todos los archivos, incluso los ocultos.
  - **ls -l**: Ver todos los archivos como una lista.
+ **cd**: Nos permite navegar entre carpetas.
  - **cd /**: Ir a la ruta principal:
  - **cd o cd ~**: Ir a la ruta de tu usuario
  - **cd carpeta/subcarpeta**: Navegar a una ruta dentro de la carpeta donde estamos ahora mismo.
  - **cd .. (cd + dos puntos)**: Regresar una carpeta hacia atrás.
  - Si quieres referirte al directorio en el que te encuentras ahora mismo puedes usar cd . (cd + un punto).
+ **history**: Ver los últimos comandos que ejecutamos y un número especial con el que podemos repetir su ejecución.
+ **! + número**: Ejecutar algún comando con el número que nos muestra el comando history (por ejemplo, !72).
+ **clear**: Para limpiar la terminal. También podemos usar los atajos de teclado Ctrl + L o Command + L.


Todos estos comandos tiene una función de autocompletado, o sea, puedes escribir la primera parte y presionar la tecla Tab para que la terminal nos muestre todas las posibles carpetas o comandos que podemos ejecutar. Si presionas la tecla Arriba puedes ver el último comando que ejecutamos.

Recuerda que podemos descubrir todos los argumentos de un comando con el argumento --help (por ejemplo, cat --help).

En este curso aprendimos a usar los comandos de GIT, los cuales fueron :
git init: lo usamos para determinar la carpeta en la que vamos a trabajar.

+ **git status**: lo usamos para saber si tenemos un archivo añadido o borrado en nuestro proyecto, para saber en la rama en la que estamos y si tenemos commits.
+ **git add**: es para añadir un archivo a nuestra rama seguidamente ponemos entre comillas el nombre de nuestro archivo o poner un punto para añadir todos los archios de nuestra carpeta.
+ **git rm**: lo usamos para borrar un archivo que hayamos añadido, para eliminarlo por completo de nuestra rama usamosgit rm --cached.
+ **git commit**: se usa para añadir un commit a nuestra rama, también podemos ponerle un -m seguidamente ponemos entre comillas nuestro ensaje.
+ **git config**: muestra configuraciones de git también podemos usar –list para mostrar la configuración por defecto de nuestro git y si añadimos --show-origin inhales nos muestra las configuraciones guardadas y su ubicación.
+ **git config --global user.name**: cambia de manera global el nombre del usuario, seguidamente ponemos entre comillas nuestro nombre.
+ **git config --global user.email**: cambia de manera global el email del usuario, seguidamente ponemos entre comillas nuestro nombre.
+ **git log**: se usa para ver la historia de nuestros archivos, los commits, el usuario que lo cambió, cuando se realizaron los cambios etc. seguidamente ponemos el nombre de nuestro archivo.



