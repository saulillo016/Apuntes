# Introducción a PowerBi
**Business Intelligence**
: Es la habilidad de transformar los datos e información, y a su vez esta información en conocimiento, para agilizar el tiempo en cuanto a la toma de decisiones.

Para esto se necesita pasar por un flujo técnico

**Flujo de BI**
● ETL: Extracción de datos, consolidación de fuentes, limpieza y transformación.
● Modelado: Relaciones, indicadores, optimización.
● Reporting: Visualización de datos, reportes, dashboards, storytelling.

**Power BI**
: Es una solución integral de Business Intelligence, que proporciona una vista detallada de los datos más críticos dentro de una organización.


Para funcionar hace uso de su suit de negocios

**Suite de Negocio**
● Power BI Desktop: Herramienta de escritorio orientada al ambiente de desarrollo, que permite conectarte a diversas fuentes de datos y crear reportes.
● Power BI Service Service: En la nube que permite establecer todo el ambiente colaborativo.
● Power BI Mobile: Aplicación para celular que permite visualizar e interactuar, con un informe desde cualquier dispositivo.

**Componentes de Power BI**
● Power Query ETL : Extracción, transformación y carga de los datos.
● Power Pivot(DAX) Modelamiento: Responder todas las preguntas de negocio.

## Arquitectura de PowerBi
**Arquitectura de Power BI Free**
+ 1 GB de Almacenamiento (fuente de información a cargar)
+ No permite colaboración con otros usuarios.
+ Los reportes se pueden compartir de modo público. (NO RECOMENDABLE EN ENTORNO EMPRESARIAL)

**Arquitectura Power BI Pro**
+ 10 GB de Almacenamiento.
+ Colaboración con usuarios internos con licencia.
+ Opción de puerta de enlace, aplicaciones y recargas de hasta 8 veces al día.
+ costo $ 10 mensual por licencia.

**Arquitectura Power BI Premium**
+ Incluye 100 TB de almacenamiento
 +Colaboración con usuarios sin necesidad de licencia.
+ Mayor escalabilidad y rendimiento que la capacidad compartida en Power BI Service.
+ Opción de puerta de enlace, aplicaciones y recargas hasta 48 veces por día.
+ Costo aprox. $ 5000 mensual.

## Tipos de conexiones

Power BI permite conectarnos a una gran variedad de fuentes de datos, desde archivos Excel, bases de datos en SQL Server, hasta sitios en la web.

Tipos de conexión:
● Importación: Los datos se copian a manera local dentro del modelo de Power BI (es el tipo más común).
● Direct Query: Los datos no se copian, pues cada interacción solicita una consulta a la base de datos.
● Live Connection o Dinámica: Lectura desde SSAS o desde un conjunto de datos de Power BI Service.
● Modelos Compuestos: Combina las tecnologías de importación y Direct Query. También permite utilizar múltiples conjuntos de datos.


## ETL

Muchas veces nuestros datos no están listos para ser analizados visualmente, por lo que debemos pasarlos por un proceso conocido como ETL.

ETL es un proceso intermedio entre las fuentes de datos originales de donde extraemos información, y el modelado de datos para su posterior análisis. ETL consta de tres pasos:

**Paso 1: Extract**
Extraer datos desde cualquier fuente, ya sea archivos planos, binarios, bases de datos o servicios cloud. Pueden ser fuentes operacionales internas (es decir, que recopilan información de transacciones en nuestra empresa), o bien fuentes externas. Esto en función de los análisis que se quieran llevar a cabo.

**Paso 2: Transform**
Transformar, limpiar o enriquecer la información extraída sin modificar la fuente. Es en este paso que se ajustan los datos según el modelo de datos (el cual se diseña previo a la creación del ETL).

**Paso 3: Load**
Cargar los datos ya transformados al modelo de datos.

### Power Query

Es una tecnología de conexión de datos que permite detectar, conectar, combinar y refinar distintos orígenes de datos para satisfacer las necesidades de análisis

Power query es capaz de :

Debes considerar que:
+ Su objetivo es **obtener datos de una variedad de fuentes y prepararlos para su posterior análisis**.
+ Su objetivo **no es analizar los datos** 
+ *Magia*: Colección de pasos que se realizan para llegar a un resultado, además permite retroceder o avanzar sin modificar el origen de datos. Similar a un proceso que realiza un macro en excel.

#### Combinaciones

Combinar fuentes de datos es fundamental para poder cruzar la información y hacer un análisis con todos los datos necesarios. Veamos cómo podemos hacer combinaciones en Power BI.

**Tipos de combinaciones en Power BI**
En Power BI, podemos hacer distintos tipos de combinaciones entre tablas o consultas.

***Anexar***
+ Permite unir dos o más tablas de manera “vertical” (es decir, se añaden filas).
+ Se recomienda que ambas tablas tengan la misma estructura. Si este no es el caso, el sistema añade al conjunto final los campos de todas demás con valores nulos.
+ Similar a una operación UNION de SQL.
+ Los resultados pueden ser una nueva consulta o ser agregada a un paso de la existente.


