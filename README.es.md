# Proyecto: Dashboard & Análisis de Datos: Electronic Release Atlas 1990-2000

[English](README.md) | [Español](README.es.md)

## Descripción

En este proyecto del bootcamp en Data Analytics dictado por ThePower aplicare los conocimientos aprendidos del módulo **“Dashboard & Análisis de Datos”**.

Para realizarlo segui las especificaciones recogidas en la lección **“Proyecto: Dashboard & Análisis de Datos”**.

## Contexto

La tematica del proyecto nace como una iniciativa personal debido a que tambien desarrollo actividades hace mas de 20 anos como dee jay y productor de musica electronica, despertando especial interes en conocer los insights de una decada clave para la evolucion de este estilo musical.

## Definición y objetivos del objetivo

“La expansión de la música electrónica en los años noventa: estilos, sellos, formatos, demanda y valor de mercado”

¿Cómo evolucionó la producción, demanda y valoración de los lanzamientos de música electrónica entre 1990 y 2000, y qué estilos, sellos, formatos y países tuvieron mayor peso en el mercado?

Discogs cataloga lanzamientos con información como artista, sello, formato, país, año, tracklist y detalles de edición, lo que permite construir un análisis muy rico desde la perspectiva de colección, edición y mercado físico.

Esto permite conectar el análisis con la evolución de estilos como el house, techno, electro, ambient, downtempo, además de mostrar qué sellos y países impulsaron la escena durante esa década. Discogs comenzó en 2005 como una base centrada en música electrónica antes de ampliar su catálogo a otros géneros y formatos.

Realizar un **análisis exploratorio** de los lanzamientos de música electrónica entre 1990 y 2000 y reflejar los principales hallazgos en un **dashboard**.

## Preguntas de analisis

El análisis se plantea como un estudio sobre la **Producción, demanda y valoración de la música electrónica en los años noventa** y tendrá como objetivo responder preguntas como:

- ¿Cómo evolucionó el número de lanzamientos de música electrónica entre 1990 y 2000?
- ¿Qué estilos y subgéneros concentraron mas lanzamientos discograficos?
- ¿Qué sellos discográficos fueron más prolíficos?
- ¿Qué países publicaron mayor cantidad de lanzamientos?
- ¿Qué formato físico predominó y cómo evolucionó?
- ¿Qué lanzamientos generaron mayor interés entre los usuarios de Discogs?
- ¿Qué relación existe entre el interés de la comunidad, las valoraciones y los precios de mercado?
- ¿Qué artistas, sellos y estilos destacan por demanda, colección o valoración?
- ¿Cómo cambió la composición del mercado electrónico a lo largo de la década?
- ¿Qué estilos alcanzaron mayores precios de mercado?

## KPIs propuestos

- Total de lanzamientos analizados [Total Releases].
- Número de lanzamientos por año [Releases by year]. 
- Número de lanzamientos por estilo o subgénero [Selected styles by year].
- Número de lanzamientos por formato [Formats by year].
- Número de lanzamientos por sello discográfico [Top 10 record labels by release count].
- Número de lanzamientos por país [Releases by country].
- Número de artistas únicos [Unique Artist Credits].
- Número de sellos únicos [Unique Labels].
- Total de usuarios que tienen cada lanzamiento (`have`).
- Total de usuarios que desean cada lanzamiento (`want`).
- Ratio de demanda: `want / have` [Top 10 highest-rated releases].
- Valoración media global.
- Valoración media por estilo, sello, país o año.
- Precio mediano por estilo, sello, país o año.
- Ranking de lanzamientos por `have`, `want`, `num_ratings` y `median_price`.

## Hipótesis iniciales

- El número de lanzamientos de música electrónica creció durante la primera mitad de los años noventa.
- El vinilo fue el formato dominante, especialmente en lanzamientos orientados al club y al DJing.
- House, Deep House, Garage House, Techno y Progressive House concentraron una parte relevante de la producción.
- Existieron sellos especialmente activos, como Strictly Rhythm, Nervous Records, Network Records, Cutting Records, FFRR, Deconstruction, Positiva o Perfecto.
- Los lanzamientos con mayor número de usuarios que los desean pueden presentar precios medianos más elevados.
- La valoración media puede relacionarse con el interés de colección, aunque no necesariamente con el precio de mercado.
- Determinados países, especialmente Estados Unidos, Reino Unido, Alemania, Italia, Países Bajos y Francia, concentraron una parte importante de la producción.

Estas hipótesis deberán validarse o descartarse mediante el análisis exploratorio.

## Estructura del proyecto

Electronic_release_atlas_1990_2000/
│
├── README.md
│
├── data/
│   ├── raw/
│   │   └── 01_discogs_electronic.csv
│   ├── cleaning/
│   │   └── 02_discogs_electronic_cleaning.xlsx
│   └── processed_analytics_dashboard/
│       └── 03_discogs_electronic_processed_analytics_dashboard.xlsm
│
└── lookandfeel/
    ├── printscreen_dashboard_electronic_release_atlas_1990_2000.png
    └── mockup_dashboard_electronic_release_atlas_1990_2000.jpg


## Extracción de columnas

Del archivo de limpieza 02_discogs_electronic_cleaning.xlsx al archivo final 03_discogs_electronic_processed_analytics_dashboard.xlsm: se trasladaron las columnas necesarias desde la hoja Discogs_electronic_cleaning a una segunda hoja Discogs_electronic_processed mediante referencias directas entre hojas, utilizando la fórmula  =Discogs_electronic_cleaning1!A:A . 

Posteriormente, los resultados se convirtieron en valores estáticos mediante Pegado especial > Valores, de modo que la base de datos final no dependa de fórmulas ni referencias a la hoja original para disminuir la carga de procesamiento. Esta hoja constituye la fuente de datos para el archivo final con los releases depurados de donde se sirve el dashboard.

## Requisitos

El proyecto debe cubrir los siguientes puntos:

- **Transformación y limpieza de los datos**
- **Análisis descriptivo de los datos**
- **Dashboard**
- **Informe explicativo del análisis**
- **README del proyecto**

## Herramientas

Para realizar el proyecto se utilizo Microsoft Excel.

## Datos

El dataset utilizado fue **`discogs_electronic.csv`**, Discogs Electronic Music Dataset (1990–2000) cuyo origen es https://www.kaggle.com/datasets/justinpakzad/discogs-electronic-music-dataset-1990-2000?resource=download

Consta de una selección de lanzamientos de música electrónica de 1990 a 2000, principalmente vinilos, algunos CDs y otros formatos. Se ha recopilado a partir del marketplace de https://www.discogs.com la mayor base de datos y plataforma de venta de música en formato fisico del mundo. Los datos se obtuvieron mediante web scraping utilizando Python junto con Scrapy.

El conjunto de datos abarcan diferentes subgeneros que permiten estudiar la producción, circulación y valoración de lanzamientos electrónicos durante una década clave para el house, el techno, el garage, el trance y la cultura de club.

Sugerencias del creador de la base de datos

Rareza y deseabilidad : "Utilice los valores de want/have para determinar qué discos o estilos son raros o mas demandados. Descubra qué discos son populares pero no están ampliamente disponibles y vea si hay un vínculo entre la rareza, la popularidad del artista, el estilo o la fecha de lanzamiento del disco".

Influencias geográficas : "Examine cómo la escena de la música electrónica varió entre países [country_clean]. ¿Qué países fueron líderes en la producción de música electrónica? ¿Cómo variaron los estilos según la región?"

Popularidad e influencia del artista : "Explore qué artistas fueron más influyentes en los 90. Esto podría evaluarse a través de num_ratings, average_rating o el número de personas que want/have sus discos.

## Limitaciones del análisis

El dataset procede de un proceso de scraping y contiene duplicados, errores de catalogación o valores incompletos.
Discogs es una base de datos colaborativa, por lo que la calidad y completitud de los metadatos puede variar entre lanzamientos.
El dataset representa una muestra de lanzamientos electrónicos, no necesariamente la totalidad de la producción musical del periodo (872,171 lanzamientos).
La presencia en Discogs no equivale necesariamente a ventas, popularidad comercial, difusión radiofónica o reproducciones.
Los precios reflejan información de mercado en un momento concreto y pueden estar condicionados por rareza, estado del soporte, edición, demanda de coleccionistas y disponibilidad actual.

## Características principales del dataset

- **Periodo analizado:** 1990–2000.
- **Género principal:** música electrónica.
- **Columnas:** 15 en el dataset original y 19 en el dataset final.
- **Registros:** 32.542 en el dataset original y 29.926 tras el proceso de limpieza.
- **Formatos físicos:** principalmente vinilo, con presencia de CD y otros soportes.


## Diccionario de datos origen

| Columna | Tipo de dato | Descripción |
|---|---|---|
| `artist` | Texto | Artista o grupo principal del lanzamiento. |
| `title` | Texto | Título del lanzamiento discográfico. |
| `label` | Texto | Sello discográfico responsable de la publicación. |
| `country` | Texto | País o región de publicación del lanzamiento. |
| `format` | Texto | Formato físico del lanzamiento, como vinilo o CD. |
| `release_date` | Fecha/Texto | Fecha o año de publicación del lanzamiento. |
| `genre` | Texto | Género principal asignado en Discogs. |
| `styles` | Texto | Estilos o subgéneros asociados al lanzamiento. |
| `have` | Numérico | Número de usuarios que tienen el lanzamiento en su colección. |
| `want` | Numérico | Número de usuarios que desean adquirir el lanzamiento. |
| `num_ratings` | Numérico | Número total de valoraciones recibidas. |
| `average_rating` | Numérico | Valoración media del lanzamiento. |
| `lowest_price` | Numérico | Precio mínimo registrado en el marketplace. |
| `median_price` | Numérico | Precio mediano registrado en el marketplace. |
| `highest_price` | Numérico | Precio máximo registrado en el marketplace. |

## Diccionario de datos final

La estructura final del dataset contiene 16 columnas que recogen información discográfica, clasificación musical, presencia en colecciones y listas de deseos, valoraciones y precios.

