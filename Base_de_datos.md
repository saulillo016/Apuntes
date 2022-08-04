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

### DDL

Formar la estructura de la base de datos, se utiliza al inicio del proyecto principalmente


SQL tiene dos grandes sublenguajes, el más grande de ellos es DDL (Data Definition Language) que nos ayuda a crear las estructuras de una base de datos. Se trata de un lenguaje procedimental y declarativo conjunto de instrucciones que apoyarán al proceso de construcción de la BD
Las sentencias DDL afectan los registros en una tabla. Estas son operaciones básicas que realizamos sobre datos tales como seleccionar algunos registros de una tabla, insertar nuevos registros, eliminar registros innecesarios y actualizar / modificar registros existentes.

- Create: Nos ayuda a crear bases de datos, tablas, vistas, índices, etc.

**CREATE DATABASE** test_db: nos ayudara a crear una base de datos y ponerle un nombre.
**USE DATABASE** test_db: Lo usamos para indicar que base de datos de todas las que tenemos queremos utilizar.


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

**Alter table** 
nos permite modificar nuestra tabla. Para hacerlo en el Workbench, luego de crear la tabla, hacemos click derecho en ella -> Alter Table. Alli podremos añadir o quitar atributos, constraints, etc.

**Drop**

- Nos permite eliminar datos. En el Workbench, para eliminar una columna, la seleccionamos con el click derecho -> Delete selected.
- Para eliminar una tabla: DROP TABLE (nombre_De_La_Tabla);
- Para eliminar una base de datos: DROP DATABASE (nombre_de_la_base);

### DML (Data Manipulation Language)


Nos permite manipular la base de datos ya una vez creada y cuanta con los siguientes comandos:


+ **Insert**: agrega un nuevo registro a nuestra tabla de bases de datos, se menciona insertar utilizando **INSERT INTO** y hacia donde se inserta. Ejemplo:

```MySQL
INSERT INTO people (last_name, first_name, address, city)
VALUES (´Hernandez´, ´Laura´, ´Calle 21´, ´Monterrey´)
```
+ **Update**: Actualiza o cambia los datos que ya tenemos. 
  + Necesitamos establecer a que tabla queremos que se dirija para hacer el cambio: UPDATE: people. 
  + Después se le menciona que cambiar: SET last_name = "Chavez", city= "Merida". 
  + Por ultimo se le define donde realizar los cambios: WHERE person_id =1. Ejemplo:
```MySQL
UPDATE: people
SET last_name = "Chavez", city= "Merida"
WHERE person_id =1;
```
Tener mucho cuidado con establecer la condición WHERE, porque sio no se menciona se cambiarían todos los datos de la Base de datos a los definidos *Siempre usar Where para definir donde hacer el cambio*
+ Delete: borra todo loq ue indiquemos que se borre, Ejemplo:
```MySQL
DELETE FROM people
WHERE person_id= 1;
 ```

 De nuevo, si no especificamos el WHERE se podría borrar toda nuestra información. *Tener mucho cuidado de establecer bien el WHERE*
+ Select: Nos trae información de la base de datos: Ejemplo:


```MySQL
SELECT first_name, last_name 
FROM people
 ```
----
## ¿Qué tan estándar es SQL?

Bastante estándar, se puede utilizar tanto en repositorios locales como en la nube sin ningún problema, los lenguajes de DDL y DML, son de alto uso en la industria.

### Creando una bse de datos: tablas independientes.

