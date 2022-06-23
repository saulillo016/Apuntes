# GiT y GiTHuB Estas solo es una prueba
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
----

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
+ **git add**: es para añadir un archivo a nuestra rama seguidamente ponemos entre comillas el nombre de nuestro archivo o poner un punto para añadir todos los archivos de nuestra carpeta.
+ **git rm**: lo usamos para borrar un archivo que hayamos añadido, para eliminarlo por completo de nuestra rama usamos git rm --cached.
+ **git commit**: se usa para añadir un commit a nuestra rama, también podemos ponerle un -m seguidamente ponemos entre comillas nuestro mensaje.
+ **git commit - am "mensaje"**: hace simultáneamente un add y un commit
+ **git config**: muestra configuraciones de git también podemos usar –list para mostrar la configuración por defecto de nuestro git y si añadimos --show-origin inhales nos muestra las configuraciones guardadas y su ubicación.
+ **git config --global user.name**: cambia de manera global el nombre del usuario, seguidamente ponemos entre comillas nuestro nombre.
+ **git config --global user.email**: cambia de manera global el email del usuario, seguidamente ponemos entre comillas nuestro nombre.
+ **git log**: se usa para ver la historia de nuestros archivos, los commits, el usuario que lo cambió, cuando se realizaron los cambios etc. seguidamente ponemos el nombre de nuestro archivo.
+ **git log --stat**: muestra los cambios específicos después de cada commit
+ **git diff**: muestra los cambios que se han hecho pero que se encuentran en estado de stage, los agregas utilizando git add
+ **git checkout** Con este comando podemos regresar a los estados anteriores de nuestro archivo se escribe el git checkout, el del estado del archivo y en nombre del archivo 

ejemplo:

$ git checkout 17e35fdb0a8eff53cffcc973ec0478db32da23de Github.md

para regresar al archivo actual utilizamos el comando **$ git checkout master **  



**En este apartado vamos a agregar una lista más completa de comandos**

+ $ git init //inicializar el repositorio
+ $ git add nombre_de_archivo.extencion //Agregar el archivo al repositorio
+ $ git commit -m “Mensaje”// Agregamos los cambios para el repositorio
+ $ git add .// Agregar los cambios de la carpeta en la que nos encontramos agregar todo
+ $ git status // visualizar cambios
+ $ git log nombre_de_archivos.extencion //historico de cambios con detalles
+ $ git push //envia a otro repositorio remoto lo que estamos haciendo
+ $ git pull //traer repositorio remoto
+ $ ls //listado de carpetas en donde me encuentro es decir dir en windows
+ $ checkout //traer cambios realizado
+ $ git rm --cached archivo.extencion//se usa para devolver el archivo que se tiene en ram cuando escribimos git add lo devuleve a estado natural mientra esta en staging
+ $ git config --list //muestra la lista de configuracion de git
+ $ git config --list --show-origin//rutas de acceso a la configuración de git
+ $ git log archivo.extencion //muestra la historia del archivo

### ¿Qué es el satging y el respositorio?

-------

