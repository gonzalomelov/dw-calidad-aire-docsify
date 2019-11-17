
Análisis {#analisis_data_warehouse}
--------

La primera etapa del proceso es el Análisis. En esta se trabaja con los
especialistas del Servicio de Calidad de Aire para poder comprender y
plasmar formalmente las funcionalidades y requisitos que se espera del
sistema de BI.

La etapa de Especificación de Requerimientos se realiza mediante un
enfoque combinado, utilizando paralelamente el enfoque orientado a las
fuentes y el enfoque orientado al usuario, y luego integrando los
resultados de ambas etapas para lograr requerimientos que sean de
utilidad para los usuarios y que puedan ser realizados con los datos
disponibles.

Como base para la identificación de requerimientos, se visualizan las
principales actividades contaminantes, como la quema de combustible para
el transporte y la industria; el uso de leña tanto en el área comercial
como residencial para la calefacción y cocción de alimentos, la
generación de energía eléctrica a partir de centrales térmicas y quema
de residuos a cielo abierto, de las cuales se necesita realizar un
análisis, y las fuentes de datos que se disponen.

### Enfoque orientado a las fuentes {#sec:enfoque_orientado_fuentes}

Como primer paso, se investigan todas las fuentes de datos internas,
abiertas al público o no, con las que se dispone desde el Servicio de
Calidad de Aire, desde bases de datos disponibles hasta archivos con
datos que puedan ser de utilidad.

Luego, se investigan fuentes de datos externas que puedan ser cruzadas
con las obtenidas del Servicio de Calidad de Aire para darle un mayor
valor agregado al análisis y lograr visualizar las mediciones de
contaminación junto con otros indicadores, para identificar relaciones
entre los distintos tipos de datos. Para dicha búsqueda se utiliza el
Catálogo de Datos Abiertos de la Agencia de Gobierno Electrónico y
Sociedad de la Información y del Conocimiento (AGESIC)
[@agesic_catalogo_datos_abiertos] donde se encuentra una gran variedad
de datos y tipos de datos.

A continuación se describe cada fuente de datos analizada:

**Barrios de Montevideo**

Shapefile [^1] de polígonos con los barrios de Montevideo. En la
[\[fig:analisis\_barrios\_1\]](#fig:analisis_barrios_1){reference-type="ref"
reference="fig:analisis_barrios_1"} se presenta un mapa gráfico de la
ciudad de Montevideo diferenciando los distintos polígonos de los
barrios en colores y en la
[\[fig:analisis\_barrios\_2\]](#fig:analisis_barrios_2){reference-type="ref"
reference="fig:analisis_barrios_2"} se puede visualizar la información
tabular del archivo Shapefile donde se muestra el área ocupada, nombre,
número y código.

Los datos de los barrios de Montevideo son mantenidos en el Servicio de
Geomática [@servicio_geomatica]. Los mismos son provistos por el
Instituto Nacional de Estadística (INE) [@ine].

![\[\[fig:analisis\_barrios\_1\]\]{#fig:analisis_barrios_1
label="fig:analisis_barrios_1"}Mapa Barrios de Montevideo
[@servicio_geomatica]](Imagenes/analisis_barrios_1.png){width="\\textwidth"}

![\[\[fig:analisis\_barrios\_2\]\]{#fig:analisis_barrios_2
label="fig:analisis_barrios_2"}Datos Barrios de Montevideo
[@servicio_geomatica]](Imagenes/analisis_barrios_2.png){width="60%"}

**Centros Comunales Zonales (CCZ) de Montevideo**

Shapefile de polígonos con los CCZ de Montevideo. En la
[\[fig:analisis\_ccz\_1\]](#fig:analisis_ccz_1){reference-type="ref"
reference="fig:analisis_ccz_1"} se presenta un mapa gráfico de la ciudad
de Montevideo diferenciando los distintos polígonos de los CCZ en
colores y en la
[\[fig:analisis\_ccz\_2\]](#fig:analisis_ccz_2){reference-type="ref"
reference="fig:analisis_ccz_2"} se puede visualizar la información
tabular del archivo Shapefile donde se muestra un identificador
autogenerado y el nombre de cada CCZ.

Los datos de los CCZ de Montevideo son mantenidos en el Servicio de
Geomática de la IM.

![\[\[fig:analisis\_ccz\_1\]\]{#fig:analisis_ccz_1
label="fig:analisis_ccz_1"}Mapa CCZ de Montevideo
[@servicio_geomatica]](Imagenes/analisis_ccz_1.png){width="\\textwidth"}

![\[\[fig:analisis\_ccz\_2\]\]{#fig:analisis_ccz_2
label="fig:analisis_ccz_2"}Datos CCZ de Montevideo
[@servicio_geomatica]](Imagenes/analisis_ccz_2.png){width="40%"}

**Descripción de campos de medidas históricas**

Esta fuente de datos sirve de meta-información
[@analisis_descripcion_historico] para comprender los archivos de
medidas históricas de calidad de aire que se presentan a continuación.
En la
[\[fig:descripcion\_medidas\_historicas\]](#fig:descripcion_medidas_historicas){reference-type="ref"
reference="fig:descripcion_medidas_historicas"} se puede visualizar el
formato y significado de cada campo de los archivos de medidas
históricas calidad de aire.

Los datos son generados por el Servicio de Calidad de Aire de la IM.

![\[\[fig:descripcion\_medidas\_historicas\]\]{#fig:descripcion_medidas_historicas
label="fig:descripcion_medidas_historicas"}Descripción medidas
históricas calidad de aire
[@analisis_descripcion_historico]](Imagenes/descripcion_medidas_historicas.png){width="\\textwidth"}

En la misma fuente de datos se especifican los archivos de medidas
históricas que se disponibilizan, diferenciando las estaciones
automáticas de las manuales, como se puede visualizar en la
[\[fig:archivos\_medidas\_historicas\_1\]](#fig:archivos_medidas_historicas_1){reference-type="ref"
reference="fig:archivos_medidas_historicas_1"} y la
[\[fig:archivos\_medidas\_historicas\_2\]](#fig:archivos_medidas_historicas_2){reference-type="ref"
reference="fig:archivos_medidas_historicas_2"}. Para cada fuente se
indica su nombre de archivo, estación de medición y período de cada
conjunto de mediciones.

![\[\[fig:archivos\_medidas\_historicas\_1\]\]{#fig:archivos_medidas_historicas_1
label="fig:archivos_medidas_historicas_1"}Archivos de medidas históricas
calidad de aire
[@analisis_descripcion_historico]](Imagenes/archivos_medidas_historicas_1.png)

![\[\[fig:archivos\_medidas\_historicas\_2\]\]{#fig:archivos_medidas_historicas_2
label="fig:archivos_medidas_historicas_2"}Archivos de medidas históricas
calidad de aire
[@analisis_descripcion_historico]](Imagenes/archivos_medidas_historicas_2.png)

**Medidas históricas calidad de aire**

Estas medidas van desde el 2005 hasta el 2018
[@analisis_medidas_historicas_calidad_aire] y para cada una se detalla a
qué contaminante se mide, las unidades, el valor y el método de
medición. Así como otros datos de interés como se explica en el archivo
de descripción de la metadata. En la
[\[fig:descripcion\_medidas\_historicas\]](#fig:descripcion_medidas_historicas){reference-type="ref"
reference="fig:descripcion_medidas_historicas"} se pueden visualizar los
campos y los valores descritos.

Los datos son generados por el Servicio de Calidad de Aire de la IM de
las distintas estaciones de la red.

![\[\[fig:icaire\_fuente\_de\_datos\]\]{#fig:icaire_fuente_de_datos
label="fig:icaire_fuente_de_datos"}Medidas históricas calidad de aire
[@analisis_medidas_historicas_calidad_aire]](Imagenes/data_source_example.png)

**Medidas históricas de sensores de la plataforma IoT - PM10**

Este conjunto contiene las medidas históricas de los sensores de calidad
del aire de la plataforma de Internet of Things (IoT)
[@analisis_historico_iot], esta plataforma cuenta con una estación de
medición automática en tiempo real conectada a internet donde envía
periódicamente los datos de medición. Los valores en tiempo real de
estos sensores se pueden acceder a través de los servicios abiertos de
la plataforma. En la
[\[fig:analisis\_iot\]](#fig:analisis_iot){reference-type="ref"
reference="fig:analisis_iot"} se puede visualizar las columnas
identificador autogenerado, identificador de estación o nodo,
contaminante medido, instante de tiempo de la medición y valor
correspondiente.

Los datos son generados por el Servicio de Calidad de Aire de la IM de
la estación automática que se encuentra en Tres Cruces.

![\[\[fig:analisis\_iot\]\]{#fig:analisis_iot
label="fig:analisis_iot"}Medidas históricas de sensores de la plataforma
IoT - PM10 [@analisis_historico_iot]](Imagenes/analisis_iot.png)

**Lista de Identificación de contaminantes**

Descripción de los tipos de contaminantes que se miden
[@analisis_contaminantes]. En la
[\[fig:analisis\_contaminantes\]](#fig:analisis_contaminantes){reference-type="ref"
reference="fig:analisis_contaminantes"} se puede visualizar las columnas
identificador autogenerado, código de contaminante y una descripción.

Los datos son generados por el Servicio de Calidad de Aire de la IM.

![\[\[fig:analisis\_contaminantes\]\]{#fig:analisis_contaminantes
label="fig:analisis_contaminantes"}Lista de Identificación de
contaminantes
[@analisis_contaminantes]](Imagenes/analisis_contaminantes.png)

**Métodos de medición**

Descripción de los métodos de medición utilizados [@analisis_metodos].
En la
[\[fig:analisis\_metodos\]](#fig:analisis_metodos){reference-type="ref"
reference="fig:analisis_metodos"} se puede visualizar las columnas
identificador autogenerado, código del método y una descripción.

Los datos son generados por el Servicio de Calidad de Aire de la IM.

![\[\[fig:analisis\_metodos\]\]{#fig:analisis_metodos
label="fig:analisis_metodos"}Métodos de medición
[@analisis_metodos]](Imagenes/analisis_metodos.png){width="\\textwidth"}

**Estaciones de medición**

Lista las estaciones de medición [@analisis_estaciones] de la Red de
Monitoreo de la IM. En la
[\[fig:analisis\_estaciones\]](#fig:analisis_estaciones){reference-type="ref"
reference="fig:analisis_estaciones"} se puede visualizar las columnas
identificador autogenerado, nombre de la estación, ubicación geográfica
mediante latitud y longitud, y el código de la estación.

Los datos son generados por el Servicio de Calidad de Aire de la IM.

![\[\[fig:analisis\_estaciones\]\]{#fig:analisis_estaciones
label="fig:analisis_estaciones"}Estaciones de medición
[@analisis_estaciones]](Imagenes/analisis_estaciones.png)

**ANCAP**

Datos de mediciones y datos meteorológicos históricos de la estación de
ANCAP [@analisis_ancap]. En la
[\[fig:analisis\_ancap\]](#fig:analisis_ancap){reference-type="ref"
reference="fig:analisis_ancap"} se pueden visualizar las columnas fecha
de medición y los valores medidos de CO, NO, NOx, NO2, PM2.5, SO2, TRS,
radiación solar global, humedad relativa, temperatura externa,
temperatura interna, dirección del viento y velocidad del viento.

Estos datos fueron provistos por ANCAP para el uso exclusivo que se
enmarca dentro del Proyecto de Grado.

![\[\[fig:analisis\_ancap\]\]{#fig:analisis_ancap
label="fig:analisis_ancap"}ANCAP
[@analisis_ancap]](Imagenes/analisis_ancap.png){width="\\textwidth"}

**Volumen vehicular**

El sistema de conteo vehicular que utiliza el Centro de Gestión de
Movilidad (CGM) [@centro_gestion_movilidad] para la medición de los
volúmenes vehiculares que circulan por las arterias que se encuentran
centralizadas, utiliza analíticas de vídeo para la generación de los
datos necesarios para la elaboración de planes y coordinaciones
semafóricas. Los detectores miden el total de vehículos y su
clasificación por largo de los mismos, por sentido de circulación,
pudiendo discriminarse por carril dentro de cada sentido
[@conteo_vehicular] [@conteo_vehicular_metadatos].

El sistema genera un registro cada 5 minutos, las medidas que se
explican a continuación corresponden a la suma de todos los vehículos de
los 5 minutos anteriores a la fecha y hora del registro. También se
publican datos particulares del sensor que permiten conocer su ubicación
y entender el sentido de circulación que se está midiendo.

En la
[\[fig:analisis\_volumen\_vehicular\]](#fig:analisis_volumen_vehicular){reference-type="ref"
reference="fig:analisis_volumen_vehicular"} se visualizan los siguientes
datos:

1.  volumen: Cantidad de vehículos que se contabilizó en los 5 minutos
    previos en un carril dado.

2.  volumen hora: Estimación de la cantidad de vehículos/hora que
    representan los 5 minutos previos medidos.

![\[\[fig:analisis\_volumen\_vehicular\]\]{#fig:analisis_volumen_vehicular
label="fig:analisis_volumen_vehicular"}Volumen Vehicular
[@conteo_vehicular]](Imagenes/analisis_volumen_vehicular.png)

**Vías de tránsito**

Shapefile de líneas con las vías de tránsito de Montevideo
[@analisis_vias_de_transito]. En la
[\[fig:analisis\_vias\_transito\]](#fig:analisis_vias_transito){reference-type="ref"
reference="fig:analisis_vias_transito"} se puede visualizar que contiene
los polígonos de las vías de Montevideo.

La información de vías de tránsito es mantenida en el Servicio de
Geomática, por la Unidad de Nomenclatura y Numeración.

![\[\[fig:analisis\_vias\_transito\]\]{#fig:analisis_vias_transito
label="fig:analisis_vias_transito"}Vías de tránsito
[@analisis_vias_de_transito]](Imagenes/analisis_vias_transito.png)

**Encuesta continua de hogares**
[\[sec:fuentes\_datos\_encuesta\_continua\_hogares\]\]{#sec:fuentes_datos_encuesta_continua_hogares
label="sec:fuentes_datos_encuesta_continua_hogares"}

Microdatos, cuestionarios, diccionario de variables y notas de la
Encuesta Continua de Hogares [@encuesta_continua_hogares]. Dentro del
conjunto de datos disponible se define analizar las condiciones de vida
de las personas mediante los indicadores socioeconómicos y demográficos,
desagregados por CCZ. En la
[\[fig:analisis\_encuesta\]](#fig:analisis_encuesta){reference-type="ref"
reference="fig:analisis_encuesta"} se puede visualizar un ejemplo de la
fuente de datos donde se presentan las distintas variables que se
utilizan para las mediciones.

Los datos de la encuesta continua de hogares son mantenidos por el INE.

![\[\[fig:analisis\_encuesta\]\]{#fig:analisis_encuesta
label="fig:analisis_encuesta"}Encuesta continua de hogares
[@encuesta_continua_hogares]](Imagenes/analisis_encuesta.png)

**Esquema de las fuentes de datos**

En la
[\[fig:fuentes\_datos\_esquema\_conceptual\]](#fig:fuentes_datos_esquema_conceptual){reference-type="ref"
reference="fig:fuentes_datos_esquema_conceptual"} se presenta un modelo
conceptual de las fuentes de datos donde se especifican las distintas
entidades y sus atributos. A su vez, como se puede reflejar, se muestran
las relaciones entre ellos indicando los distintos tipos de asociación
como uno a uno, uno a muchos o mucho a muchos.

![\[\[fig:fuentes\_datos\_esquema\_conceptual\]\]{#fig:fuentes_datos_esquema_conceptual
label="fig:fuentes_datos_esquema_conceptual"}Esquema conceptual de las
fuentes](Imagenes/fuentes_datos_esquema_conceptual.png){width="80%"}

### Enfoque orientado al usuario {#sec:enfoque_orientado_usuario}

Para identificar las necesidades que los usuarios del sistema de BI
quieren o pueden atacar, se realizan sucesivas reuniones presenciales
donde se discuten y ponen en la mesa ideas o solicitudes de análisis de
datos o situaciones puntuales que han surgido en el Servicio de Calidad
de Aire en los últimos años.

Dentro de los puntos que se lograron identificar se encuentran:

1.  Automatizar la realización de la sección Resultados de Red de
    Monitoreo del Informe Anual.

2.  Relacionar la combustión realizada en la quema de leña o carbón al
    hacer asados con los días festivos, por ejemplo, un 1ro de mayo.

3.  Investigar en qué medida varía la emisión de contaminantes en los
    días que la Central Batlle se encuentra encendida generando energía.

4.  Investigar la relación entre distintos contaminantes, esto es,
    cuánto influye en la emisión de un contaminante el aumento en la
    emisión de otro. Por ejemplo, cuánto influye un aumento de emisión
    de PM10 en la presencia de Humo Negro.

### Estudio de factibilidad {#sec:analisis_estudio_factibilidad}

Con las fuentes externas e internas disponibles se realizan distintos
prototipos con cruzamientos entre ellas para identificar, junto a los
especialistas de la IM, cuáles son los relacionamientos más relevantes
que pueden convertirse en requerimientos para un posterior análisis y
desarrollo de los mismos.

Los prototipos fueron plasmados en las herramientas de análisis de datos
con distintos ejemplos reales de cómo se visualizan los datos ingresados
en el sistema.

Esta forma de trabajo permite obtener feedback de los usuarios en etapas
tempranas del desarrollo del sistema, lo que brinda la posibilidad de
realizar cambios o ajustar tempranamente los requerimientos.

A continuación se describen los distintos cruzamientos que se realizaron
pero que no fueron tomados en cuenta para un posterior desarrollo:

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Cruzamiento                                                                                                                                                              Motivo
  Evolución en el tiempo de la contaminación del aire relacionándolo con la densidad de vehículos en las calles y los tipos de caminería.                                  Aunque el estudio de en qué vías se presenta una mayor contaminación según un mayor volumen vehicular es muy prometedor, sucede que alrededor de las cámaras vehiculares y de las estaciones de monitoreo de la red, los tipos de caminería son iguales, imposibilitando un análisis por tipo de caminería, por ejemplo, logrando una comparación entre pavimento y caminos de tierra.
  Evolución en el tiempo de la contaminación del aire relacionándolo con la afectación a las personas que residen en los hogares de los distintos barrios de Montevideo.   Teniendo claro que el objetivo último y más importante de la Red de Monitoreo es poder generar conocimiento que sea utilizado para brindar a los ciudadanos de Montevideo una mejor calidad de aire, se entiende que el análisis de distintas dimensiones relacionadas a la información brindada por la encuesta excede el alcance del proyecto y se prefiere priorizar otros requerimientos.
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Tomando en cuenta los cruzamientos potenciales descartados, las fuentes
de datos descartadas son:

1.  Vías de tránsito

2.  Encuesta continua de hogares

### Especificación de requerimientos funcionales {#esp_requerimientos}

Basados en ambos enfoques y en el estudio de factibilidad se presentan
los requerimientos funcionales acordados con los especialistas de la IM
según las fuentes de datos disponibles y las necesidades identificadas.
Primeramente se especifican los requerimientos funcionales de análisis:

  -------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------- --------------------------------------------------------------------------------------------------------------------------------------------
  ID                                                                                                                                                       Requerimiento Funcional   Descripción
  phantomsection [\[label:rfaid1\]\]{#label:rfaid1 label="label:rfaid1"} [\[label:rfaid1\]](#label:rfaid1){reference-type="ref" reference="label:rfaid1"}                             phantomsection [\[label:rfa1\]\]{#label:rfa1 label="label:rfa1"} [\[label:rfa1\]](#label:rfa1){reference-type="ref" reference="label:rfa1"}
  phantomsection [\[label:rfaid2\]\]{#label:rfaid2 label="label:rfaid2"} [\[label:rfaid2\]](#label:rfaid2){reference-type="ref" reference="label:rfaid2"}                             phantomsection [\[label:rfa2\]\]{#label:rfa2 label="label:rfa2"} [\[label:rfa2\]](#label:rfa2){reference-type="ref" reference="label:rfa2"}
  phantomsection [\[label:rfaid3\]\]{#label:rfaid3 label="label:rfaid3"} [\[label:rfaid3\]](#label:rfaid3){reference-type="ref" reference="label:rfaid3"}                             phantomsection [\[label:rfa3\]\]{#label:rfa3 label="label:rfa3"} [\[label:rfa3\]](#label:rfa3){reference-type="ref" reference="label:rfa3"}
  -------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------- --------------------------------------------------------------------------------------------------------------------------------------------

A continuación se describen los requerimientos funcionales de uso, éstos
son, las herramientas a utilizar por los especialistas de la IM para el
manejo de la plataforma.

  -------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------- --------------------------------------------------------------------------------------------------------------------------------------------
  ID                                                                                                                                                       Requerimiento Funcional   Descripción
  phantomsection [\[label:rfuid1\]\]{#label:rfuid1 label="label:rfuid1"} [\[label:rfuid1\]](#label:rfuid1){reference-type="ref" reference="label:rfuid1"}                             phantomsection [\[label:rfu1\]\]{#label:rfu1 label="label:rfu1"} [\[label:rfu1\]](#label:rfu1){reference-type="ref" reference="label:rfu1"}
  phantomsection [\[label:rfuid2\]\]{#label:rfuid2 label="label:rfuid2"} [\[label:rfuid2\]](#label:rfuid2){reference-type="ref" reference="label:rfuid2"}                             phantomsection [\[label:rfu2\]\]{#label:rfu2 label="label:rfu2"} [\[label:rfu2\]](#label:rfu2){reference-type="ref" reference="label:rfu2"}
  phantomsection [\[label:rfuid3\]\]{#label:rfuid3 label="label:rfuid3"} [\[label:rfuid3\]](#label:rfuid3){reference-type="ref" reference="label:rfuid3"}                             phantomsection [\[label:rfu3\]\]{#label:rfu3 label="label:rfu3"} [\[label:rfu3\]](#label:rfu3){reference-type="ref" reference="label:rfu3"}
  -------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------- --------------------------------------------------------------------------------------------------------------------------------------------

#### [\[label:rfaid1\]](#label:rfaid1){reference-type="ref" reference="label:rfaid1"} - Relación Volumen Vehicular y Contaminación {#sec:reqana1}

*[\[label:rfa1\]](#label:rfa1){reference-type="ref"
reference="label:rfa1"}*

El siguiente requerimiento intenta realizar un análisis sobre uno de los
principales focos de contaminación de aire como es el transporte. El
objetivo del mismo es poder visualizar si a mayor densidad de autos
existe una mayor contaminación.

El mismo surge del cruzamiento de una fuente de datos interna del
Servicio de Calidad de Aire y una fuente de datos externa obtenida del
catálogo de datos abiertos de AGESIC.

Para relacionar el volumen vehicular en las calles de Montevideo con la
contaminación, es necesario investigar en paralelo, con datos horarios,
la emisión de los contaminantes PM2, PM10 o PTS, junto con el volumen de
vehículos que se encuentran alrededor de las estaciones de la red en las
que se realizan las mediciones de dichos contaminantes.

Para tomar datos de casos reales para realizar la investigación, se
define junto a los especialistas del Servicio de Calidad de Aire un
rango de distancia entre una estación de la red y las cámaras de conteo
vehicular. El valor definido es *1km* de radio pero es modificable al
momento de la carga.

En la etapa de carga de datos de contaminación y volumen vehicular se
filtrarán y no se relacionarán los datos obtenidos de estaciones de
monitoreo y cámaras de conteo vehicular que se encuentren a un radio de
más de *1km*.

Analizando las fuentes de datos con las que se cuenta en el momento de
la elaboración del informe, se puede observar que:

Para el conteo vehicular:

1.  Se obtuvieron datos del conteo vehicular del 2017 y 2018, por lo
    tanto se podrá relacionar con las mediciones de contaminación para
    ese período.

2.  Aunque se obtuvo un número considerable de cámaras de conteo
    vehicular, se podrán relacionar sólo las que se encuentren en un
    radio de *1km* con alguna estación de la red.

Para las mediciones de contaminación:

1.  Existen datos de PM2, PM10 y PTS semanales en varias estaciones de
    monitoreo, como Ciudad Vieja y Portones, pero no horarios o por
    minutos como es requerido.

2.  Existen datos horarios de PM10 en Ciudad Vieja y Tres Cruces, pero
    no se encuentran en el mismo período de medición del conteo
    vehicular.

Por lo tanto, al momento de la elaboración de este informe será posible
relacionar:

1.  Mediciones de contaminación de PM10, obtenidas en la estación de la
    red que se encuentra en Tres Cruces para el período 2017.

2.  Datos de conteo vehicular de las cámaras que se encuentran a menos
    de *1km* de la estación de Tres Cruces para el período 2017. Se
    puede visualizar los datos obtenidos en
    [\[fig:estaciones\_de\_la\_red\_camaras\_vehiculares\]](#fig:estaciones_de_la_red_camaras_vehiculares){reference-type="ref"
    reference="fig:estaciones_de_la_red_camaras_vehiculares"}.

![\[\[fig:estaciones\_de\_la\_red\_camaras\_vehiculares\]\]{#fig:estaciones_de_la_red_camaras_vehiculares
label="fig:estaciones_de_la_red_camaras_vehiculares"}Radio de *1km*
alrededor de las estaciones de la red y cámaras
vehiculares](Imagenes/estaciones_de_la_red_camaras_vehiculares.png){width="\\textwidth"}

En el prototipo desarrollado para mostrar la relación entre ambos datos,
se realizó una carga inicial manual y se generó un cubo de ejemplo para
ser visualizado en Saiku, como se puede ver en
[\[fig:prueba\_concepto\_relacion\_contaminacion\_volumen\_vehicular\]](#fig:prueba_concepto_relacion_contaminacion_volumen_vehicular){reference-type="ref"
reference="fig:prueba_concepto_relacion_contaminacion_volumen_vehicular"},
que lograra mostrar básicamente la relación entre ambos datos.

![\[\[fig:prueba\_concepto\_relacion\_contaminacion\_volumen\_vehicular\]\]{#fig:prueba_concepto_relacion_contaminacion_volumen_vehicular
label="fig:prueba_concepto_relacion_contaminacion_volumen_vehicular"}Prototipo
- Relación Contaminación - Volumen
Vehicular](Imagenes/prueba_concepto_relacion_contaminacion_volumen_vehicular.png){width="\\textwidth"}

Algunos puntos interesantes para estudiar serían las estaciones de
monitoreo en el Palacio Legislativo y en Portones de Carrasco pero el
conteo vehicular se tienen datos sólo de 2017 y necesitaríamos datos
horarios de los contaminantes en dichas estaciones de monitoreo. UTE
tiene estos datos horarios pero no se logró obtener los datos al momento
de realizar el informe. En la estación de ANCAP se tienen datos horarios
pero no se tiene conteo vehicular alrededor.

#### [\[label:rfaid2\]](#label:rfaid2){reference-type="ref" reference="label:rfaid2"} - Relación Actividad Industrial y Contaminación {#sec:reqana2}

*[\[label:rfa2\]](#label:rfa2){reference-type="ref"
reference="label:rfa2"}*

El requerimiento pretende realizar un análisis sobre otro de los
principales focos de contaminación de aire como son los procesos
industriales. El objetivo es poder entender si a mayor actividad se
encuentra una mayor contaminación en el aire.

El mismo surge del cruzamiento de una fuente de datos interna del
Servicio de Calidad de Aire y fuentes de datos externas de industrias
obtenidas.

Para relacionar la actividad industrial con la contaminación, es
necesario investigar en paralelo, con datos diarios, la emisión de los
contaminantes PM2, PM10 o PTS, junto con el nivel de actividad de las
industrias que se encuentran alrededor de las estaciones de la red en
las que se realizan las mediciones de dichos contaminantes.

Por lo tanto, para tomar datos de casos reales para realizar la
investigación, se define junto a los especialistas del Servicio de
Calidad de Aire un rango de distancia entre una estación de la red y una
industria. El valor definido es *3km* de radio pero es modificable al
momento de la carga.

En la etapa de carga de datos de contaminación y nivel de actividad se
filtrarán y no se relacionarán los datos obtenidos de estaciones de
monitoreo e industrias que se encuentren a un radio de más de *3km*.

Analizando las fuentes de datos con las que se cuenta en el momento de
la elaboración del informe, se puede observar que:

Para el nivel de actividad:

1.  Dentro de las industrias a investigar, de la cual se logró conseguir
    datos actuales, se encuentra la Central Batlle mediante la
    información provista por Administración del Mercado Eléctrico (ADME)
    [@adme].

2.  Se obtuvieron datos de nivel de actividad desde 2015 por lo tanto se
    podrá relacionar con las mediciones de contaminación para ese
    período.

3.  Aunque existen un número considerable de estaciones de la red, se
    podrán relacionar sólo las que se encuentren en un radio de *3km*
    con la Central Batlle. Para el momento que se realizó el informe, la
    estación de la red en Ciudad Vieja es la única estación en el rango
    de la cual se disponían datos para cruzar.

Para las mediciones de contaminación:

1.  Existen datos de múltiples contaminantes con periodicidad diaria y
    semanal.

Por lo tanto, al momento de la elaboración de este informe será posible
relacionar:

1.  Mediciones de múltiples contaminantes obtenidas en la estación de la
    red que se encuentra en Ciudad Vieja para el período desde 2005
    hasta la fecha.

2.  Datos de la actividad industrial de la Central Batlle desde 2015. Se
    puede visualizar los datos obtenidos en
    [\[fig:estaciones\_de\_la\_red\_central\_batlle\]](#fig:estaciones_de_la_red_central_batlle){reference-type="ref"
    reference="fig:estaciones_de_la_red_central_batlle"}.

![\[\[fig:estaciones\_de\_la\_red\_central\_batlle\]\]{#fig:estaciones_de_la_red_central_batlle
label="fig:estaciones_de_la_red_central_batlle"}Radio de *3km* alrededor
de la Central
Batlle](Imagenes/estaciones_de_la_red_central_batlle.png){width="50%"}

En el prototipo desarrollado para mostrar la relación entre ambos datos,
se realizó una carga inicial manual y se generó un cubo de ejemplo para
ser visualizado en Saiku, como se puede ver en
[\[fig:prueba\_concepto\_relacion\_contaminacion\_actividad\_industrial\_pm2\]](#fig:prueba_concepto_relacion_contaminacion_actividad_industrial_pm2){reference-type="ref"
reference="fig:prueba_concepto_relacion_contaminacion_actividad_industrial_pm2"},
[\[fig:prueba\_concepto\_relacion\_contaminacion\_actividad\_industrial\_hn\]](#fig:prueba_concepto_relacion_contaminacion_actividad_industrial_hn){reference-type="ref"
reference="fig:prueba_concepto_relacion_contaminacion_actividad_industrial_hn"}
y
[\[fig:prueba\_concepto\_relacion\_contaminacion\_actividad\_industrial\_so2\]](#fig:prueba_concepto_relacion_contaminacion_actividad_industrial_so2){reference-type="ref"
reference="fig:prueba_concepto_relacion_contaminacion_actividad_industrial_so2"},
que lograra mostrar básicamente la relación entre ambos datos.

![\[\[fig:prueba\_concepto\_relacion\_contaminacion\_actividad\_industrial\_pm2\]\]{#fig:prueba_concepto_relacion_contaminacion_actividad_industrial_pm2
label="fig:prueba_concepto_relacion_contaminacion_actividad_industrial_pm2"}Prototipo
- Relación Contaminación en PM2.5 - Actividad
Industrial](Imagenes/prueba_concepto_relacion_contaminacion_actividad_industrial_pm2.png){width="\\textwidth"}

![\[\[fig:prueba\_concepto\_relacion\_contaminacion\_actividad\_industrial\_hn\]\]{#fig:prueba_concepto_relacion_contaminacion_actividad_industrial_hn
label="fig:prueba_concepto_relacion_contaminacion_actividad_industrial_hn"}Prototipo
- Relación Contaminación en Humo Negro - Actividad
Industrial](Imagenes/prueba_concepto_relacion_contaminacion_actividad_industrial_hn.png){width="\\textwidth"}

![\[\[fig:prueba\_concepto\_relacion\_contaminacion\_actividad\_industrial\_so2\]\]{#fig:prueba_concepto_relacion_contaminacion_actividad_industrial_so2
label="fig:prueba_concepto_relacion_contaminacion_actividad_industrial_so2"}Prototipo
- Relación Contaminación en SO2 - Actividad
Industrial](Imagenes/prueba_concepto_relacion_contaminacion_actividad_industrial_so2.png){width="\\textwidth"}

#### [\[label:rfaid3\]](#label:rfaid3){reference-type="ref" reference="label:rfaid3"} - Relación Días Especiales y Contaminación {#sec:reqana3}

*[\[label:rfa3\]](#label:rfa3){reference-type="ref"
reference="label:rfa3"}*

El requerimiento pretende realizar un análisis sobre otro de los
principales focos de contaminación de aire como son los procesos de
quema de leña por distintos motivos, en especial, los asados. El
objetivo es poder entender si en los días que se produce una mayor quema
de leña se encuentra una mayor contaminación en el aire.

El mismo surge del cruzamiento de una fuente de datos interna del
Servicio de Calidad de Aire y fuentes de datos externas para obtener los
días festivos, feriados y fechas patria, y del ingreso manual de fechas
con eventos destacables.

Para relacionar los días especiales con la contaminación, es necesario
investigar en paralelo, con datos horarios y diarios, la emisión de los
contaminantes PM2, PM10 o PTS, junto con los días especiales. Cabe
destacar que son relevantes los datos obtenidos de todas las estaciones
de la red.

Por lo tanto, para tomar datos de casos reales para realizar la
investigación, se define junto a los especialistas del Servicio de
Calidad de Aire los días que serán tomamos en cuenta para la realización
del análisis.

Analizando las fuentes de datos con las que se cuenta en el momento de
la elaboración del informe, se puede observar que:

Para los días especiales:

1.  Se obtuvieron datos de los días festivos del Ministerio de Turismo
    (MINTUR) [@horarios_dias_festivos].

2.  Se obtienen e ingresan los días que hay partidos de fútbol
    relevantes (Selección Uruguaya de Fútbol, partidos de los equipos
    grandes).

Para las mediciones de contaminación:

1.  Existen datos de múltiples contaminantes con periodicidad diaria y
    semanal.

Por lo tanto, al momento de la elaboración de este informe será posible
relacionar:

1.  Mediciones de múltiples contaminantes obtenidos en las estaciones de
    la red de monitoreo para el período desde 2005 hasta la fecha.

2.  Días especiales tomados de las fuentes externas y de las ingresadas
    manualmente.

En el prototipo desarrollado para mostrar la relación entre ambos datos,
se realizó una carga inicial manual y se generó un cubo de ejemplo para
ser visualizado en Saiku, como se puede ver en
[\[fig:prueba\_concepto\_relacion\_contaminacion\_dias\_especiales\_pm2\]](#fig:prueba_concepto_relacion_contaminacion_dias_especiales_pm2){reference-type="ref"
reference="fig:prueba_concepto_relacion_contaminacion_dias_especiales_pm2"},
que lograra mostrar básicamente la relación entre ambos datos.

![\[\[fig:prueba\_concepto\_relacion\_contaminacion\_dias\_especiales\_pm2\]\]{#fig:prueba_concepto_relacion_contaminacion_dias_especiales_pm2
label="fig:prueba_concepto_relacion_contaminacion_dias_especiales_pm2"}Prototipo
- Relación Contaminación en PM2.5 - Días
Importantes](Imagenes/prueba_concepto_relacion_contaminacion_dias_especiales_pm2.png){width="\\textwidth"}

#### [\[label:rfuid1\]](#label:rfuid1){reference-type="ref" reference="label:rfuid1"} - Aplicación web de carga y actualización {#sec:requso1}

*[\[label:rfu1\]](#label:rfu1){reference-type="ref"
reference="label:rfu1"}*

Para promover el uso del sistema de BI es necesario brindar herramientas
simples e intuitivas para las tareas que son indispensables de realizar
periódicamente para su gestión, como lo son la carga y actualización de
los datos desde las fuentes. Para cumplir dicho motivo se disponibiliza
una aplicación web fácilmente accesible.

#### [\[label:rfuid2\]](#label:rfuid2){reference-type="ref" reference="label:rfuid2"} - Generación de reporte de BI de sección en Informe Anual {#sec:requso2}

*[\[label:rfu2\]](#label:rfu2){reference-type="ref"
reference="label:rfu2"}*

Actualmente, los especialistas del servicio ECCA, generan manualmente la
información, estadísticas y reportes de la sección Resultados de Red de
Monitoreo del Informe Anual como se visualiza en
[\[fig:informe\_anual\]](#fig:informe_anual){reference-type="ref"
reference="fig:informe_anual"}. Se espera la posibilidad de generar
dicho reporte de BI de la sección a demanda, desde aplicativo web a
implementar, para con los datos que se encuentren en el DW para el año
indicado.

![\[\[fig:informe\_anual\]\]{#fig:informe_anual
label="fig:informe_anual"}Sección Resultados de Red de Monitoreo -
Informe Anual](Imagenes/informe_anual.png){width="60%"}

#### [\[label:rfuid3\]](#label:rfuid3){reference-type="ref" reference="label:rfuid3"} - Generación de un dashboard para análisis {#sec:requso3}

*[\[label:rfu3\]](#label:rfu3){reference-type="ref"
reference="label:rfu3"}*

Con el objetivo de brindar herramientas de BI visuales para descubrir
insights que logren retratar fielmente el estado de la calidad de aire
en Montevideo mediante un acceso eficaz y eficiente a la información, se
genera un Dashboard con gráficas e indicadores pre-establecidos para
poder ser consultado de manera rápida e intuitiva.

### Especificación de requerimientos no funcionales {#esp_requerimientos_no_funcionales}

Basados en ambos enfoques y en el estudio de factibilidad se presentan
los requerimientos no funcionales acordados con los especialistas de la
IM que deberá cumplir el sistema.

1.  Implementar la solución utilizando la suite de Pentaho Community
    Edition (CE).

2.  Funcionar en arquitecturas de varios niveles.

3.  Mantener una relación adecuada con Bases de Datos (BDs) Fuentes:

    1.  Acceso a BDs heterogéneas y multiplataforma.

    2.  Independiente de los Sistemas de Producción.

4.  Proveer documentación técnica detallada del sistema, su instalación,
    configuración, inicialización y monitoreo para su posterior gestión,
    actualización y soporte por parte del Servicio de Calidad de Aire.

5.  Proveer documentación funcional del sistema, un manual de usuario y
    tutoriales web para su posterior utilización por parte del Servicio
    de Calidad de Aire.