Se creara un blog de acuerdo a un diagrama físico:
![](https://static.platzi.com/media/user_upload/Capturatable-917266aa-7d16-413d-be30-3ef6f47faac0.jpg)

### Tablas dependientes

Las Foreing Key options son las siguientes:

On update: Significa qué pasará con las relaciones cuando una de estas sea modificada en sus campos relacionados, Por ejemplo, pueden utilizarse los valores:
cascade: Si el id de un usuario pasa de 11 a 12, entonces la relacion se actualizará y el post buscará el id nuevo en lugar de quedarse sin usuario.
_ restrict: _Si el id de un usuario pasa de 11 a 12, no lo permitirá hasta que no sean actualizados antes todos los post relacionados.
set null Si el id de un usuario pasa de 11 a 12, entonces los post solo no estará relacionados con nada.
no action: Si el id de un usuario pasa de 11 a 12, no se hará nada. Solo se romperá la relación.
On delete
_ cascade: Si un usuario es eliminado entonces se borrarán todos los post relacionados.
restrict: No se podrá eliminar un usuario hasta que sean eliminados todos su post relacionados.
_ set null: Si un usuario es eliminado, entonces los post solo no estará relacionados con nada.
no action: Si un usuario es eliminado, no se hará nada. Solo se romperá la relación.

## Consultas
Una consulta bien hecha puede salvar a una empresa si esta bien elaborada. Tenemos mucha información que por si sola no representa nada, pero que si la unimos en un Query podemos descubrir un informe o un tendencia. 

Las consultas o Query en una base de datos juegan un papel muy fundamental, puesto que facilitan de manera considerable los procesos en cualquier empresa.
**ETL** Corresponde al acrónimo de:

+ **Extract**(extraer)
+ **Transform**(transformar)
+ **Load** (Cargar)


ETL hacer parte del proceso de integración de datos, más uan es un componentes muy importante que completa el resultado final en la relación de aplicaciones sy sistemas.

### Estructura básica de un Query

Los queries son la forma en la que estructuramos las preguntas que se harán a la base de datos. Transforma preguntas en sintaxis.

El query tiene básicamente 2 partes: SELECT y FROM y puede aparecer una tercera como WHERE.

La estrellita o asterisco (*) quiere decir que vamos a seleccionar todo sin filtrar campos.

Como le hacemos preguntas a las bases de datos? Los queries transforman nuestras preguntas en el lenguaje que utiliza la base de datos.
Dos partes mas una tercera opcional:
**SELECT** : que datos queremos obtener (que columnas/campos de la tabla).
**FROM** : de donde los queremos obtener (de que tabla, por ejemplo).
**WHERE** : condicion que deben cumplir o filtro que deben pasar los datos a obtener. Es opcional, pero se suele utilizar, ya que sino se obtienen todos los datos sin filtrar ninguno.
Otras sentencias:
**GROUP BY** : de que manera agrupamos los datos (en este caso agrupa por ciudad).
**ORDER BY** : de que manera ordenamos los datos (en este caso, por poblacion).
**HAVING** : otra manera de filtrar los datos.

![](https://static.platzi.com/media/user_upload/SQL-torpedo-1f000591-7381-4596-ba4d-95667a3c10e0.jpg)

#### SELECT

SELECT trata de proyectar, o de presentar. 
SELECT no puede funcionar por si solo, siempre necesitara del FROM

Cuando queremos traer todos los atributos de una tabla, podemos usar el asterisco (*) para omitir colocar todos atributos al lado del SELECT uno por uno.

  
El nombre de las columnas o campos que estamos consultando puede ser cambiado utilizando AS después del nombre del campo y poniendo el nuevo que queremos tener:


```MySQL
SELECT titulo AS encabezado
FROM posts;
 ```

Existe una función de SELECT para poder contar la cantidad de registros. Esa información (un número) será el resultado del query:


```MySQL
SELECT COUNT(*)
FROM posts;
 ```


#### FROM

FROM indica de dónde se deben traer los datos y puede ayudar a hacer sentencias y filtros complejos cuando se quieren unir tablas. La sentencia compañera que nos ayuda con este proceso es JOIN.

Los diagramas de Venn son círculos que se tocan en algún punto para ver dónde está la intersección de conjuntos. Ayudan mucho para poder formular la sentencia JOIN de la manera adecuada dependiendo del query que se quiere hacer.

![](https://static.platzi.com/media/user_upload/FROM%20en%20Fundamentos%20de%20Bases%20de%20Datos%20-%20Google%20Chrome%2029_03_2020%2004_06_00%20p.%20m.%20%282%29-0c28b9b8-7b06-4a28-b1dc-7cbe87669406.jpg)
![](https://static.platzi.com/media/user_upload/FROM%20en%20Fundamentos%20de%20Bases%20de%20Datos%20-%20Google%20Chrome%2029_03_2020%2004_07_53%20p.%20m.%20%282%29-212ac551-e5b9-448d-aaef-eb27b9d174b9.jpg)
![](https://static.platzi.com/media/user_upload/yku64jkyz9121-8283dcd6-59b2-49e3-9c83-1a189379e380.jpg)

