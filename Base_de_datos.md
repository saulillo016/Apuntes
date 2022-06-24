# Curso de base de datos 

Una Base de Datos es una colección organizada de información estructurada o datos típicamente almacenados electrónicamente en un sistema computacional. Una base de datos es usualmente controlada por un sistema de administración de bases de dato


## Introducción a bases de datos relacionales 

### Entidades y atributos 
________

Una entidad puede ser cualquier objeto de la vida real o virtual
Ejem:![](https://static.platzi.com/media/user_upload/ENTIDAD%20LAPTOPS-4910405e-b261-44c6-9193-a68d85a92541.jpg)

*Las entidades siempre se escribirán en plural porque nos referimos a varios de ellos*

Un Automóviles sería una entidad y este tendrá varios atributos
+ Volante 
+ Llantas

Por lo que los atributos son necesarios para describir nuestra entidad

*Las entidades y los atributos de representan con figuras que varían su importancia dependiendo de sus símbolos, como se muestra a continuación*

![](https://static.platzi.com/media/user_upload/img-2e2fc1ba-ad77-4045-b7a5-f74a65e3f55e.jpg)


Las entidades se pueden clasificar en débiles o fuertes. Las **fuertes o llaves** se caracterizan por que no dependen de ninguna otra entidad para existir, pueden ser naturales(inherente al objeto) o artificiales (asignado de manera arbitraria). 


==Las entidades **debiles** no pueden existir sin una entidad fuerte==

Cuando se hacen entidades se procura relacionarlas entre si para que tenga mayor cohesion entre las demás partes. 

### Relaciones
--------

Es la manera en la que empezamos alugar nuestras entidades u objetos y se representan con un rombo 
+ La entidades se definen a traves de verbos
+ Se representan con rombos
+ Conectan entidades  mediante cardinalidad
  
### *Cardinalidad*


Cardinalidad
: Es una propiedad de las relaciones que indica la cantidad y correspondencia con la que se puede estar relacionada una entidad, pueden ser:
+ Uno a uno
+ Uno a varios
+ Varios a uno
+ Varios a Varios

Y se representan e la siguiente manera:

![](https://static.platzi.com/media/user_upload/cardinalidd-64af23a5-0433-4e2f-b4fd-f56ff86b8824.jpg)

También encontramos el caso donde una entidad se relaciones a N cantidad de otra entidad y Viceversa y se conoce como entidad ==**N a N**== También conocida como **"Muchos a Muchos"**

![](https://static.platzi.com/media/user_upload/cardinalidad%20n%20a%20n-e8130a46-dd22-41a6-90e9-e737d2c3b4a1.jpg)

Se deben generar diagramas *Entidad relación* para visualizar de manera sencilla todas las relaciones con nuestras entidades y sus respectivos atributos, definiendo el tipo de relación que existe entre uno y otro, ya se 1:1, 1:0, 1:N, N, N.

### Diagramas entidad-relación

Un diagrama es como un mapa y nos ayuda a entender cuáles son las entidades con las que vamos a trabajar, cuáles son sus relaciones y qué papel van a jugar en las aplicaciones de la base de datos. 


![](https://static.platzi.com/media/user_upload/diagrama%20ER-ed0a237c-3e8e-4057-83f2-07fbac9c8548.jpg)

### Diagrama físico

**Tipos de datos**
==Texto==

CHAR(n) : Significa character, es decir almacena caracteres de texto y cadenas de texto.

VARCHAR(n): Es lo mismo que CHAR, almacena cadena de caracteres pero además optimiza el uso de memoria.

TEXT: Es para cadena de caracteres mucho más grandes, ya que CHAR y VARCHA almacenan unicamente 255 caracteres

==Numeros==

INTEGER: Significa entero en español, es para números enteros que vas a colocar en la base de datos.

BIGINT: Lo mismo que integer, es decir numeros enteros, pero para almacenar numeros grandes.

SMALLINT: Para números enteros pequeños de 99 a menos. Usando BIGINT o SMALLINT es mas eficiente en el ahorro de memoria.

DECIMAL(n,s) y NUMERIC(n,s) : Permite declarar números decimales cuando quieres trabajar con moneda o fracciones. Lo primero que añades es el numero entero y lo segundo los decimales.

==Fecha/Hora==

DATE: Almacena solo año, mes y día.
TIME: Almacena horas, minutos y segundos. Las 24 horas del día.

DATETIME y TIMESTAMP: Almacena fecha + tiempo.

==Lógicos==

BOOLEAN: Es un tipo de dato que puede tener solo 2 valores; Verdadero o Falso, 1 o 0, Activo o Inactivo, etc.

**Constriants (restricciones)**

Añadimos reglas a que tipos de datos ya valores se pueden meter, se pueden ir poniendo por celdas para poder tener las reglas deseadas y adaptar la base a tus necesidades

|  Constraint  |  Descripción  |
|----|----|
| NOT NULL| Se asegura que la columna no tenga valores nulos|
|UNIQUE|Se asegura que cada valor en la columna no se repita|
|PRIMARY KEY| Es una combinación de NOT NULL Y UNIQUE|
|FOREIGN KEY| Identifica de manera única una tupla en otra tabla|
|CHECK| Se asegura que el valor en la columna cumpla una condición dada|
|DEFAULT| Coloca un valor por defecto cuando no hay un valor especificado|
|INDEX | Se crea por columna para permitir búsquedas más rápidas|

Las PRIMARY KEY nos ayudan a hacer las relaciones entre entidades y automáticamente lo convierte en un indice
La FOREIGN KEY nos ayudan a relacionar entidades entre tablas foránea.
CHECK crea su propia regla según lo que le mandemos 
INDEX nos permite hacer búsqueda más rápidas en nuestras bases de datos, tiene sus limitaciones cuando existen muchos datos o se van agregando constantemente, se recomienda cuando ya no piensas modificar una tabla y quieres buscar información.

#### Normalización

La normalización como su nombre lo indica nos ayuda a dejar todo de una forma normal. Esto obedece a las 12 reglas de Codd y nos permiten separar componentes en la base de datos:

Primera forma normal (1FN): Atributos atómicos (Sin campos repetidos)
Segunda forma normal (2FN): Cumple 1FN y cada campo de la tabla debe depender de una clave única.
Tercera forma normal (3FN): Cumple 1FN y 2FN y los campos que NO son clave, NO deben tener dependencias.
Cuarta forma normal (4FN): Cumple 1FN, 2FN, 3FN y los campos multivaluados se identifican por una clave única.

El proceso de normalización es un estándar que consiste, básicamente, en un proceso de conversión de las relaciones entre las entidades, evitando:

+ La redundancia de los datos: repetición de datos en un sistema.
+ Anomalías de actualización: Inconsistencias de los datos como resultado de datos redundantes y actualizaciones parciales.
+ Anomalías de borrado: Pérdidas no intencionadas de datos debido a que se han borrado otros datos.
+ Anomalías de inserción: Imposibilidad de adicionar datos en la base de datos debido a la ausencia de otros datos.

==**Primera Forma Normal (1FN)**==
Esta FN nos ayuda a eliminar los valores repetidos y no atómicos dentro de una base de datos.

Formalmente, una tabla está en primera forma normal si:

+ Todos los atributos son atómicos. Un atributo es atómico si los elementos del dominio son simples e indivisibles.
+ No debe existir variación en el número de columnas.
+ Los campos no clave deben identificarse por la clave (dependencia funcional).
+ Debe existir una independencia del orden tanto de las filas como de las columnas; es decir, si los datos cambian de orden no deben cambiar sus significados.


Se traduce básicamente a que si tenemos campos compuestos como por ejemplo “nombre_completo” que en realidad contiene varios datos distintos, en este caso podría ser “nombre”, “apellido_paterno”, “apellido_materno”, etc.

También debemos asegurarnos que las columnas son las mismas para todos los registros, que no haya registros con columnas de más o de menos.

Todos los campos que no se consideran clave deben depender de manera única por el o los campos que si son clave.

Los campos deben ser tales que si reordenamos los registros o reordenamos las columnas, cada dato no pierda el significado.

==**Segunda Forma Normal (2FN)**==
Esta FN nos ayuda a diferenciar los datos en diversas entidades.

Formalmente, una tabla está en segunda forma normal si:

+ Está en 1FN
+ Sí los atributos que no forman parte de ninguna clave dependen de forma completa de la clave principal. Es decir, que no existen dependencias parciales.
+ Todos los atributos que no son clave principal deben depender únicamente de la clave principal.

Lo anterior quiere decir que sí tenemos datos que pertenecen a diversas entidades, cada entidad debe tener un campo clave separado. Por ejemplo:
![](https://static.platzi.com/media/user_upload/Captura%20de%20Pantalla%202019-04-30%20a%20la%28s%29%2017.30.27-e38ed9bb-5d10-4f2b-acdc-fa2fa45433d3.jpg)

En la tabla anterior tenemos por lo menos dos entidades que debemos separar para que cada uno dependa de manera única de su campo llave o ID. En este caso las entidades son alumnos por un lado y materias por el otro. En el ejemplo anterior, quedaría de la siguiente manera:
![](https://static.platzi.com/media/user_upload/Captura%20de%20Pantalla%202019-04-30%20a%20la%28s%29%2017.26.28-2a12f9b9-2f11-4a1d-9cb0-23c2595cc260.jpg)

==**Tercera Forma Normal (3FN)**==
Esta FN nos ayuda a separar conceptualmente las entidades que no son dependientes.

Formalmente, una tabla está en tercera forma normal si:

+ Se encuentra en 2FN
+ No existe ninguna dependencia funcional transitiva en los atributos que no son clave

Esta FN se traduce en que aquellos datos que no pertenecen a la entidad deben tener una independencia de las demás y debe tener un campo clave propio. Continuando con el ejemplo anterior, al aplicar la 3FN separamos la tabla alumnos ya que contiene datos de los cursos en ella quedando de la siguiente manera:
![](https://static.platzi.com/media/user_upload/Captura%20de%20Pantalla%202019-04-30%20a%20la%28s%29%2017.27.43-92a1523a-c6fc-42e6-85fb-86dd87ee20af.jpg)
![](https://static.platzi.com/media/user_upload/Captura%20de%20Pantalla%202019-04-30%20a%20la%28s%29%2017.27.52-cb96ff88-e8f4-4957-8bbb-ded1cc6cf599.jpg)

==**Cuarta Forma Normal (4FN)**==
Esta FN nos trata de atomizar los datos multivaluados de manera que no tengamos datos repetidos entre rows.

Formalmente, una tabla está en cuarta forma normal si:

+ Se encuentra en 3FN
+ Los campos multivaluados se identifican por una clave única
  
Esta FN trata de eliminar registros duplicados en una entidad, es decir que cada registro tenga un contenido único y de necesitar repetir la data en los resultados se realiza a través de claves foráneas.

Aplicado al ejemplo anterior la tabla materia se independiza y se relaciona con el alumno a través de una tabla transitiva o pivote, de tal manera que si cambiamos el nombre de la materia solamente hay que cambiarla una vez y se propagara a cualquier referencia que haya de ella.
![](https://static.platzi.com/media/user_upload/Captura%20de%20Pantalla%202019-04-30%20a%20la%28s%29%2017.29.00-ba58de30-a08d-472a-82f9-ea478bf6fcee.jpg)
![](https://static.platzi.com/media/user_upload/Captura%20de%20Pantalla%202019-04-30%20a%20la%28s%29%2017.29.29-149d96f3-78e4-4a26-8c4a-0f002c81cc2f.jpg)

De esta manera, aunque parezca que la información se multiplicó, en realidad la descompusimos o normalizamos de manera que a un sistema le sea fácil de reconocer y mantener la consistencia de los datos.

Algunos autores precisan una 5FN que hace referencia a que después de realizar esta normalización a través de uniones (JOIN) permita regresar a la data original de la cual partió.

## RDBMS (Relational Database Management System)

Es un programa que nos ayuda a hacer lo teórico a algo practico

La diferencia entre ambos es que las BBDD son un conjunto de datos pertenecientes ( o al menos en teoría) a un mismo tipo de contexto, que guarda los datos de forma persistente para un posterior uso, y el Sistema de gestión de BBDD o sistema manejador, es el que nos permite acceder a ella, es un software, herramienta que sirve de conexión entre las BBDD y el usuario (nos presenta una interfaz para poder gestionarla, manejarla).

RDBMS

+ MySQL
+ PostgreSQL
+ Oracle

Todas toman un lenguaje base, pero cada uno lo apropia, imponiéndole diferentes reglas y características.

Las bases de datos relacionales almacenan datos en tablas. Las tablas pueden crecer y tener una gran cantidad de columnas y registros. Los sistemas de administración de bases de datos relacionales (RDBMS) usan SQL (y variantes de SQL) para administrar los datos en estas tablas grandes.

## Historia de SQL (Lenguaje de consultas estructurado)

Objetivo: hacer un solo lenguaje que unifica a todos los visualizadores de datos, siendo SQL como un estándar

**SQL**
- **S**tructured
- **Q**uery
- **L**anguage

Por otro lado tenemos bases de datos no relacionales como **NOSQL** (Not Sonly Structured Query Language)
![](https://edteam-media.s3.amazonaws.com/community/original/4cf4f171-bd37-4164-988a-d9f8b98e1838.jpg)

### DML

SQL tiene dos grandes sublenguajes, el más grande de ellos es DDL (Data Definition Language) que nos ayuda a crear las estructuras de una base de datos. Se trata de un lenguaje procedimental y declarativo conjunto de instrucciones que apoyarán al proceso de construcción de la BD
Las sentencias DML afectan los registros en una tabla. Estas son operaciones básicas que realizamos sobre datos tales como seleccionar algunos registros de una tabla, insertar nuevos registros, eliminar registros innecesarios y actualizar / modificar registros existentes.

- Create: Nos ayuda a crear bases de datos, tablas, vistas, índices, etc.
- Alter: Ayuda a alterar o modificar entidades.
- Drop: Nos ayuda a borrar. Hay que tener cuidado al utilizarlo.

3 objetos que manipularemos con el lenguaje DDL:

- Database o bases de datos
- Table o tablas. Son la traducción a SQL de las entidades
- View o vistas: Se ofrece la proyección de los datos de la base de datos de forma entendible.

**Views**
- Toman datos de la base de datos, las ordenan de manera presentable, y las convierten en algo consultable recurrentemente.
- Se crea con _CREATE VIEW _ (nombreDeLaVista) AS
SELECT… (por ej. FROM platziblog.people, es decir de cada persona de platziblog -> hacer algo, por ejemplo, trabajar con un atributo, o filtrarla, etc.).
- En el Workbench, se hace click derecho en Views -> Create View, y luego va la sentencia de arriba.
Alter

**Alter table** 
nos permite modificar nuestra tabla. Para hacerlo en el Workbench, luego de crear la tabla, hacemos click derecho en ella -> Alter Table. Alli podremos añadir o quitar atributos, constraints, etc.

**Drop**

- Nos permite eliminar datos. En el Workbench, para eliminar una columna, la seleccionamos con el click derecho -> Delete selected.
- Para eliminar una tabla: DROP TABLE (nombre_De_La_Tabla);
- Para eliminar una base de datos: DROP DATABASE (nombre_de_la_base);








  