![](https://static.platzi.com/media/user_upload/Staging%20y%20Repositorio-01ae5dc2-dc43-4d21-b25d-c7aca0bcd930.jpg)


### Ramas y como funciona un Merge en Git

En GIT, una rama o branch es una versión del código del proyecto sobre el que estás trabajando. Estas ramas ayudan a mantener el orden en el control de versiones y manipular el código de forma segura.
Por defecto, el proyecto se crea en una rama llamada Main (anteriormente conocida como Master). Cada vez que añades código y guardas los cambios, estás haciendo un commit, que es añadir el nuevo código a una rama. Esto genera nuevas versiones de esta rama o branch, hasta llegar a la versión actual de la rama Main.

Cuando decides hacer experimentos, puedes generar ramas experimentales (usualmente llamadas development), que están basadas en alguna rama main, pero sobre las cuales puedes hacer cambios a tu gusto sin necesidad de afectar directamente al código principal.

En otros casos, si encuentras un bug o error de código en la rama Main (que afecta al proyecto en producción), tendrás que crear una nueva rama (que usualmente se llaman bug fixing o hot fix) para hacer los arreglos necesarios. Cuando los cambios estén listos, los tendrás que fusionar con la rama Main para que los cambios sean aplicados. Para esto, se usa un comando llamado Merge, que mezcla los cambios de la rama que originaste a la rama Main.

**Checkout y merge**

Producir una nueva rama se conoce como Checkout. Unir dos ramas lo conocemos como Merge.

Cuando haces merge de estas ramas con el código principal, su código se fusiona, originando una nueva versión de la rama Master (o main) que ya tiene todos los cambios que aplicaste en tus experimentos o arreglos de errores.

Podemos generar todas las ramas y commits que queramos. De hecho, podemos aprovechar el registro de cambios de Git para producir ramas, traer versiones viejas del código, arreglarlas y combinarlas de nuevo para mejorar el proyecto.

Solo ten en cuenta que combinar estas ramas (hacer “merge”) puede generar conflictos. Algunos archivos pueden ser diferentes en ambas ramas. Git es muy inteligente y puede intentar unir estos cambios automáticamente, pero no siempre funciona. En algunos casos, somos nosotros los que debemos resolver estos conflictos a mano.

![](https://static.platzi.com/media/user_upload/Branch%20y%20Checkout-9d05b5e2-887f-4fcb-9065-18079bb3c8a9.jpg)



### Git reset vs Git rm
----

Git reset y git rm son comandos con utilidades muy diferentes, pero se pueden confundir muy fácilmente.

#### Git rm

Este comando nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones. Esto quiere decir que si necesitamos recuperar el archivo solo debemos “viajar en el tiempo” y recuperar el último commit antes de borrar el archivo en cuestión.

Recuerda que git rm no puede usarse así nomás. Debemos usar uno de los flags para indicarle a Git cómo eliminar los archivos que ya no necesitamos en la última versión del proyecto:

+ **git rm --cached**: Elimina los archivos de nuestro repositorio local y del área de staging, pero los mantiene en nuestro disco duro. Básicamente le dice a Git que deje de trackear el historial de cambios de estos archivos, por lo que pasaran a un estado untracked.
+ **git rm --force**: Elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).

#### Git reset

Este comando nos ayuda a volver en el tiempo. Pero no como git checkout que nos deja ir, mirar, pasear y volver. Con git reset volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir. No hay vuelta atrás.

Este comando es muy peligroso y debemos emplearlo solo en caso de emergencia. Recuerda que debemos usar alguna de estas dos opciones:

Hay dos formas de utilizar git reset: con el argumento --hard, borrando toda la información que tengamos en el área de staging (y perdiendo todo para siempre). O, un poco más seguro, con el argumento --soft, que mantiene allí los archivos del área de staging para que podamos aplicar nuestros últimos cambios pero desde un commit anterior.

+ **git reset --soft**: Borramos todo el historial y los registros de Git pero guardamos los cambios que tengamos en Staging, así podemos aplicar las últimas actualizaciones a un nuevo commit.
+ **git reset --hard**: Borra todo. Todo todito, absolutamente todo. Toda la información de los commits y del área de staging se borra del historial.
+ **git reset HEAD**: Este es el comando para sacar archivos del área de staging. No para borrarlos ni nada de eso, solo para que los últimos cambios de estos archivos no se envíen al último commit, a menos que cambiemos de opinión y los incluyamos de nuevo en staging con git add, por supuesto.

## Repositorio remoto

**Comandos para trabajo remoto con GIT**

+ **git clone url_del_servidor_remoto**: Nos permite descargar los archivos de la última versión de la rama principal y todo el historial de cambios en la carpeta .git.
+ **git push**: Luego de hacer git add y git commit debemos ejecutar este comando para mandar los cambios al servidor remoto.
+ **git fetch**: Lo usamos para traer actualizaciones del servidor remoto y guardarlas en nuestro repositorio local (en caso de que hayan, por supuesto).
+ **git merge**: También usamos el comando git merge con servidores remotos. Lo necesitamos para combinar los últimos cambios del servidor remoto y nuestro directorio de trabajo.
+ **git pull**: Básicamente, git fetch y git merge al mismo tiempo.

Adicionalmente, tenemos otros comandos que nos sirven para trabajar en proyectos muy grandes:

+ git log --oneline:Te muestra el id commit y el título del commit.
+ git log --decorate: Te muestra donde se encuentra el head point en el log.
+ git log --stat: Explica el número de líneas que se cambiaron brevemente.
+ git log -p: Explica el número de líneas que se cambiaron y te muestra que se cambió en el contenido.
+ git shortlog: Indica que commits ha realizado un usuario, mostrando el usuario y el título de sus commits.
+ git log --graph --oneline --decorate y
+ git log --pretty=format:"%cn hizo un commit %h el dia %cd": Muestra mensajes personalizados de los commits.
+ git log -3: Limitamos el número de commits.
+ git log --after=“2018-1-2”
+ git log --after=“today1” y
+ git log --after=“2018-1-2” --before=“today”: Commits para localizar por fechas.
+ git log --author=“Name Author”: Commits hechos por autor que cumplan exactamente con el nombre.
+ git log --grep=“INV1IE”: Busca los commits que cumplan tal cual está escrito entre las comillas.
+ git log --grep=“INVIE” –i: Busca los commits que cumplan sin importar mayúsculas o minúsculas.
+ git log – index.html: Busca los commits en un archivo en específico.
+ git log -S “Por contenido”: Buscar los commits con el contenido dentro del archivo.
+ git log > log.txt: guardar los logs en un archivo txt

## Ramas o branches de Git#

Las ramas son al forma de hacer cambios en nuestro proyecto sin afectar el flujo de la rama principal. Esto porque queremos trabajar una parte muy especifica de la aplicación o simplemente experimentar. 

La cabecera o HEAD representan la rama y el commit de esa rama donde estamos trabajando. Por defecto, esta cabecera aparecerá en el último commit de nuestra rama principal. Pero podemos cambiarlo al crear una rama (git branch rama, git checkout -b rama) o movernos en el tiempo a cualquier otro commit de cualquier otra rama con los comandos (git reset id-commit, git checkout rama-o-id-commit).

**¿Cómo funcionan las ramas en Git?**

![](https://static.platzi.com/media/user_upload/Git%20y%20GitHub-1-efd7383d-2bba-4fad-b73f-00813a95efbc.jpg)

+ **git branch -nombre de la rama-**: Con este comando se genera una nueva rama.

+ **git checkout -nombre de la rama-**: Con este comando puedes saltar de una rama a otra.

+**git checkout -b rama**: Genera una rama y nos mueve a ella automáticamente, Es decir, es la combinación de git brach y git checkout al mismo tiempo.

+ **git reset id-commit**: Nos lleva a cualquier commit no importa la rama, ya que identificamos el id del tag., eliminando el historial de los commit posteriores al tag seleccionado.

+ **git checkout rama-o-id-commit**: Nos lleva a cualquier commit sin borrar los commit posteriores al tag seleccionado.


## Repositorios remotos y ramas o branch

Al trabajar con otras personas, es necesario utilizar un repositorio remoto.
­
+ Para copiar el repositorio remoto al directorio de trabajo local, se utiliza el comando git clone <url>, y para enviar cambios al repositorio remoto se utiliza git push.
+ Para actualizar el repositorio local se hace uso del comando git fetch, luego se debe fusionar los datos traídos con los locales usando git merge.

  + Para traer los datos y fusionarlos a la vez, en un solo comando, se usa git pull.
  + Para crear commits rápidamente, fusionando git add y git commit -m "", usamos git commit -am "".
  + Para generar nuevas ramas, hay que posicionarse sobre la rama que se desea copiar y utilizar el comando git branch <nombre>.
  + Para saltar entre ramas, se usa el comando git checkout <branch> ­- Una vez realizado los cambios en la rama, estas deben fusionarse con git merge.
  + El merge ocurre en la rama en la que se está posicionado. Por lo tanto, la rama a fusionar se transforma en la principal.
  + Los merges también son commits.
  + Los merges pueden generar conflictos, esto aborta la acción y pide que soluciones el problema manualmente, aceptando o rechazando los cambios que vienen.

# Git Hub

Paso a paso para subir tu proyecto a Git-hub

![](https://static.platzi.com/media/user_upload/github1-8a3f88c1-7c3c-4369-8171-9b97567f2203.jpg)