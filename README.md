# Trabajo de Analisis de Datos en base a los Accidentes de Transito en la Ciudad de Buenos Aires

![Imagen caratula](https://camo.githubusercontent.com/a8afd26d487e19995da36a49959dc1b8286e07a898e1e27d296fde19b23fb461/68747470733a2f2f7374617469632e6c616a6f726e61646165737461646f64656d657869636f2e636f6d2f77702d636f6e74656e742f75706c6f6164732f323032322f30382f53696e69657374726f732d7669616c65732e6a7067)
## Introducción
En este proyecto nos ponemos en la piel dee un Data Analyst al servicio de El Observatorio de Movilidad y Seguridad Vial (OMSV), un organismo parte de la Oficina de Transporte del Gobierno de la Ciudad de Buenos Aires, el cual nos encarga realizar un analisis detallado de los datos 

El proposito de este analisis es proveer a las autoridades pertinentes la informacion adecuada para la toma de decisiones sobre uno de los temas que mas afectan a esta gran ciudad, para hacer esto, trabajaremos con la informacion provista a traves de la pagina (https://data.buenosaires.gob.ar/dataset/victimas-siniestros-viales)

Para abordar esta problematica, se realiza este trabajo el cual consta de 4 partes:
- las **Cargas**  y **Transformaciones**
- el **EDA**
- la carga de informacion a **SQL**
- la presentacion en **Power Bi**


## Estructura
Este proyecto se basa alrededor de 3 preguntas que nos planteamos, las cuales consideramos de maxima importancia a la hora de tomar las medidas:

- QUIEN? (analisis de las victimas)
- CUANDO? (analisis de dispercion de tiempo)
- DONDE? (analisis geografico)

este proyecto se basa en responder estas preguntas con toda la informacion neccesaria para las autoridades pertinentes

## Tecnologias utilizadas

En el proyecto se utilizan Tecnologias conjuntas

En Python, utilizamos las librerias de:
- Pandas
- Matplotlib
- Seaborn
- Re
- SQLalchemy

Se utilizo SQL para almacenar los datos en el servidor

Para el Dashboard interactivo se utilizo Power Bi, desde donde llamamos a la base de datos de SQL


## Data Analisis
El estudio efectuado desvela una serie de pautas significativas en cuanto a los homicidios, abordando variables temporales, perfiles de víctimas y distribución geoespacial.

En primer término, se aprecia una marcada disminución en el número de homicidios durante el año 2020, atribuible a las medidas de confinamiento por la pandemia de COVID-19. No obstante, esta tendencia no se repite consistentemente en años anteriores. Aunque diciembre resalta como un mes con un aumento en el número de víctimas, esta tendencia no es uniforme en todos los años, sugiriendo una posible influencia de la flexibilización de las restricciones de confinamiento en los patrones de homicidios.

Al examinar escalas temporales más detalladas, se constata que la mayoría de los homicidios ocurren entre lunes y viernes, lo que podría relacionarse con los desplazamientos diarios al trabajo. Sin embargo, no se observan diferencias significativas en la distribución de víctimas entre los distintos días de la semana. Además, un porcentaje considerable de las víctimas se registra en las primeras horas de la mañana, aunque la mayoría de estos incidentes ocurrieron durante el fin de semana.

En cuanto al perfil de las víctimas, sobresale que la mayoría son hombres, principalmente dentro del rango de edad de 25 a 35 años. Cerca de la mitad de las víctimas son conductores, principalmente de motocicletas, y la responsabilidad del accidente recae principalmente en vehículos como automóviles, autobuses y camiones.

En términos de distribución geoespacial, los accidentes en las avenidas son frecuentes en todas las comunas de la Ciudad Autónoma de Buenos Aires, con la mayoría de las víctimas perdiendo la vida en estos lugares, especialmente en los cruces con otras calles. El papel de la víctima varía entre motociclista y peatón dependiendo de la comuna.

Este análisis completo proporciona una visión detallada de los patrones temporales, el perfil de las víctimas y los factores espaciales asociados con los homicidios, lo que puede ser crucial para identificar áreas de enfoque en términos de prevención y políticas públicas orientadas a la seguridad ciudadana



## PROCEDIMIENTO Y ORDEN

- En primer lugar, se descargan los archivos [homicidios](https://data.buenosaires.gob.ar/dataset/victimas-siniestros-viales/resource/7529164c-5a3f-453d-8509-d0af49267c37)*, [comunas](https://www.indec.gob.ar/indec/web/Nivel4-Tema-2-41-165) "Cuadro 1.1",  y [lesiones](https://data.buenosaires.gob.ar/dataset/victimas-siniestros-viales/resource/05837b81-0f62-43cc-a068-d7132228ee08)**

- se procede  a realizar un vistazo general de la informacion en pandas, las primeras transformaciones, uniones y tambien, las primeras ideas de como encarar el proyecto en base a los datos

- Se realiza la creacion de una base de datos en SQL en un entorno local, se crean las tablas con los formatos pertinentes y se proceden a cargar los archivos "refinados"

- se llaman esas tablas a Pandas devuelta con **sqlalchemy** y se realiza un analisis profundo con la idea de empezara ver dispersiones, patrones y tener una mejor nocion de los datos con los que se trabaja. A raiz de este analisis nacen nuevas transformaciones y se crean los archivos **"comunasSQL"** y **"homicidiosSQL"**

- se cargan estos nuevos archivos a la base de datos de SQL, una vez el proceso esta completado, estas tablas seran importadas a Power Bi donde se realiza la presentacion y la medicion de los KPI

*homicidios este archivo excel cuenta con dos hojas, se obtienen los datos de las dos por separado y luego se mezclan según sus ID

**lesiones, si bien se trabajo en un principio esta tabla resulto obsoleta para el trabajo posterior, pero se incluye pues es parte y puede obtener relevancia en un futuro



## Navegacíon
dentro de la carpeta del proyecto encontra lo siguiente:

### carpeteta data:
- carpeta raw: contiene los 3 archivos .xlsx, nuestra materia prima
- carpeta refined: contiene los 3 archivos .csv obtenidos despues de *lec_y_transf*, los cuales fueron cargados a SQL en el archivo *carga_tablas_pre_eda*

### carpeta Imagenes:
- imagenes utilizadas en la presentacion y en este README

### carpeta procesos:
- carpeta SQL: contiene una carpeta con los arhivos .csv finales utilizados en la presentacion y ademas dos archivos, **carga_tablas_pre_eda** y **carga_tablas**, donde en una se cargan las tablas para el eda y en otra para la presentacion respectivamente
- carpeta Visual Studio: contiene dos archivos, **EDA** y **lec_y_transf** donde en uno se hace el Analisis Exploratorio de Datos y en el otro se realizan las primeras cargas y trabajos sobre la materia prima respectivamente