| Columna | Tipo de dato | Descripción |
|---|---|---|
| `artist` | Texto | Nombre del artista, grupo o proyecto musical al que se atribuye el lanzamiento. Puede contener denominaciones colectivas como `Various` para recopilaciones de varios artistas. |
| `title` | Texto | Título del lanzamiento discográfico. |
| `label` | Texto | Nombre del sello discográfico asociado al lanzamiento. |
| `country_clean` | Texto | País de publicación del lanzamiento después del proceso de limpieza y normalización. No representa necesariamente la nacionalidad del artista ni la ubicación del sello. |
| `market_regions` | Texto | Región o conjunto de mercados de publicación identificado durante la limpieza geográfica. Su interpretación depende del criterio utilizado para separar países y regiones. |
| `format` | Texto | Formato del lanzamiento registrado en el dataset, por ejemplo, `Vinyl` o `CD`. |
| `release_year` | Número entero | Año de publicación del lanzamiento, extraído y normalizado a partir de la fecha original. El periodo previsto de análisis es de 1990 a 2000, ambos inclusive. |
| `genre` | Texto | Género musical asignado al lanzamiento en el dataset de origen. |
| `styles_clean` | Texto | Estilo o conjunto de estilos musicales asociados al lanzamiento después de su limpieza y normalización. Un mismo registro puede incluir varios estilos. |
| `styles_primary` | Texto | Primer estilo musical asociado al lanzamiento después de su limpieza y normalización. |
| `have` | Número entero | Número de usuarios de Discogs que tenían el lanzamiento añadido a su colección en el momento de la extracción de los datos. No equivale al número total de copias fabricadas o vendidas. |
| `want` | Número entero | Número de usuarios de Discogs que tenían el lanzamiento añadido a su lista de deseos en el momento de la extracción. No representa compras realizadas ni pedidos pendientes. |
| `num_ratings` | Número entero | Cantidad de valoraciones recibidas por el lanzamiento o edición. Permite contextualizar la valoración media. |
| `votes_threshold` | Texto | Cortes de cantidad de personas que valoraron el lanzamiento discografico. |
| `average_rating_clean` | Número decimal | Valoración media de los usuarios asociada al lanzamiento o edición en Discogs. No corresponde a la reputación del vendedor ni a la clasificación del estado físico de una copia concreta. Los valores no disponibles no se integraron como una valoración numérica. |
| `lowest_price_clean` | Número decimal — importe monetario | Valor mínimo de precio recogido para el lanzamiento en el dataset de origen, tras limpiar el campo `lowest_price`. Los valores no disponibles no se integraron como una valoración numérica. |
| `median_price_clean` | Número decimal — importe monetario | Mediana de precio recogida para el lanzamiento en el dataset de origen, tras limpiar el campo `median_price`. Los valores no disponibles no se integraron como una valoración numérica. |
| `highest_price_clean` | Número decimal — importe monetario | Valor máximo de precio recogido para el lanzamiento en el dataset de origen, tras limpiar el campo `highest_price`. Los valores no disponibles no se integraron como una valoración numérica. |
| `release_display` | Texto | Etiqueta descriptiva de identificación que reúne los principales datos de cada lanzamiento y permite distinguirlo dentro del análisis. |


## Unidad de análisis

Cada fila se trata como un registro de lanzamiento discográfico del dataset, no como una canción ni como una venta individual.

La coincidencia de artista y título no se utiliza, por sí sola, para declarar que dos registros son duplicados, ya que pueden corresponder a distintas ediciones o versiones de un lanzamiento.

## Notas metodológicas

### Países y regiones

La variable `country_clean` recoge el país de publicación normalizado, mientras que `market_regions` permite identificar regiones o mercados de publicación.

### Estilos musicales

La variable `styles_clean` puede contener varios estilos asociados a un mismo lanzamiento, por lo que no debe interpretarse como una clasificación de estilo único o principal.

A partir de esta variable, se realizó un proceso de separación y filtrado para obtener una lista de estilos individuales. Esta lista sirve como catálogo de consulta y como apoyo a los recuentos por estilo individual. No constituye por sí sola un segmentador conectado a todos los elementos del dashboard.

En los cálculos que buscan etiquetas completas dentro de `styles_clean`, se incluyen los lanzamientos que contienen ese estilo, aunque también tengan otras etiquetas. Este criterio no debe confundirse con el filtro `style_primary`, que conserva únicamente el primer estilo del texto de origen.

### Valores ausentes

El archivo original utiliza el indicador `--` en algunas valoraciones y precios para las variables categoricas decidi sustituirlo por `Unknown` y para las cuantitativas por null.

La documentación de limpieza especifica indica cómo se han tratado estos valores en cada columna.

### Valoraciones y estado de los ejemplares

La valoración media se interpreta como una evaluación de los usuarios sobre el lanzamiento o edición, sin atribuirla exclusivamente a su calidad artística.

El dataset no incluye el estado del soporte y de la carátula de cada ejemplar, ni el feedback de las transacciones. Por tanto, no permite analizar directamente la satisfacción con el vendedor, el embalaje, el envío o la correspondencia del artículo con su descripción.

### Interpretación temporal

El campo `release_year` corresponde al año de publicación del lanzamiento.

Las variables de colección, listas de deseos, valoraciones y precios corresponden a la información recopilada en el momento de la extracción (2023), no necesariamente al año de publicación.

### Interpretación de precios

Los precios del archivo original incluyen el símbolo `$` cuya divisa corresponde a dolares americanos.

### Tipos de datos

Los tipos indicados en este diccionario son los esperados para el análisis. Su asignación efectiva puede comprobarse en el archivo `03_discogs_electronic_processed_analytics_dashboard.xlsm`.

## Transformación y limpieza

## Eliminación o tratamiento de duplicados.

Como en cualquier proceso de depuración de datos, fue necesario tomar decisiones estratégicas sobre qué criterios definirían un registro duplicado. En este conjunto de datos, no se consideró duplicado cualquier registro que compartiera [artist] [title]: dos ediciones del mismo álbum pueden corresponder a lanzamientos distintos, con valoraciones y precios diferentes en el mercado discografico.

Por ello, se definió una clave compuesta de unicidad basada en seis campos:[artist] [title][ label][ country] [ format ][ release_year_transformed] 

Un registro se consideró duplicado únicamente cuando coincidían simultáneamente estos seis campos. Si, por ejemplo, artista, título, sello, país y formato coincidían, pero el año de edición era diferente, el registro no se trató como duplicado, sino como una edición o reedición distinta del mismo material fonográfico.

Esta decisión responde a la lógica del mercado discográfico: el año de publicación puede afectar de forma relevante al valor de una referencia, ya que no se valora igual una edición original que una reedición posterior. Por tanto, conservar registros con distinto  release_year_transformed  permite mantener ediciones alternativas del mismo álbum como observaciones independientes.

## Revisión de duplicados

Posteriormente, se creó la hoja  Duplicados  como espacio de control de calidad. En ella se generó una vista dinámica mediante la función  FILTRAR , que extrajo únicamente los registros cuya combinación de  [artist] [title][ label][ country] [ format ][ release_year_transformed]  aparecía más de una vez en la base.

La detección se basó en  CONTAR.SI.CONJUNTO , que calcula el número de coincidencias simultáneas en varias columnas. Los registros con un recuento superior a 1 fueron considerados duplicados según la clave compuesta definida.

La hoja  Duplicados  no se utilizó como fuente principal del dashboard, sino como instrumento de revisión y auditoría previa a la depuración final.

## Eliminación de duplicados

Una vez identificados y filtrados los registros marcados como  DUPLICADO , se aplicó la herramienta Datos > Quitar duplicados sobre el conjunto filtrado.

En el cuadro de configuración se seleccionaron exclusivamente las seis columnas que conformaban la clave de unicidad: [artist] [title] [label] [country] [format] [release_year_transformed] 

Excel conservó la primera aparición de cada combinación repetida y eliminó las filas restantes que compartían exactamente esa misma clave. La operación fue permanente, por lo que se mantuvo el archivo original como respaldo para conservar la trazabilidad del proceso.

El resultado fue una base depurada en la que cada combinación de [artist] [title][ label][ country] [ format ][ release_year_transformed]  aparece una única vez. Esta base constituye la fuente de datos para el dashboard y evita que registros repetidos de una misma edición inflen métricas de catálogo, valoración o precio.

## Columna de control

En la hoja  Discogs_electronic_cleaning  se creó la columna de control  [duplicate_count] , calculada mediante las funciones  SI  y  CONTAR.SI.CONJUNTO .
La fórmula comparó cada fila contra el conjunto completo de registros y contabilizó las coincidencias simultáneas en la clave compuesta. Cuando el recuento era superior a 1, la fila se etiquetó como  DUPLICADO ; en caso contrario, como  ÚNICO .

=SI(
  CONTAR.SI.CONJUNTO(
    $A$2:$A$32543; A2;
    $B$2:$B$32543; B2;
    $C$2:$C$32543; C2;
    $D$2:$D$32543; D2;
    $G$2:$G$32543; G2;
    $I$2:$I$32543; I2
  ) > 1;
  "DUPLICADO";
  "ÚNICO"
)

La columna  [duplicate_count]  funcionó como mecanismo de validación y trazabilidad: permitió identificar, filtrar y revisar los registros afectados antes de aplicar cualquier eliminación.

## Eliminacion de generos musicales

En la hoja Discogs_electronic_cleaning dado que el objetivo del análisis es estudiar exclusivamente lanzamientos de música electrónica, se aplicó un filtro sobre la columna  [genre]  para delimitar el universo analítico. Se conservaron los registros clasificados en estilos o subgéneros electrónicos y se excluyeron aquellos asociados a géneros no electrónicos.

Esta segmentación permitió asegurar que las métricas reflejadas en el dashboard correspondieran únicamente a publicaciones de música electrónica. La exclusión de registros fuera de este ámbito no constituyó una depuración de errores, sino una decisión de alcance analítico orientada al objetivo del proyecto.

## Gestion de valores nulos
Para variables cualitativas decidi remplazar los registros vacios por “Unknown” y en las variables cuantitativas reemplazar los registros encontrados por null, 

En el analisis exploratorio identifique valores faltantes en las columnas [country], [styles], se crearon dos columnas auxiliares [country_clean] [styles_clean] y se etiquetaron como  “Unknown” usando las funciones SI ,  CONTAR.SI  y  ESPACIOS para facilitar su identificación en los filtros y visualizaciones del dashboard.  En las columnas [average_rating], [lowest_price], [median_price], [highest_price] se sustituyeron los valores “--” por null mediante la herramienta Buscar y Reemplazar  representando así los datos no disponibles. Se conservaron las filas y no se asignaron ceros a los valores faltantes.

## Control y normalizacion de tipo de formato de celdas

El dataset se limita a extraer datos incompletos la columna [release_date] es del tipo General, y algunas fechas son strings del tipo fecha corta, otras se limitan solo al año y mes y otras solo al año, a modo de conservar el activo me limite a homogeneizar los datos extrayendo solo el dato en comun, el año de lanzamiento creando la columna [release_year] esta vez del tipo personalizada “aaaa”. 

Creacion de la columna [release_year_transform] a partir de la columna [release_day] 
=SI(F32504="";"";SI(ESNUMERO(F32504);SI(F32504<10000;F32504;AÑO(F32504));VALOR(IZQUIERDA(ESPACIOS(F32504);4))))

Creacion de la columna [release_year] a partir de la columna [release_year_transform] para normalizar la columna a formato fecha personalizado “aaaa”
=SI(G32504="";"";FECHA(VALOR(G32504);1;1))

En las columnas [have] [want] [num_ratings] transforme el dato de tipo General a Numero, eliminando decimales. 

En las columnas [average_rating] [lowest_price] [median_price] [highest_price] remplaze el . por la ,  para transformar los datos de texto a numero

Para realizar un control de tipo para todas las columnas numericas finales se creo la columna [type_control] mediante el metodo =ESNUMERO([@[columna]])

