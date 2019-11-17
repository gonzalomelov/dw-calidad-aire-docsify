Arquitectura {#arquitectura_data_warehouse}
------------

Luego del análisis realizado de los requerimientos funcionales y no
funcionales es necesario definir la base de herramientas y componentes
que compondrán la arquitectura del sistema de BI.

Como se puede identificar en la
[\[fig:arquitectura\_del\_sdw\]](#fig:arquitectura_del_sdw){reference-type="ref"
reference="fig:arquitectura_del_sdw"}, donde se pueden visualizar los
distintos componentes que forman parte de cada capa, se presenta una
arquitectura en varios niveles, logrando desacoplar las
responsabilidades de cada nivel. Fuentes de datos, integración y
limpieza, repositorio de datos, herramientas de análisis de datos y
metadatos, son algunos de los niveles identificados.

![\[\[fig:arquitectura\_del\_sdw\]\]{#fig:arquitectura_del_sdw
label="fig:arquitectura_del_sdw"}Arquitectura sistema de
BI](Imagenes/arquitectura_del_sdw.png){width="\\textwidth"}

### Fuentes de datos {#arquitectura_data_sources}

La capa de Fuentes de datos representa las diferentes fuentes de datos
que alimentan los datos del DW. La fuente de datos puede estar en
cualquier formato: archivo de texto plano, base de datos relacional,
otros tipos de base de datos, archivo Excel, etc.

Como se explicitó en la etapa de Análisis, y se muestra en
[\[fig:arquitectura\_del\_sdw\_fuentes\_de\_datos\]](#fig:arquitectura_del_sdw_fuentes_de_datos){reference-type="ref"
reference="fig:arquitectura_del_sdw_fuentes_de_datos"}, se logran
identificar fuentes de datos internas del Servicio de Calidad de Aire y
externas de Datos Abiertos, ANCAP y ADME.

![\[\[fig:arquitectura\_del\_sdw\_fuentes\_de\_datos\]\]{#fig:arquitectura_del_sdw_fuentes_de_datos
label="fig:arquitectura_del_sdw_fuentes_de_datos"}Fuentes de
Datos](Imagenes/arquitectura_del_sdw_fuentes_de_datos.png){width="40%"}

### Back-end {#arquitectura_back_end}

La capa de Back-end, ver
[\[fig:arquitectura\_del\_sdw\_backend\]](#fig:arquitectura_del_sdw_backend){reference-type="ref"
reference="fig:arquitectura_del_sdw_backend"}, contiene tres secciones
importantes: Capa de extracción de datos, Área de pruebas y procesos
ETL.

Dentro del Área de pruebas (Data Staging) podemos visualizar las
distintas tablas basadas en las fuentes de datos que se identificaron,
tanto internas como externas.

En los procesos de ETL se define uno por cada requerimiento
identificado.

![\[\[fig:arquitectura\_del\_sdw\_backend\]\]{#fig:arquitectura_del_sdw_backend
label="fig:arquitectura_del_sdw_backend"}Back-end](Imagenes/arquitectura_del_sdw_backend.png){width="60%"}

### DW {#arquitectura_data_warehouse}

En la capa de almacenamiento de datos se tiene una base de datos
relacional que oficia de repositorio de datos.

En el mismo se pueden diferenciar dos grandes grupos: las tablas que
sirven como Dimensiones y las que sirven como Hechos, como se muestra en
[\[fig:arquitectura\_del\_sdw\_data\_warehouse\]](#fig:arquitectura_del_sdw_data_warehouse){reference-type="ref"
reference="fig:arquitectura_del_sdw_data_warehouse"}.

![\[\[fig:arquitectura\_del\_sdw\_data\_warehouse\]\]{#fig:arquitectura_del_sdw_data_warehouse
label="fig:arquitectura_del_sdw_data_warehouse"}DW](Imagenes/arquitectura_del_sdw_data_warehouse.png){width="60%"}

### OLAP {#arquitectura_olap}

En la capa OLAP se mantienen las reglas de negocio que se aplican a la
información almacenada en el Enterprise DW para ser presentada de forma
intuitiva por las herramientas de análisis de datos.

En el mismo, ver
[\[fig:arquitectura\_del\_sdw\_olap\]](#fig:arquitectura_del_sdw_olap){reference-type="ref"
reference="fig:arquitectura_del_sdw_olap"}, se definen tres cubos, uno
por cada requerimiento identificado.

![\[\[fig:arquitectura\_del\_sdw\_olap\]\]{#fig:arquitectura_del_sdw_olap
label="fig:arquitectura_del_sdw_olap"}OLAP](Imagenes/arquitectura_del_sdw_olap.png){width="30%"}

### Front-end {#arquitectura_front_end}

Finalmente, en la capa de análisis de datos, se ofrecen al usuario
herramientas con los siguientes objetivos:

1.  Mecanismos de acceso a la información eficaces.

2.  Tener conexión eficaz al DW.

Primero se utiliza Saiku, una herramienta de la suite Pentaho, para que
los especialistas puedan realizar las consultas de forma dinámica
logrando la mayor flexibilidad posible para analizar los datos.

A su vez, se disponibiliza la capacidad de generar un informe, similar
al publicado anualmente, para automatizar la generación del mismo.

Finalmente, se genera un dashboard a medida para poder visualizar de
forma rápida y directa los indicadores preestablecidos.

En la siguiente
[\[fig:arquitectura\_del\_sdw\_frontend\]](#fig:arquitectura_del_sdw_frontend){reference-type="ref"
reference="fig:arquitectura_del_sdw_frontend"} se pueden diferenciar las
distintas herramientas de análisis.

![\[\[fig:arquitectura\_del\_sdw\_frontend\]\]{#fig:arquitectura_del_sdw_frontend
label="fig:arquitectura_del_sdw_frontend"}Front-end](Imagenes/arquitectura_del_sdw_frontend.png){width="80%"}

### Metadatos {#arquitectura_metadatos}

Horizontalmente, ver
[\[fig:arquitectura\_del\_sdw\_metadatos\]](#fig:arquitectura_del_sdw_metadatos){reference-type="ref"
reference="fig:arquitectura_del_sdw_metadatos"}, se puede visualizar la
capa de metadatos donde la información sobre los datos almacenados en el
sistema de BI es almacenada.

![\[\[fig:arquitectura\_del\_sdw\_metadatos\]\]{#fig:arquitectura_del_sdw_metadatos
label="fig:arquitectura_del_sdw_metadatos"}Metadatos](Imagenes/arquitectura_del_sdw_metadatos.png){width="30%"}

### Operaciones del sistema {#arquitectura_operations}

Esta capa incluye información sobre cómo está funcionando el sistema de
BI, cuál es el estado de trabajo ETL, cuál es el rendimiento del sistema
y el historial de acceso de los usuarios.

Como se puede visualizar en
[\[fig:arquitectura\_del\_sdw\_operaciones\]](#fig:arquitectura_del_sdw_operaciones){reference-type="ref"
reference="fig:arquitectura_del_sdw_operaciones"}, en esta capa se
pueden visualizar múltiples elementos de operaciones que sirven para el
monitoreo:

1.  Monitoreo de solución en Docker Host mediante Grafana [@grafana] y
    Prometheus [@prometheus].

2.  Status de PBI.

3.  Status de PDI (Carte).

4.  Aplicación web desarrollada a medida.

![\[\[fig:arquitectura\_del\_sdw\_operaciones\]\]{#fig:arquitectura_del_sdw_operaciones
label="fig:arquitectura_del_sdw_operaciones"}Operaciones](Imagenes/arquitectura_del_sdw_operaciones.png){width="30%"}