***Combinar consultas***
+ Nos permite tomar dos  tablas y cruzarlas mediante una columna en común.
+ Usualmente utilizado para complementar información de una tabla.
+ Es el equivalente más cercano a la función JOIN del estándar SQL.
+ Los distintos tipos de combinaciones (y su equivalente en SQL) son:
    +  Externa izquierda (LEFT JOIN)
    + Externa derecha (RIGHT JOIN)
    + Externa completa (FULL OUTER JOIN)
    + Interna (INNER JOIN)
    + Anti izquierda (LEFT EXCLUSIVE JOIN)
    + Anti derecha (RIGHT EXCLUSIVE JOIN)

***Combinar binarios***
+ Permite extraer las tablas de los archivos mediante un proceso automatizado.
+ Usualmente utilizado mediante el conector de carpeta.
+ Es de especialidad utilidad cuando la fuente de información se encuentra demasiado fragmentada como para la operación de anexar.


## Modelado de datos

El modelado de datos consiste en realizar análisis complejos entre varias tablas conectadas por un campo en común. El modelado de datos se realiza con Power Pivot

## Relaciones de tablas 

En bases de datos nos encontramos con los conceptos de relaciones y filtros. Las relaciones se refieren a la correspondencia que hay entre tablas. Los filtros, por otro lado, se refieren a incluir (o no) ciertos registros al consultar una base de datos, en función de ciertos criterios.

Cuando hablamos de relaciones entre tablas, tenemos dos conceptos claves:

+ **Llaves primarias** (Primary Keys): definen la clave principal de la tabla. No pueden contener valores nulos ni duplicados.
+ **Llaves foráneas** (Foreign Keys): es una columna, o conjunto de columnas, que contiene un valor que hace referencia a una fila de otra tabla.

**Tipos de relaciones**
+ 1 a 1 (1-1): ambas tablas se conectan con sus llaves primarias, se trata de un tipo extensión de la tabla.
+ 1 a muchos (1-*): cuando se conecta una llave primaria con una llave foránea de otra tabla. Es la que se debe buscar en Power BI.
+ Muchos a muchos (* - *): ocurre cuando ambas tablas se relacionan por sus llaves foráneas (ninguna de las columnas tiene valores únicos). Se recomienda evitar este tipo de relación.  Debemos evitar en medida de los posible crear relaciones muchos a muchos en PowerBI

## Corrigiendo modelos de datos

**Diseño de un modelo de datos**

Cuando se  habla del diseño de un modelo de datos se encontrara que existen distintos tipos. Sin embargo en Power BI se debe enfocar a un modelo en particular, que por su manera de operar es el que resulta más eficiente. Se trata del modelo esquema de estrella. 

El **modelo de estrella** se compone de:

+ Tabla dimensión (de búsqueda): tiene descripciones de la tabla de hechos. Las dimensiones añaden contexto a los hechos. Por ejemplo: fechas, ubicación, etc.

+ Tabla de hechos (transaccionales o fact): tiene el grueso de la información. Por ejemplo: ventas, subscripciones, órdenes, etc.

Power Bi cuenta con un motor de modelo de datos llamado Vertipaq. El cual se encarga de :

+ Todas las operaciones de análisis de datos (DAX).
+ Utiliza tecnología in-memory que provee un elevado desempeño para almacenamiento y consulta de datos.
+ Permite ciclos de desarrollo corto.

## Lenguaje DAX

+ DAX es una colección de funciones y operadores, que pueden ser utilizados en expresiones que permiten calcular uno o más valores
+ Este lenguaje se encuentra en Excel, Power Bi y SSAS Tabular 
+ Esta pensado para alcanzar mayor cantidad de usuarios

+ Menor curva de aprendizaje para los analistas de datos
+ Aprovecha el conocimiento existente de trabajar con fórmulas de excel
+ Más potente que las formulas de Excel
+ Relaciones de navegación
+ Cálculo de dinámico de dimensiones 
+ Manejo de dimensiones de tiempo. (Time Intelligence)

**¿Qué se puede calcular con DAX?**

+ Columnas calculadas
Crea nuevas columnas en el modelo de datos. Método parta conectar tablas de multiples columnas claves 
+ Tablas calculadas
Crea una nueva tabla derivada de otra tablas 
+ Medidas: crea cálculos dinámicos guardados en memoria. Más eficientes que las columnas calculadas. Soportan la inteligencia de tiempo.

**Convenciones del Lenguaje (Formato General )**

‘Nombre de tabla’ : [nombre de columna]
Ejemplo : ‘tabla productos’ : [Precio]

El nombre de la tabla puede ser omitido al utilizarse en columnas calculadas mas no se recomienda hacerlo