El campo [country] estaba afectado por nombres de paises, territorios, mercados y regiones geograficas por lo que decidi segmentar, paises por un lado y territorios, mercados y regiones por otro.

Se reclasificaron los valores de la columna [country] , separando las regiones, agrupaciones de mercados y territorios en una nueva columna denominada  [market_regions] . La columna de países se reservó para los valores correspondientes a países individuales. Esta transformación se realizó mediante una lista auxiliar de clasificación y las funciones  SI ,  CONTAR.SI  y  ESPACIOS , sin eliminar registros ni desglosarlos en varias filas.

Los campos  [country_clean]  y  [market_regions]  se completaron de forma excluyente: los países individuales se conservaron en el primero y las regiones, agrupaciones y territorios se trasladaron al segundo. Por ello, los vacíos generados por esta clasificación no representan pérdida de información. Los registros sin información geográfica en la fuente se identificaron como  "Unknown" .

En la transformacion de la columna [average_rating] se eliminaron las celdas sin valoracion "—" por valores null, la ausencia de información no debe confundirse con un valor numérico igual a cero.

Cambie los numeros con separadores decimales inconsistentes: algunos valores utilizaban punto y otros coma a valores de tipo numerico con la "," como separador de decimales. Para homogeneizar la información y permitir su uso en cálculos del dashboard, se creó una columna auxiliar average_rating_clean y se transformo a tipo de valor numerico con el valor numérico normalizado a dos decimales.

=SI(M2="--";"";VALOR(SUSTITUIR(M2;".";",")))

La funcion realizó tres operaciones:
•	Comprobó si la celda original estaba vacía, para conservar los registros sin valoración como celdas vacías.
•	Reemplazó los puntos por comas mediante  SUSTITUIR , homogeneizando el separador decimal.
•	Convirtió el texto resultante en un valor numérico mediante  VALOR .

La columna  [average_rating_clean_2]  contiene las valoraciones medias en formato numérico, con el separador decimal unificado. Esta columna permite calcular indicadores como el promedio de valoración, identificar lanzamientos mejor valorados y realizar comparaciones por estilo, artista, año u otras dimensiones del dashboard.

La columna original  [average_rating] y [average_rating_clean _1] se conservaron como respaldo del proceso de transformacion de los valores de origen. La normalización se realizó en una columna independiente para evitar modificar directamente los datos originales.

Las celdas con ausencia de valoracion se dejaron null.

La columnas [lowest_price] [median_price] [highest_price] estan expresadas como texto anteponiendo un signo monetario al numero con decimales y donde faltan valores figura "-—", en la transformacion se elimino el sígno de  "$"  y converti el separador decimal a "," en todos los casos, luego devolvi el formato de la celda a moneda con signo de "$". Los valores  "--"  deben quedar como celdas null, porque no representan un precio y la ausencia de información no debe confundirse con un valor numérico igual a cero..

La función  SI  permite devolver un valor u otro según una condición; aquí se utiliza para tratar  "—"  y las celdas vacías como ausencia de precio.

=SI(O(T2="--";T2="");"";VALOR(SUSTITUIR(SUSTITUIR(T2;"$";"");".";",")))

Con esta fórmula realizamos estas operaciones:
•	Si el valor es "--"  o está vacío, devuelve una celda vacía.
•	Si contiene un precio, elimina el símbolo "$" .
•	Reemplaza el punto decimal por ",".
•	Convierte el resultado en número mediante  VALOR . 

Tratamiento de estilos musicales y creación del catálogo de consulta
La columna  styles_clean  contenía uno o varios estilos musicales por lanzamiento, separados por comas. Para facilitar las consultas por estilo individual, se construyó un catálogo único mediante fórmulas de Excel en hojas auxiliares.

Este procedimiento conservó la columna original y mantuvo una fila por lanzamiento en la tabla principal, evitando multiplicar los registros por cada estilo asociado.

1. Extracción de las combinaciones
Se creó la hoja  Styles_catalog , con el encabezado  styles  en  A1 . En  A2  se introdujo una referencia estructurada a la columna de origen:
=discogs_electronic[styles_clean]

Esta fórmula trasladó las combinaciones de estilos a la hoja auxiliar, manteniendo su vinculación con la tabla principal.

2. Separación y normalización de los estilos
En  B2  se introdujo la siguiente fórmula y se extendió hasta la última fila con datos:

=SI(A2="";"";ESPACIOS(DIVIDIRTEXTO(A2;",")))

La fórmula dejó en blanco las filas sin información, separó las etiquetas utilizando la coma como delimitador y eliminó espacios sobrantes mediante  ESPACIOS .

Los estilos de cada lanzamiento se distribuyeron horizontalmente en columnas independientes:

[House,Tech House,Trance,Deep House]:	[House]	[Tech House]	[Trance]	[Deep House]

### Construcción del catálogo único de estilos

En la hoja `Styles_list` se generó un catálogo único de estilos musicales
a partir del rango `B2:AE29972` de la hoja `Styles_catalog`, donde los
estilos de cada lanzamiento ya se encontraban separados en distintas
columnas.

Para ello se utilizó la siguiente fórmula:

=LET(styles;ENCOL(Styles_catalog!B2:AE29972;3);ORDENAR(UNICOS(FILTRAR(styles;styles<>""))))
Genere una hoja nueva llamada Styles_list y construi una lista única y ordenada de los estilos que ya están distribuidos en las columnas de  [Styles_catalog]. No cuenta lanzamientos ni separa por sí misma los textos con comas: consolida los estilos previamente separados.

## Nueva columna: [style_primary]

### Objetivo

Crear una categoría de estilo principal para poder filtrar el dashboard por un único estilo electrónico. La columna original [styles_clean] puede contener varios estilos separados por comas, por lo que no es adecuada como segmentador directo.

### Regla de transformación

La columna [style_primary] conserva únicamente el primer estilo que aparece en [styles_clean], antes de la primera coma.

Fórmula aplicada en la primera fila de datos:

=SI.ERROR(IZQUIERDA(I2;ENCONTRAR(",";I2)-1);I2)


### Recuento de lanzamientos por estilo

En la hoja `Analytics` se construyó una tabla resumen a partir del catálogo de estilos individuales.

Mediante una fórmula se contabilizaron los registros de [styles_clean], en la hoja `Discogs_electronic_processed_analytics_dashboard`, que contienen cada estilo.
La búsqueda se realizó por etiqueta completa para evitar coincidencias parciales entre estilos como House, Deep House y Tech House.

Un mismo lanzamiento puede contabilizarse en varios estilos. Por tanto, la suma de los recuentos por estilo puede superar el número total de lanzamientos analizados.

El procedimiento consistió en:

1.	Consolidar los estilos distribuidos en varias columnas en una sola lista mediante  ENCOL , omitiendo celdas vacías y errores.
2.	Asignar el nombre temporal  styles  a esa lista mediante  LET , facilitando su reutilización dentro de la fórmula.
3.	Excluir los valores equivalentes a una cadena vacía mediante  FILTRAR .
4.	Obtener una sola aparición de cada estilo mediante  UNICOS .
5.	Ordenar alfabéticamente el resultado mediante  ORDENAR .

El resultado es un catálogo de estilos individuales, sin repeticiones, que sirve como base para las consultas y los recuentos por estilo utilizados en el análisis y el dashboard.

Este procedimiento no modifica la tabla principal ni multiplica sus registros. La asociación entre cada lanzamiento y sus estilos permanece en [styles_clean].

El catálogo no establece por sí mismo una relación automática con los lanzamientos ni con los segmentadores del dashboard; esa asociación se resuelve mediante las fórmulas de consulta y recuento correspondientes.

Se identificaron 307 estilos musicales distintos y 63.983 asociaciones entre lanzamientos y estilos.

Un mismo lanzamiento puede pertenecer a varios estilos, por lo que la suma de los recuentos por estilo supera el número total de lanzamientos.

La media resultante es de aproximadamente 2,14 estilos por lanzamiento.

### Identificadores de registro

En la hoja Discogs_electronic_cleaning del archivo 02_discogs_electronic_data_cleaning.xlsx se creo una nueva etiqueta llamada [release_display] a falta de un identificador de registro 

Para esto se utilizo la formula:

=A2&" — "&B2&" | "&C2&" | "&SI(E2<>"";E2;F2)&" | "&TEXTO(J2;"aaaa")&" | “&K2&" | fila "&FILA()

La etiqueta muestra artista, título, sello, país o región, formato y año. El sufijo de fila evita que dos registros con esos mismos atributos se fusionen en la tabla dinámica. Es una identificación de trabajo, no un identificador permanente de Discogs. 

## Creacion de nueva columna: `votes_threshold`
En la hoja `Discogs_electronic_processed`genere la columna `votes_threshold` utilizando en origen `num_ratings` con el objetivo de crear una categoría por intervalos de número de valoraciones para filtrar el Top 10 de lanzamientos mejor valorados. Los intervalos son excluyentes, no umbrales acumulativos: seleccionar `100–199` no equivale a seleccionar todos los lanzamientos con 100 votos o más; `500+` sí corresponde al intervalo abierto de 500 votos o más. La finalidad es distinguir valoraciones respaldadas por distintos niveles de evidencia comunitaria.

### Regla de transformación

La columna `votes_threshold` agrupa los valores de `num_ratings` en intervalos de 100 valoraciones:

| Categoría | Regla |
|---|---|
| `0–99` | Menos de 100 valoraciones |
| `100–199` | 100 a 199 valoraciones |
| `200–299` | 200 a 299 valoraciones |
| `300–399` | 300 a 399 valoraciones |
| `400–499` | 400 a 499 valoraciones |
| `500+` | 500 valoraciones o más |

La fórmula se aplicó en la primera fila de datos de la columna `votes_threshold`, tomando como referencia la celda `M2`, correspondiente a la primera fila de datos de `num_ratings`:

=SI(M2>=500;"500+";SI(M2>=400;"400–499";SI(M2>=300;"300–399";SI(M2>=200;"200–299";SI(M2>=100;"100–199";"0–99")))))

## Preparación de hojas auxiliares para el análisis de relaciones

### 1. Objetivo

Para responder a la pregunta «¿Qué relación existe entre colección, demanda, valoraciones y precios?», se crearon cinco hojas auxiliares a partir de `Discogs_electronic_processed`:

- `Want_price`
- `Have_price`
- `Rating_want`
- `Rating_have`
- `Rating_price`

Estas hojas permiten preparar pares de observaciones válidas, calcular correlaciones de Pearson y construir gráficos de dispersión sin modificar el conjunto de datos procesado.

La separación por cruces facilita la trazabilidad del análisis: cada hoja conserva únicamente las variables y los registros necesarios para estudiar una relación concreta.

### 2. Fuente de datos y unidad de análisis

Se utilizaron las siguientes columnas:

| Columna | Variable | Uso |
|---|---|---|
| J | `have` | Presencia del lanzamiento en colecciones |
| K | `want` | Presencia del lanzamiento en listas de deseos |
| L | `num_ratings` | Número de valoraciones registradas |
| M | `average_rating_clean` | Valoración media depurada |
| O | `median_price_clean` | Precio mediano depurado |

La unidad de análisis es cada registro de lanzamiento del dataset.

No se agruparon distintas ediciones de una obra por artista o título.

Los indicadores de colección, demanda, valoración y precio corresponden al momento de recopilación de los datos. El periodo 1990–2000 se refiere al año de publicación de los lanzamientos, no al momento de actividad de los usuarios.

### 3. Criterios de inclusión

Se aplicó una selección de registros válidos específica para cada cruce.

| Hoja | Variable X | Variable Y | Criterio de inclusión |
|---|---|---|---|
| `Want_price` | `want` | `median_price_clean` | Ambas variables numéricas |
| `Have_price` | `have` | `median_price_clean` | Ambas variables numéricas |
| `Rating_want` | `average_rating_clean` | `want` | Ambas numéricas y `num_ratings > 0` |
| `Rating_have` | `average_rating_clean` | `have` | Ambas numéricas y `num_ratings > 0` |
| `Rating_price` | `average_rating_clean` | `median_price_clean` | Ambas numéricas y `num_ratings > 0` |

Los valores ausentes no se sustituyeron por cero. Los registros que no cumplieron los criterios se excluyeron únicamente del cruce correspondiente y se conservaron en la hoja procesada.

El criterio numérico conserva los ceros existentes. Por tanto, esta selección no equivale a exigir valores estrictamente positivos en las variables analizadas.

En los cruces con valoración se exigió al menos un voto para evitar tratar los lanzamientos sin valoraciones como si dispusieran de una puntuación válida.

### 4. Lógica de implementación

Cada hoja auxiliar se organizó en dos columnas:

- Columna A: variable representada en el eje X.
- Columna B: variable representada en el eje Y.

La extracción se realizó mediante fórmulas con:

- `LET`, para definir los rangos y la condición de selección.
- `ESNUMERO`, para comprobar que las variables fueran numéricas.
- `FILTRAR`, para devolver los registros que cumplieran la condición.

Se aplicó exactamente la misma condición a las dos columnas de cada hoja. De este modo, la fila de salida conserva los valores correspondientes a un mismo lanzamiento.

No se filtró ni se ordenó cada variable de forma independiente, ya que esto rompería el emparejamiento necesario para el análisis.

#### Ejemplo: hoja `Want_price`

En A2 se extrajeron los valores válidos de demanda:

=LET(
demanda;Discogs_electronic_processed!K2:K29927;
precio;Discogs_electronic_processed!O2:O29927;
validos;ESNUMERO(demanda)*ESNUMERO(precio);
FILTRAR(demanda;validos)
)

En B2 se utilizó la misma condición para extraer los precios:

=LET(
demanda;Discogs_electronic_processed!K2:K29927;
precio;Discogs_electronic_processed!O2:O29927;
validos;ESNUMERO(demanda)*ESNUMERO(precio);
FILTRAR(precio;validos)
)

Para `Have_price` se sustituyó el rango de `want` por el de `have`,
manteniendo el mismo procedimiento.

#### Ejemplo: hoja `Rating_price`

En los cruces con valoración se añadió la condición `num_ratings > 0`.

La fórmula de A2 fue:

=LET(
valoracion;Discogs_electronic_processed!M2:M29927;
precio;Discogs_electronic_processed!O2:O29927;
votos;Discogs_electronic_processed!L2:L29927;
validos;ESNUMERO(valoracion)*ESNUMERO(precio)*(votos>0);
FILTRAR(valoracion;validos)
)

La fórmula de B2 mantuvo las mismas definiciones y condiciones,
cambiando únicamente la expresión final por:

FILTRAR(precio;validos)

En `Rating_want` y `Rating_have` se aplicó esta misma lógica,
sustituyendo el precio por la demanda o la colección, respectivamente.

### 5. Matrices dinámicas y recuento de observaciones

Las fórmulas generan matrices dinámicas desde A2 y B2.
Las referencias `A2#` y `B2#` abarcan los resultados completos devueltos por cada fórmula.

El número de observaciones incluidas se obtuvo mediante:

=FILAS(A2#)

Como control de emparejamiento, las dos columnas de una misma hoja deben contener el mismo número de filas.

Los rangos de origen utilizados son fijos y llegan hasta la fila 29927.

### 6. Cálculo de las correlaciones

Los coeficientes se calcularon con `COEF.DE.CORREL` sobre las columnas
filtradas de cada hoja:

=COEF.DE.CORREL(Want_price!A2#;Want_price!B2#)

=COEF.DE.CORREL(Have_price!A2#;Have_price!B2#)

=COEF.DE.CORREL(Rating_want!A2#;Rating_want!B2#)

=COEF.DE.CORREL(Rating_have!A2#;Rating_have!B2#)

=COEF.DE.CORREL(Rating_price!A2#;Rating_price!B2#)

Los resultados se presentaron con tres decimales y se registraronjunto con el número de pares válidos de cada cruce.

### 7. Bases analíticas y resultados obtenidos

| Hoja | Pares válidos | Registros excluidos del cruce | Pearson |
|---|---:|---:|---:|
| `Want_price` | 29.414 | 512 | 0,600 |
| `Have_price` | 29.414 | 512 | 0,130 |
| `Rating_want` | 29.192 | 734 | 0,276 |
| `Rating_have` | 29.132 | 794 | 0,174 |
| `Rating_price` | 28.903 | 1.023 | 0,271 |

Las exclusiones se calculan respecto a los 29.926 registros originales.

Estas cantidades no deben sumarse entre hojas: un mismo lanzamiento puede quedar excluido de varios cruces.

Las diferencias entre bases analíticas son compatibles con la aplicación de criterios específicos a distintas variables. Sin una revisión registro a registro, no se atribuyen todas las exclusiones únicamente a valores nulos: también pueden intervenir valores no numéricos o la condición sobre el número de votos.

Asimismo, que dos hojas tengan el mismo número de observaciones no demuestra que contengan exactamente los mismos registros.

### 8. Visualización de las relaciones

Se construyó un gráfico de dispersión para cada hoja auxiliar, utilizando los mismos pares empleados en el cálculo de correlación.

| Hoja | Eje X | Eje Y | Título del gráfico |
|---|---|---|---|
| `Want_price` | Want | Median Price | Demand vs Median Price |
| `Have_price` | Have | Median Price | Collection vs Median Price |
| `Rating_want` | Average Rating | Want | Average Rating vs Demand |
| `Rating_have` | Average Rating | Have | Average Rating vs Collection |
| `Rating_price` | Average Rating | Median Price | Average Rating vs Median Price |

Cada punto representa un registro de lanzamiento.

Se conservaron los outliers en esta fase exploratoria y no se aplicaron transformaciones logarítmicas a las variables.
Los gráficos complementan al coeficiente y permiten examinar la dispersión y la presencia de observaciones alejadas del resto.

### 9. Síntesis analítica

El cruce entre demanda y precio mediano presentó la mayor correlación de estas cinco hojas, con un coeficiente de 0,600. Este resultado respalda la existencia de una asociación lineal positiva entre el interés por obtener un lanzamiento y su precio mediano.

La relación entre presencia en colecciones y precio fue mucho menor, con un coeficiente de 0,130. Por tanto, los lanzamientos más coleccionados no son necesariamente los más caros.

La valoración media presentó asociaciones positivas débiles con:

- La demanda: 0,276.
- La presencia en colecciones: 0,174.
- El precio mediano: 0,271.

En conjunto, los resultados muestran que colección, demanda, valoración y precio describen dimensiones relacionadas, pero distintas, del comportamiento observado en la muestra.

### 10. Limitaciones

- La correlación de Pearson resume asociaciones lineales y no demuestra causalidad.
- Una correlación débil no descarta relaciones no lineales.
- Los valores extremos pueden influir en los coeficientes.
- Cada cruce utiliza su propia base de registros válidos; no se impuso una muestra común para todas las comparaciones.
- Las diferencias entre coeficientes se interpretan descriptivamente; no se realizó una prueba formal para compararlos.
- En los análisis con valoración, cada lanzamiento recibe el mismo peso, independientemente de su número de votos.
- Exigir `num_ratings > 0` no garantiza que todas las valoraciones medias tengan el mismo respaldo.
- La selección numérica no valida por sí sola la moneda, la procedencia ni la plausibilidad de los precios.
- Los resultados se limitan al dataset analizado y no representan necesariamente la totalidad del mercado de música electrónica.

## `Style_price`: análisis del precio mediano por estilo

Se incorporó la hoja auxiliar `Style_price` con el objetivo de responder a la pregunta:

> ¿Qué estilos presentan los precios medianos más elevados?

La hoja permite calcular, para cada etiqueta de estilo:

- El número de lanzamientos con precio numérico.
- La mediana de sus precios medianos por lanzamiento.
- Su posición en un ranking de estilos que cumplen un mínimo de observaciones.

Este análisis complementa el ranking de estilos por volumen de lanzamientos: mide precios, no producción.

## Fuente de datos

Los cálculos utilizan la hoja `Discogs_electronic_processed`, que contiene 29.926 registros, sin incluir el encabezado.

| Columna de origen | Variable | Rango utilizado |
|---|---|---|
| I | `styles_clean` | `I2:I29927` |
| O | `median_price_clean` | `O2:O29927` |

La lista de estilos individuales se tomó del catálogo previamente preparado en `Styles_list`.

Los rangos de origen son fijos. Si se incorporan registros después de la fila 29927, será necesario actualizar las referencias.

### Estructura de la hoja

La hoja se organizó en dos bloques:

| Columna | Encabezado | Contenido |
|---|---|---|
| A | `style` | Catálogo de estilos individuales |
| B | `releases_with_price` | Cantidad de lanzamientos del estilo con precio numérico |
| C | `median_release_price` | Mediana de los precios medianos de esos lanzamientos |
| E | `Style` | Estilos seleccionados y ordenados para el ranking |
| F | `Releases with price` | Recuento correspondiente a cada estilo del ranking |
| G | `Median release price` | Mediana correspondiente a cada estilo del ranking |

La columna D se dejó como separación visual.

El bloque A:C conserva el resumen completo. El bloque E:G contiene una selección de hasta 100 estilos, ordenada por precio mediano descendente.

Los bloques se mantuvieron como rangos normales, sin convertirlos en tablas de Excel, para permitir el uso de fórmulas con resultados desbordados.

### Identificación de estilos dentro de cada lanzamiento

Un lanzamiento puede contener varias etiquetas en `styles_clean`.

Para identificar un estilo se buscaron coincidencias delimitadas por comas, en lugar de coincidencias parciales de texto.

La expresión utilizada fue:

ESNUMERO(HALLAR(","&A2&",";","&estilos&","))

Por ejemplo, la búsqueda de `,House,` no coincide con `,Deep House,`.

Esta lógica presupone que las etiquetas están separadas por comas y que no existen espacios adicionales junto al separador. Su funcionamiento depende de mantener la normalización aplicada a `styles_clean`.

Cada lanzamiento puede participar en varios grupos si contiene varios estilos. Por tanto, los recuentos por estilo no son categorías excluyentes y no deben sumarse para obtener el total de lanzamientos del dataset.

### Recuento de lanzamientos con precio numérico

En B2 se utilizó:

=LET(
estilos;Discogs_electronic_processed!I2:I29927;
precios;Discogs_electronic_processed!O2:O29927;
coincide;ESNUMERO(HALLAR(","&A2&",";","&estilos&","));
SUMAPRODUCTO(--coincide;--ESNUMERO(precios))
)

La fórmula cuenta los registros que cumplen simultáneamente dos condiciones:

1. El lanzamiento contiene el estilo indicado en A2.
2. `median_price_clean` contiene un valor numérico.

Se copió la fórmula hasta el último estilo del catálogo.

Los valores ausentes y los precios almacenados como texto no se incluyeron en el recuento. No se sustituyeron por cero.

El criterio `ESNUMERO` conserva los ceros numéricos existentes: no equivale a exigir precios estrictamente positivos.

### 6. Cálculo del precio mediano por estilo

En C2 se utilizó:

=SI(B2=0;"";LET(
estilos;Discogs_electronic_processed!I2:I29927;
precios;Discogs_electronic_processed!O2:O29927;
coincide;ESNUMERO(HALLAR(","&A2&",";","&estilos&","));
MEDIANA(FILTRAR(precios;coincide*ESNUMERO(precios)))
))

La fórmula:

1. Comprueba si el estilo tiene registros con precio numérico.
2. Filtra los precios de los lanzamientos asociados al estilo.
3. Calcula la mediana de los valores seleccionados.
4. Devuelve una celda visualmente vacía si no hay observaciones válidas.

Se copió hasta el último estilo del catálogo.

El indicador resultante es la mediana de `median_price_clean` entre lanzamientos. No es una media aritmética ni la mediana de todas las transacciones individuales de Discogs.

Cada registro de lanzamiento aporta un valor al cálculo, sin ponderación por número de ventas, usuarios o valoraciones.

### Criterio de inclusión en el ranking

El resumen A:C conserva todos los estilos, incluidos aquellos sin precio numérico o con pocas observaciones.

Para el ranking E:G se exigió:

- Una etiqueta de estilo no vacía.
- Al menos 30 lanzamientos con precio numérico.
- Una mediana numérica.

El mínimo de 30 registros se adoptó como criterio práctico para evitar que grupos con muy pocas observaciones dominaran la clasificación principal.

Este umbral no constituye una garantía estadística de representatividad. Los estilos que no lo cumplen no se eliminan del dataset ni del resumen completo; únicamente quedan fuera del ranking seleccionado.

### Generación del ranking dinámico

El ranking se planteó inicialmente con diez estilos y posteriormente se amplió a un máximo de 100.

En E2 se utilizó:

=LET(
estilos;$A$2:$A$1000;
recuentos;$B$2:$B$1000;
precios;$C$2:$C$1000;
validos;(estilos<>"")*(recuentos>=30)*ESNUMERO(precios);
lista;FILTRAR(estilos;validos);
medianas;FILTRAR(precios;validos);
ordenados;ORDENARPOR(lista;medianas;-1;lista;1);
INDICE(ordenados;SECUENCIA(MIN(100;FILAS(ordenados))))
)


La fórmula aplica el siguiente procedimiento:

1. Filtra los estilos que cumplen los criterios.
2. Los ordena por precio mediano descendente.
3. En caso de igualdad exacta en la mediana, utiliza el nombre del estilo en orden alfabético.
4. Devuelve hasta 100 estilos.

La expresión:

MIN(100;FILAS(ordenados))

limita la salida al número de estilos disponibles cuando menos de 100 cumplen el criterio.

La fórmula presupone que existe al menos un estilo elegible, condición que se cumple en el dataset analizado.

La selección utiliza los valores originales de las celdas, no los valores redondeados que se muestran en pantalla. Dos medianas visualmente iguales a dos decimales pueden tener un orden diferente si su precisión interna difiere.

### Recuperación de los valores asociados

En F2 se recuperó el número de lanzamientos con precio:

=BUSCARX(E2#;$A$2:$A$1000;$B$2:$B$1000;"";0)

En G2 se recuperó la mediana del precio:

=BUSCARX(E2#;$A$2:$A$1000;$C$2:$C$1000;"";0)

Las fórmulas utilizan coincidencia exacta y toman como referencia la lista desbordada desde E2.

De esta manera, los estilos, sus recuentos y sus medianas permanecen alineados según el orden del ranking.

Las fórmulas se escriben únicamente en E2, F2 y G2. Las celdas situadas debajo deben permanecer libres para permitir la expansión de los resultados.

Los rangos de consulta llegan hasta la fila 1000. Si el catálogo supera ese límite, deberán ampliarse las referencias de las tres fórmulas.

### Controles de consistencia

Se establecieron los siguientes controles para revisar el resultado:

- Cada estilo del ranking debe tener al menos 30 registros con precio.
- Las medianas deben aparecer ordenadas de mayor a menor.
- Los recuentos y las medianas de F:G deben coincidir con los valores del mismo estilo en A:C.
- Las tres columnas del ranking deben tener la misma cantidad de filas.
- El catálogo de A debe contener una sola entrada por estilo.
- Los resultados no deben contener errores de desbordamiento ni de referencia.

La cantidad de estilos incluidos puede consultarse con:

=FILAS(E2#)

También pueden comprobarse las longitudes de las columnas asociadas:

=FILAS(F2#)

=FILAS(G2#)

Los tres resultados deben coincidir.

### Gráfico de precios por estilo

Se construyó un gráfico de barras horizontales con los diez primeros estilos del ranking.

| Elemento | Configuración |
|---|---|
| Categorías | `E2:E11` |
| Valores | `G2:G11` |
| Tipo | Barras agrupadas 2D |
| Título | `Top 10 Styles by Median Release Price` |
| Orden visual | Precio mediano más elevado en la parte superior |
| Etiquetas | Precio con dos decimales |

La columna F se conserva como información de apoyo y no se representa como una segunda serie de barras.

El ranking auxiliar contiene hasta 100 estilos, mientras que el gráfico muestra únicamente los diez primeros.

Se añadió la siguiente nota metodológica:

> Solo se incluyen estilos con al menos 30 lanzamientos con precio numérico. Cada valor corresponde a la mediana de los precios medianos de los lanzamientos asociados al estilo. Un lanzamiento puede pertenecer a varios estilos.

Se mantuvo el formato monetario existente sin atribuir una moneda específica mientras no se confirme la unidad del campo de origen.

### Alcance y limitaciones

- El análisis describe diferencias de precio entre estilos dentro del dataset.
- No mide la evolución histórica de los precios ni demuestra revalorización.
- El periodo 1990–2000 corresponde a los años de publicación de los lanzamientos, no necesariamente al momento de observación de sus precios.
- Las etiquetas de estilo se solapan y los grupos tienen tamaños distintos.
- Una diferencia entre medianas no demuestra que el estilo sea la causa del precio.
- La selección numérica no verifica por sí sola la moneda, la plausibilidad ni la comparabilidad de los precios.
- No se aplicó una exclusión adicional de valores extremos en este procedimiento.
- Las fórmulas recalculan los resultados dentro de los rangos definidos; no incorporan automáticamente registros situados fuera de ellos.

## Evolución anual de estilos: tabla cruzada en `Analytics`

Se incorporó a la hoja `Analytics` una tabla cruzada con el objetivo de analizar cómo cambió la presencia de cinco estilos seleccionados entre 1990 y 2000:

- House.
- Deep House.
- Garage House.
- Techno.
- Progressive House.

La selección corresponde a los estilos mencionados en una de las hipótesis iniciales del proyecto.

El objetivo es comparar su peso relativo dentro de los lanzamientos de cada año, diferenciando los cambios de composición de las variaciones en el volumen total de publicaciones.

### Ubicación y organización

La lógica se preparó inicialmente en una hoja denominada `Styles_evolution`.

Posteriormente, se trasladaron la tabla y sus fórmulas a `Analytics` y se eliminó la hoja independiente. Esta reorganización centraliza los análisis y reduce la cantidad de hojas del libro.

La tabla de apoyo para el análisis porcentual se construyó mediante fórmulas; no es una tabla dinámica de Excel. Este bloque analítico debe distinguirse del gráfico dinámico final «Selected styles by year», cuya respuesta al segmentador YEAR se comprobó posteriormente. La descripción de porcentajes de esta sección corresponde al análisis auxiliar y no acredita por sí sola la métrica ni el origen exacto de las series del gráfico final.

Su estructura lógica es:

| Campo | Contenido |
|---|---|
| `year` | Año de publicación, de 1990 a 2000 |
| `total_releases` | Total de lanzamientos del año |
| `House` | Proporción anual de lanzamientos con esta etiqueta |
| `Deep House` | Proporción anual de lanzamientos con esta etiqueta |
| `Garage House` | Proporción anual de lanzamientos con esta etiqueta |
| `Techno` | Proporción anual de lanzamientos con esta etiqueta |
| `Progressive House` | Proporción anual de lanzamientos con esta etiqueta |

Las coordenadas utilizadas en las fórmulas de esta documentación son ilustrativas y corresponden a la distribución inicial:

- A1:G1: encabezados.
- A2:A12: años.
- B2:B12: totales anuales.
- C2:G12: proporciones por estilo.

En `Analytics`, las referencias a años, totales y encabezados corresponden a la ubicación efectiva del bloque.

### Fuente de datos

Se utilizó la hoja `Discogs_electronic_processed`, con 29.926 registros y encabezados en la fila 1.

| Columna | Variable | Rango utilizado |
|---|---|---|
| G | `release_year` | `G2:G29927` |
| I | `styles_clean` | `I2:I29927` |

No se aplicaron filtros de precio, colección, demanda o valoración. El análisis utiliza todos los lanzamientos comprendidos en cada año.

Los rangos de origen son fijos. Si el dataset aumenta después de la fila 29927, deberán actualizarse las fórmulas.

### Tratamiento del año de publicación

Durante la implementación se comprobó que `release_year` contiene fechas de Excel, aunque las celdas muestran únicamente el año mediante su formato.

Por este motivo, no se comparó directamente el contenido de la columna G con números como `1990`.

Los registros de cada año se identificaron mediante dos límites:

- Fecha igual o posterior al 1 de enero del año analizado.
- Fecha anterior al 1 de enero del año siguiente.

La columna `year` de la tabla de análisis contiene años escritos como números enteros, no fechas completas.

No se modificó la columna de origen.

### Cálculo del total anual de lanzamientos

Con el año situado en A2, la fórmula de referencia para `total_releases` es:

=CONTAR.SI.CONJUNTO(
Discogs_electronic_processed!$G$2:$G$29927;">="&FECHA($A2;1;1);
Discogs_electronic_processed!$G$2:$G$29927;"<"&FECHA($A2+1;1;1)
)

Se replicó el cálculo para los once años comprendidos entre 1990 y 2000.

La utilización de un límite superior exclusivo permite incluir todas las fechas del año sin depender de que los registros estén almacenados específicamente como el 1 de enero.

Como comprobación inicial, el recuento de 1990 devolvió 1.757 lanzamientos, coincidiendo con la tabla dinámica anual ya utilizada en el proyecto.

### Identificación de etiquetas de estilo

`styles_clean` puede contener varias etiquetas separadas por ",".

Para identificar un estilo se utilizó una búsqueda delimitada:

ESNUMERO(HALLAR(","&C$1&",";","&estilos&","))

La incorporación de "," al inicio y al final permite buscar etiquetas completas.

Por ejemplo:

- `House` se identifica como una etiqueta independiente.
- La búsqueda de `House` no cuenta automáticamente `Deep House` ni `Progressive House`.
- Si un lanzamiento contiene simultáneamente `House` y `Deep House`, participa en ambos grupos.

Esta lógica presupone que la separación por comas está normalizada y no presenta espacios adicionales junto a los delimitadores.

Los encabezados de la tabla deben coincidir con las etiquetas del catálogo.

### Cálculo de la presencia anual por estilo

El indicador utilizado es:

Presencia anual del estilo =
lanzamientos del año que incluyen el estilo /
total de lanzamientos del año.

La fórmula de referencia, situada inicialmente en C2, es:

=LET(
fechas;Discogs_electronic_processed!$G$2:$G$29927;
estilos;Discogs_electronic_processed!$I$2:$I$29927;
coincide;ESNUMERO(HALLAR(","&C$1&",";","&estilos&","));
desde;FECHA($A2;1;1);
hasta;FECHA($A2+1;1;1);
SI($B2=0;"";SUMAPRODUCTO(
--(fechas>=desde);
--(fechas<hasta);
--coincide
)/$B2)
)

La fórmula:

1. Define los rangos de fechas y estilos.
2. Identifica la etiqueta indicada en el encabezado.
3. Selecciona los registros del año de la fila.
4. Cuenta los lanzamientos que cumplen ambas condiciones.
5. Divide el recuento entre el total anual.
6. Devuelve una celda visualmente vacía si el denominador es cero.

El cálculo se replicó hacia la derecha para los cinco estilos y hacia abajo para los once años.

Los resultados se almacenan como proporciones y se muestran mediante formato de porcentaje. No se multiplican adicionalmente por 100.

### Denominador y solapamiento de categorías

El denominador de cada porcentaje es el total de lanzamientos del año, no la suma de apariciones de los cinco estilos.

Por tanto:

- Un lanzamiento puede contribuir al numerador de varios estilos.
- Los porcentajes de una fila no tienen que sumar 100 %.
- No se calcula el reparto exclusivo entre los cinco estilos.
- Los registros sin coincidencia con esos estilos permanecen incluidos en el denominador anual.

El indicador mide la presencia de cada etiqueta en el conjunto anual de lanzamientos.

### Visualización del análisis porcentual y distinción respecto al dashboard

La configuración siguiente documenta la visualización del análisis porcentual. No debe atribuirse automáticamente al gráfico dinámico final, que se mantuvo para conservar la interactividad con YEAR.

Para comparar las trayectorias se definió un gráfico de líneas no apiladas, con una serie por estilo.

| Elemento | Configuración |
|---|---|
| Título | `Selected Electronic Styles by Year (1990–2000)` |
| Eje horizontal | Años de 1990 a 2000 |
| Eje vertical | Porcentaje del total anual de lanzamientos |
| Series | House, Deep House, Garage House, Techno y Progressive House |
| Tipo | Líneas con marcadores, no apiladas |
| Tabla de apoyo | Porcentajes con dos decimales |

La columna `total_releases` no se incluye como serie, ya que contiene recuentos y utiliza una unidad distinta.

No se utiliza un gráfico apilado al 100 %, porque los estilos son categorías solapadas.

Nota metodológica:

> Porcentaje del total de lanzamientos de cada año que incluye cada estilo seleccionado. Las etiquetas pueden solaparse; los porcentajes no suman necesariamente 100 %.

### Alcance y limitaciones

- El análisis describe los lanzamientos incluidos en el dataset, no ventas, ingresos ni audiencia.
- Una pérdida de participación porcentual no implica necesariamente una disminución del número absoluto de lanzamientos.
- La selección de cinco estilos responde a la hipótesis inicial y no representa toda la diversidad estilística del dataset.
- Los resultados no permiten afirmar por sí solos que aumentó o disminuyó la diversidad del mercado.
- Las etiquetas se analizan de forma independiente, sin agrupar automáticamente subgéneros dentro de una categoría principal.
- Las variaciones observadas son descriptivas y no identifican sus causas.
- La centralización en `Analytics` cambia la organización del libro, pero no el criterio de cálculo.

## Funciones de control en hoja Analytics

En la hoja Analytics tenemos varias funciones de control e informacion de datos Unique Artists hace un control de valores unicos para toda la columna artistas =FILAS(UNICOS(discogs_electronic_processed[artist]))

Missing Data Check hace un control de valores vacios para todas las columnas =CONTAR.BLANCO(discogs_electronic_processed[artist])

## Respuestas a preguntas planteadas

1. ¿Cómo evolucionó el número de lanzamientos entre 1990 y 2000?

Observamos que los lanzamientos aumentan, disminuyen o fluctúan entre 1990 y 1994, e identificamos a 1996 como el año máximo de todo el periodo.
La conclusión se refiere a los lanzamientos presentes en la muestra, no a la totalidad de la producción electrónica mundial. Además, un aumento entre el primer y el último año no implica necesariamente un crecimiento continuo: el gráfico permite distinguir ambas situaciones.

2. ¿Qué estilos y subgéneros concentraron más lanzamientos discograficos?

House fue el estilo con mayor presencia en la muestra, con 11.838 lanzamientos asociados, seguido de Techno, con 9.536. Ambos se sitúan claramente por encima del resto de estilos: Progressive House ocupa el tercer puesto con 4.414 lanzamientos, seguido de Tech House, con 3.754, y Electro, con 3.678.

El ranking también muestra una presencia destacada de Ambient y Trance, con 2.494 y 2.133 lanzamientos, respectivamente.

La hipótesis inicial queda parcialmente respaldada. House, Techno, Progressive House y Deep House figuran entre los diez estilos con más lanzamientos, mientras que Garage House se sitúa en la posición 13.

Además, Tech House y Electro presentan una frecuencia superior a Deep House y Garage House.

Estos resultados describen la presencia de cada estilo en la muestra analizada, no su cuota de ventas ni su participación en la totalidad de la producción electrónica del periodo.

Un mismo lanzamiento puede estar asociado a varios estilos. Por tanto, los recuentos no son excluyentes y no deben sumarse como si representaran lanzamientos diferentes.

3. ¿Qué sellos discográficos fueron más prolíficos?.

Virgin encabeza el ranking de la muestra con 315 lanzamientos, seguido de Epic, con 263, y Columbia, con 245. Entre los sellos planteados en la hipótesis inicial, FFRR y Strictly Rhythm presentan una presencia destacada, con 185 y 179 lanzamientos, respectivamente. Deconstruction registra 115 y ocupa la posición 15 de la clasificación original.

Los resultados respaldan parcialmente la hipótesis: algunos de los sellos previstos aparecen entre los más frecuentes, pero ninguno ocupa las primeras posiciones. El ranking describe el número de registros asociados a cada etiqueta de sello en la muestra, no sus ventas, influencia ni producción total durante el periodo.

Se excluye del ranking la categoría «Not On Label», en Discogs, no representa un sello discográfico único, es una categoría llamada meta-label para registrar lanzamientos sin un sello identificable.

Los registros se conservan en el conjunto de datos.

4. ¿Qué países concentraron mayor actividad editorial?

El análisis por países incluye 27.645 registros con país identificado. Se excluyen del ranking 1.012 registros clasificados como «Unknown» y 1.270 sin país individual en  [country_clean], cuya información geográfica se encuentra en [market_zones]. Todos los registros se conservan en el dataset.

Reino Unido [UK] encabeza el ranking con 9.775 lanzamientos, seguido de Estados Unidos con 6.755, Alemania con 3.637 e Italia con 2.606. Países Bajos ocupa la quinta posición, con 1.190 registros.

Los resultados respaldan la hipótesis de una presencia destacada de Reino Unido, Estados Unidos, Alemania, Italia, Países Bajos y Francia, ya que todos figuran entre los siete primeros países de la muestra. Bélgica también presenta una participación relevante, situándose por delante de Francia.

Estos resultados describen la distribución geográfica de los lanzamientos incluidos en el dataset. No representan necesariamente el país de origen de los artistas ni la totalidad de la producción electrónica del periodo. Se excluyen de este ranking las categorías «Unknown» y los registros clasificados únicamente por zona de mercado (null).

5. ¿Qué formato físico predominó y cómo evolucionó?

El vinilo fue el formato predominante entre los lanzamientos de la muestra, con 26.940 registros, aproximadamente el 90,02%, seguido del CD, con 2.957 registros el 9,88%. Las demás categorías tuvieron una presencia residual. 

El CD pasa de 96 lanzamientos en 1990 a 420 en 2000. Su máximo se registra en 1999, con 453. También tiene fluctuaciones: por ejemplo, baja de 293 en 1995 a 290 en 1996.

El CD gana participación: pasa de aproximadamente el 5,5% del total anual en 1990 al 13,2% en 2000, con un máximo cercano al 15,5% en 1999. Aun así, no desplaza al vinilo como formato principal de la muestra. Estos porcentajes se calculan sobre el total de cada año, incluidos todos los formatos.

Estos resultados respaldan la hipótesis del predominio del vinilo dentro del dataset, pero no permiten afirmar por sí solos que todos esos lanzamientos estuvieran orientados al club o al DJing.

El vinilo aumenta de 1.653 lanzamientos en 1990 a su máximo de 3.221 en 1996. Después disminuye hasta 2.473 en 1999 y repunta a 2.750 en 2000. No presenta, por tanto, un crecimiento continuo.

6. ¿Qué lanzamientos registraron mayor interés de colección y demanda?

El lanzamiento con mayor presencia en las colecciones fue "#1, de Mr. Oizo", con 10.643 registros en [have] , seguido de "Knights Of The Jaguar EP, de The Aztec Mystic", con 7.689, y "American Pie, de Madonna", con 7.290. Thomas Bangalter (50% de Daft Punk) destacó por situar tres lanzamientos entre los diez más coleccionados.

En demanda, 'Knights Of The Jaguar EP" encabezó el ranking con 7.511 registros en  [want] , seguido de "6 Millions Pintades EP, de Pépé Bradock", con 6.838, y "Trax On Da Rocks Vol. 2, de Thomas Bangalter", con 5.390. Los diez lanzamientos más deseados correspondieron a ediciones en vinilo.

Cuatro registros coincidieron en ambos top 10, lo que indica una coincidencia parcial entre colección y demanda. Sin embargo, las diferencias de posición muestran que los lanzamientos más coleccionados no son necesariamente los más deseados. Los rankings describen ediciones concretas incluidas en la muestra, no el total agregado de todas las ediciones de una obra.

Los indicadores reflejan el estado de las colecciones y listas de deseos en el momento de recopilar los datos. El periodo 1990–2000 corresponde al año de publicación de los lanzamientos, no al momento en que los usuarios los añadieron.

7. ¿Qué relación existe entre [have], [want], [num_ratings], [average_rating_clean] y [lowest_price_clean], [median_price_clean], [highest_price_clean]?

[have] vs [want]
Se obtuvo una correlación de Pearson de 0,593, lo que indica una asociación lineal positiva de magnitud moderada. Los lanzamientos con mayor presencia en las colecciones tienden también a registrar un mayor número de usuarios interesados en obtenerlos. Sin embargo, el gráfico muestra una dispersión considerable y una elevada concentración de registros en los valores bajos de ambas variables. También aparecen lanzamientos con niveles excepcionalmente altos de colección o demanda. En conjunto, ambos indicadores están relacionados, pero no son equivalentes ni esta asociación demuestra causalidad.

[want] vs [median_price_clean]
Se analizó la relación en 29.414 lanzamientos con valores numéricos en ambas variables. La correlación de Pearson obtenida fue de 0,600, compatible con una asociación lineal positiva de magnitud moderada.

El gráfico muestra, sin embargo, una dispersión considerable, lanzamientos con niveles similares de demanda presentan precios muy diferentes. Además, los mayores precios medianos no corresponden a los registros más deseados. Por tanto, el resultado respalda la hipótesis de una asociación positiva entre demanda y precio dentro de la muestra, pero no una relación proporcional ni una explicación causal.

[have] vs [median_price_clean]
Se analizó la relación en 29.414 lanzamientos con valores numéricos en ambas variables. La correlación de Pearson fue de 0,130, indicando una asociación lineal positiva muy débil. El gráfico muestra que los lanzamientos más coleccionados no son necesariamente los más caros.

En contraste, la correlación entre demanda ( want ) y precio mediano fue de 0,600. Por tanto, en los cruces analizados, la demanda presenta una asociación lineal con el precio mayor que la presencia en colecciones, sin que esto implique causalidad.

[average_rating_clean] vs [want]

Se analizó la relación en 29.192 lanzamientos con valores numéricos en ambas variables y al menos una valoración registrada [num_ratings] > 0.

Se obtuvo una correlación de Pearson de 0,276, compatible con una asociación lineal positiva débil. Los lanzamientos mejor valorados tienden a presentar una mayor demanda, aunque la
valoración media, por sí sola, no permite anticipar con precisión el interés por obtener un lanzamiento.

Los 734 registros que no cumplieron los criterios de inclusión se excluyeron únicamente de este cruce y se conservaron en el dataset procesado.

El análisis asigna el mismo peso a cada lanzamiento, con independencia de su número de valoraciones. Por tanto, una puntuación basada en pocos votos participa en la correlación igual que otra respaldada por cientos de votos.

El resultado describe una asociación y no demuestra que una mejor valoración provoque una mayor demanda.

[average_rating_clean] vs [have]

Se analizó la relación en 29.132 lanzamientos con valores numéricos en ambas variables y al menos una valoración registrada [num_ratings] > 0.

El coeficiente de Pearson obtenido fue de 0,174, lo que indica una asociación lineal positiva muy débil. Los lanzamientos mejor valorados tienden ligeramente a estar más presentes en las colecciones, pero la relación es limitada: una valoración media elevada no implica necesariamente un mayor número de usuarios que poseen el lanzamiento.

En comparación con el cruce entre [average_rating_clean] vs [want], cuya correlación fue de 0,276, la asociación con la presencia en colecciones es menor. Esta comparación es descriptiva, ya que ambos análisis utilizan conjuntos de registros válidos que pueden diferir.

En conclusión, la valoración media presenta poca asociación lineal con  have  dentro de la muestra. El resultado no demuestra causalidad y debe interpretarse considerando que cada lanzamiento recibe el mismo peso en el cálculo, independientemente del número de votos que respalden su valoración media.

[average_rating_clean] vs [median_price_clean]

Se analizó la relación en 28.903 lanzamientos con valores numéricos en ambas variables y al menos una valoración registrada [num_ratings] > 0.

El coeficiente de correlación de Pearson fue de 0,271, lo que indica una asociación lineal positiva débil. Los lanzamientos mejor valorados tienden ligeramente a presentar precios medianos más elevados, pero la relación es limitada: una puntuación alta no implica necesariamente un precio alto.

El resultado no demuestra causalidad. Además, cada lanzamiento recibe el mismo peso en el cálculo, independientemente del número de votos que respalden su valoración media. Los 1.023 registros que no cumplieron los criterios de inclusión se excluyeron únicamente de este cruce y se conservaron en el dataset procesado.

## Balance final 

La hipótesis de que los lanzamientos más deseados pueden presentar precios medianos más altos queda respaldada dentro de la muestra por la correlación de 0,600.

La hipótesis sobre valoración e interés de colección recibe un respaldo limitado: las asociaciones son positivas, pero débiles. Además, no podemos concluir que valoración y precio 
carezcan de relación: obtuvimos una asociación positiva débil de 0,271, similar en magnitud a la observada entre valoración y demanda.

Estos resultados son descriptivos, utilizan bases válidas que pueden diferir y no permiten establecer qué variable causa a otra.


8. ¿Qué estilos alcanzaron mayores precios de mercado?

Freetekno y Minimal Techno presentaron las medianas más elevadas del ranking, ambos con un valor mostrado de $16,30, respaldados por 38 y 72 lanzamientos con precio, respectivamente.

A continuación se situaron Bleep, con $10,87 y 202 registros; Dub Techno, con $10,76 y 59 registros; e IDM, con $8,70 y 318 registros.

Entre los estilos con bases más amplias, también destacaron Minimal, Acid, Experimental y Ambient. En contraste, House y Techno, que lideraban el análisis de volumen de lanzamientos, registraron medianas de $3,24 y $5,43, respectivamente

Los estilos con mayor volumen de lanzamientos no fueron necesariamente los que presentaron precios medianos más elevados. Freetekno y Minimal Techno encabezaron el ranking entre los estilos con al menos 30 registros con precio, seguidos por Bleep y Dub Techno.

Los resultados muestran diferencias descriptivas de precio entre las etiquetas de estilo, pero no permiten afirmar que el estilo determine el valor de un lanzamiento. Tampoco demuestran una revalorización histórica, ya que se comparan los precios recogidos en el dataset para lanzamientos publicados entre 1990 y 2000, no la evolución de sus precios a lo largo del tiempo.

La lectura debe considerar que los grupos tienen tamaños distintos y que las etiquetas se solapan: un mismo lanzamiento puede contribuir al resultado de varios estilos.

9. ¿Qué artistas y sellos aparecen asociados a los lanzamientos más valorados?

En la hoja auxiliar [Top_rated_releases] se seleccionaron los diez lanzamientos con mayor valoración media entre aquellos con al menos 500 votos, ordenados por puntuación descendente y, en caso de empate, por número de valoraciones. Los resultados que siguen corresponden a ese análisis auxiliar. El gráfico del dashboard utiliza otra implementación: una tabla dinámica en `Analytics`, un bloque de salida y el segmentador `Votes threshold`. Por tanto, el mínimo fijo y el desempate de esta hoja no deben atribuirse automáticamente al gráfico interactivo.
Choice encabezó el ranking con Acid Eiffel / How Do You Plead?, publicado por Fragile Records, con una valoración de $4,82 y 771 votos. Le siguieron Galaxy 2 Galaxy, con $4,78 y 911 votos, y Pépé Bradock con Burning, con $4,77 y 1.039 votos. También aparecieron Aril Brikha, Sasha, Drexciya, The Aztec Mystic, DJ Rolando, Ron Trent y Maurizio.

Por sellos, Underground Resistance concentró cuatro de los diez registros y Fragile Records dos. Kif Recordings, Deconstruction, Djax-Up-Beats y Maurizio estuvieron representados por un lanzamiento cada uno. Por tanto, Underground Resistance y Fragile Records destacaron por su presencia en esta selección de lanzamientos altamente valorados.

## Contraste con las hipótesis iniciales

Esta pregunta aporta un resultado exploratorio, pero no valida ni descarta directamente ninguna de las hipótesis iniciales:

La hipótesis sobre sellos especialmente activos se refiere al número de publicaciones, mientras que este ranking analiza la valoración de lanzamientos concretos. La presencia de Deconstruction, uno de los sellos mencionados inicialmente, no basta para confirmar que estuviera entre los más productivos.

Este hallazgo complementa el estudio de los sellos por volumen de publicaciones, pero no demuestra que sean los más productivos ni los mejor valorados en el conjunto de sus catálogos.

La hipótesis sobre la relación entre [num_ratings], [want] y precio debe contrastarse con los cruces de la pregunta 7, no con este ranking.

El mínimo de 500 votos delimita la selección a lanzamientos con mayor participación de usuarios, pero no convierte el resultado en una clasificación representativa de todos los lanzamientos.

10.	¿Cómo cambió la composición del mercado electrónico a lo largo de la década?

Entre 1990 y 2000, la composición de los lanzamientos analizados experimentó cambios de formato, estilo y distribución geográfica. El vinilo conservó su predominio, aunque el CD ganó participación. Entre los estilos seleccionados, House perdió peso relativo, Techno destacó especialmente al comienzo del periodo y Progressive House amplió su presencia. Geográficamente, Reino Unido consolidó su posición, Alemania y Francia aumentaron su participación y Estados Unidos terminó con un peso menor que en 1990.

Los resultados describen cambios en la composición del dataset, no cuotas de ventas ni relaciones causales. Una caída porcentual no implica necesariamente una reducción de publicaciones, y la evolución de cinco estilos no permite caracterizar toda la diversidad de la música electrónica. La interpretación geográfica también debe considerar los registros sin país identificado o clasificados únicamente por zona de mercado.

Los veredictos siguientes son descriptivos: indican hasta qué punto los resultados del dataset respaldan cada planteamiento. No equivalen a pruebas estadísticas formales ni permiten generalizar automáticamente a todo el mercado de música electrónica.

## 1. El número de lanzamientos creció durante la primera mitad de los años noventa

Veredicto: respaldada como tendencia general, pero no como crecimiento continuo.

Los lanzamientos aumentaron de 1.757 en 1990 a 2.394 en 1994 y alcanzaron 3.072 en 1995. Sin embargo, en 1994 se produjo una pequeña disminución respecto a los 2.418 registros de 1993. El máximo de todo el periodo analizado llegó en 1996, con 3.516 lanzamientos.

Por tanto, el dataset respalda una expansión entre el inicio y mediados de los noventa, con fluctuaciones interanuales.

## 2. El vinilo fue el formato dominante, especialmente en lanzamientos orientados al club y al DJing

Veredicto: parcialmente respaldada.

El predominio del vinilo queda claramente respaldado: reúne 26.940 de los 29.926 lanzamientos, aproximadamente el 90,02 % del total. Además, mantuvo una participación anual superior al 84 % durante todo el periodo.

No obstante, el análisis no estableció una clasificación específica de lanzamientos orientados al club o al DJing. En consecuencia, esa parte de la hipótesis queda sin comprobar.

## 3. House, Deep House, Garage House, Techno y Progressive House concentraron una parte relevante de la producción

Veredicto: parcialmente respaldada; los cinco estilos no tuvieron el mismo peso.

La evolución anual confirma una presencia especialmente elevada de House y Techno. House aparece aproximadamente en el 57 % de los lanzamientos de 1990 y en el 31 % de los de 2000; Techno alcanza alrededor del 47 % en 1991–1992. Progressive House amplía su presencia desde aproximadamente el 1 % inicial hasta el 18 % en 2000. Deep House y Garage House presentan participaciones menores.

La hipótesis se sostiene mejor como una combinación de estilos de gran volumen y otros de presencia más limitada, no como un dominio equivalente de los cinco.

No se calculó su concentración conjunta sin duplicados: los porcentajes no deben sumarse porque un mismo lanzamiento puede incluir varias etiquetas de estilo.

## 4. Existieron sellos especialmente activos, como Strictly Rhythm, Nervous Records, Network Records, Cutting Records, FFRR, Deconstruction, Positiva o Perfecto

Veredicto: parcialmente respaldada para la selección propuesta.

El ranking confirma la actividad de algunos sellos mencionados: FFRR registra 185 lanzamientos, Strictly Rhythm 179 y Deconstruction 115. Sin embargo, los primeros puestos generales corresponden a Virgin, con 315; Epic, con 263; y Columbia, con 245 los sellos mas mainstream con fuerte presencia en todos los mercados.

Por tanto, algunos ejemplos iniciales destacan, pero no encabezan el ranking. No se dispone en esta síntesis de los recuentos individuales de los otros cinco sellos propuestos, por lo que no corresponde confirmar la lista completa.

La categoría `Not On Label` se conserva en los datos, pero no se interpreta como una discográfica única ni se incluye en el ranking de sellos identificados.

## 5. Los lanzamientos más deseados pueden presentar precios medianos más elevados

Veredicto: respaldada descriptivamente.

En el cruce entre [want] y [median_price_clean] se obtuvo una correlación de Pearson de 0,600, sobre 29.414 pares válidos.

Esto respalda una asociación lineal positiva entre demanda registrada y precio mediano dentro de la muestra. No significa que todos los lanzamientos más deseados sean más caros ni demuestra que la demanda sea la causa del precio.

## 6. La valoración media puede relacionarse con el interés de colección, aunque no necesariamente con el precio de mercado

Veredicto: parcialmente respaldada y matizada por los resultados.

Los coeficientes obtenidos fueron:

| Cruce | Correlación de Pearson | Pares válidos |
|---|---:|---:|
| [average_rating_clean] y [have] | 0,174 | 29.132 |
| [average_rating_clean] y [want] | 0,276 | 29.192 |
| [average_rating_clean] y [median_price_clean] | 0,271 | 28.903 |

La valoración presenta una asociación positiva muy débil con la presencia en colecciones y asociaciones positivas débiles con demanda y precio.

Por tanto, no corresponde concluir que la valoración se relaciona con la colección, pero no con el precio: ambos cruces muestran asociaciones positivas, y la correlación con precio es numéricamente mayor que la obtenida con [have].

Las comparaciones entre coeficientes son descriptivas, utilizan bases diferentes y no se sometieron a una prueba formal de diferencias.

## 7. Estados Unidos, Reino Unido, Alemania, Italia, Países Bajos y Francia concentraron una parte importante de la producción

Veredicto: respaldada dentro del dataset, con diferencias importantes entre países.

Los seis países suman 24.803 registros de los 29.926 analizados, aproximadamente el 82,88 % del total. Reino Unido y Estados Unidos encabezan el conjunto, seguidos por Alemania e Italia; Países Bajos y Francia tienen participaciones menores.

La concentración no fue estática: entre 1990 y 2000, Reino Unido pasó del 30,39 % al 35,27 %, Alemania del 7,46 % al 14,98 % y Francia del 1,14 % al 4,83 %. Estados Unidos descendió del 31,36 % al 18,33 %, e Italia del 8,42 % al 4,51 %.

La conclusión se refiere a la clasificación geográfica de los lanzamientos, no a la nacionalidad de los artistas, el lugar de fabricación o las ventas.

## Resumen de conclusiones

El análisis exploratorio respalda una expansión general del número de lanzamientos entre el inicio y mediados de los noventa, el predominio del vinilo y una elevada concentración geográfica en los seis países propuestos. También identifica diferencias importantes entre estilos y sellos, por lo que las selecciones iniciales requieren matices: no todos los nombres planteados ocuparon posiciones equivalentes.

En los cruces realizados, la demanda registrada mostró una asociación positiva con el precio mediano. La valoración media presentó relaciones más débiles con colección, demanda y precio, sin que estos resultados permitan establecer causalidad.

Las hipótesis se consideran respaldadas o parcialmente respaldadas únicamente dentro del alcance del dataset y de los criterios aplicados. Las partes no comprobadas se mantienen expresamente como limitaciones, sin ampliar el análisis para resolverlas en esta versión.

## Implementación final del dashboard y comprobaciones funcionales de segmentadores y macro

## Importación y actualización de datos

El archivo `01_discogs_electronic.csv` se importó mediante **Datos → Obtener datos (Power Query)**. 

La hoja procesada utilizada en los cálculos es `Discogs_electronic_processed.xlsm`.

Al ejecutar **Datos → Actualizar todo**, Excel mostró un aviso de conexión a un origen externo. Se identificó esa conexión como la importación del CSV del proyecto.

Se decidió no incluir **Actualizar todo** en la macro de restablecimiento de filtros: la actualización del origen y el restablecimiento de la selección se mantienen como operaciones separadas.

## Segmentador YEAR y gráficos dinámicos

Controla las tablas dinámicas utilizadas por:

- [Releases by year]
- [Formats by year]
- [Selected styles by year]

La tabla auxiliar de proporciones anuales por estilos documentada anteriormente sigue siendo un análisis diferente. No se atribuyen sus porcentajes, denominadores o rangos al gráfico dinámico final sin comprobar directamente sus series. La revisión confirma la interactividad de este último, no una equivalencia entre ambos bloques.

## Conexión de YEAR con el recuento por estilos

`Top 10 styles by release count` se alimenta de una tabla normal agregada por estilos, no directamente de una tabla dinámica. Para trasladar la selección de años a sus cálculos, se incorporó una tabla dinámica auxiliar en `Analytics`, conectada al mismo segmentador YEAR.

| Elemento | Ubicación o función |
|---|---|
| Lista de años seleccionados | `Analytics!B44:B54` |
| Total general en la disposición observada | `Analytics!B55` |
| Columna de años del origen | `Discogs_electronic_processed!G:G` |
| Columna de estilos del origen | `Discogs_electronic_processed!I:I` (`styles_clean`) |
| Nueva medida de la tabla normal | `Releases_selected_year` |
| Primera celda de cálculo confirmada | `Analytics!K11` |

El gráfico utiliza los siguientes rangos:

Valores: =Analytics!$K$11:$K$20
Etiquetas: =Analytics!$I$11:$I$20

## Top 10 de lanzamientos mejor valorados: dos implementaciones

## Análisis auxiliar `Top_rated_releases`

La hoja auxiliar utiliza un mínimo fijo de 500 votos y ordena los lanzamientos por valoración descendente, con número de votos como desempate. Los resultados narrados en la pregunta de análisis 9 corresponden a esta selección.

En ese análisis, Choice — *Acid Eiffel / How Do You Plead?*, de Fragile Records, encabeza el ranking con 4,82 y 771 votos.

## Gráfico interactivo del dashboard

La revisión identificó el siguiente recorrido:


Tabla dinámica en Analytics
          ↓
Bloque de salida Analytics!CS12:CT22
          ↓
Gráfico Top 10 highest rated releases del dashboard


| Componente | Configuración observada |
|---|---|
| Campos de identificación visibles | [title] y [artist] |
| Medida de votos | `Máx. de [num_ratings], en CP |
| Medida de puntuación | Promedio de [average_rating_clean], en CQ |
| Filtros de la tabla dinámica | [votes_threshold] y [style_primary] |
| Bloque de salida | `Analytics!CS12:CT22` |
| Etiquetas de salida | Columna CS, [Artist - Title] |
| Puntuaciones de salida | Columna CT |
| Referencia comprobada | La puntuación de CT13 procede de CQ13 |

Las capturas mostraron inicialmente ambos filtros en «(Todas)». En esa vista aparecían puntuaciones de 5,000 acompañadas de recuentos de votos bajos en la tabla dinámica. Por tanto, el gráfico no debe describirse como limitado permanentemente a 500 votos o más.

El filtro [style_primary] corresponde al primer estilo de [styles_clean]; no equivale a buscar el estilo en cualquiera de las etiquetas de un lanzamiento.

## Prueba del segmentador Votes threshold

Se seleccionó únicamente `500+` en el segmentador del dashboard. Se confirmó que Choice pasó a ocupar el primer lugar del gráfico.

La prueba acredita que el filtro llega al gráfico final a través de su tabla y bloque de apoyo. La confirmación comunicada fue la primera posición de Choice; no se registró una comprobación independiente de las diez posiciones, de la puntuación mostrada ni del desempate del gráfico.

- El mínimo de 500 votos depende de seleccionar `500+`.
- Los empates del gráfico se resuelvan por número de votos.
- La tabla dinámica muestra una media de [average_rating_clean] y un máximo de [num_ratings]; estas agregaciones no deben confundirse con una media ponderada por votos.
- La agrupación visible por artista y título no demuestra que todas las ediciones estén separadas mediante un identificador único en ese gráfico.

### Texto de síntesis para la memoria

Para la construcción del dashboard combiné tablas dinámicas, tablas auxiliares y fórmulas de Excel. Conecté el segmentador YEAR a los gráficos dinámicos de evolución anual, formatos y estilos seleccionados. Para trasladar la selección temporal al recuento por estilos, incorporé una tabla dinámica auxiliar que devuelve los años seleccionados y añadí la medida [Releases_selected_year] a la tabla de apoyo. Comprobé tanto la selección múltiple de años como el funcionamiento del cálculo. La actualización automática del orden del Top 10 de estilos tambien se verifico.

Mantuve el gráfico dinámico de estilos para conservar su interactividad, en lugar de sustituirlo por una visualización estática con líneas suavizadas. Diferencié este gráfico del análisis auxiliar de porcentajes anuales por etiquetas de estilo.

Para el gráfico de lanzamientos mejor valorados identifiqué una tabla dinámica en `Analytics` y el bloque `CS12:CT22` que alimenta sus etiquetas y puntuaciones. Comprobé que, al seleccionar `500+` en el segmentador `Votes threshold`, Choice aparece en primer lugar. Separé esta implementación interactiva del análisis auxiliar `Top_rated_releases`, que utiliza un mínimo fijo de quinientos votos y un criterio de desempate por cantidad de valoraciones.
