Interfaz de usuario {#interfaz_usuario_data_warehouse}
-------------------

Debido a que la plataforma de BI presentada será de uso exclusivo de los
especialistas de la IM, delegándose por completo su carga, actualización
y utilización, es necesario brindar distintas herramientas que sirvan a
cada caso.

### Aplicación web de carga, actualización y reportes {#sec:carga_actualizacion}

Con el fin de brindar una herramienta que facilite la carga y
actualización del DW y mediante la cual se pueda generar los reportes de
BI requeridos, se implementó una aplicación web que permite realizar
dichas tareas de forma centralizada. Basado en lineamientos
estandarizados de diseño y experiencia de usuario, se provee una
interfaz limpia e intuitiva para la gestión de los datos del DW y la
generación de reportes de BI.

En dicha aplicación web es posible:

1.  Realizar la gestión de datos del DW.

2.  Ejecutar la generación de un reporte de BI de la sección del Informe
    Anual.

#### Carga y actualización {#sec:carga_actualizacion}

Para realizar la gestión de los datos del DW se visualizan y disponen
dos opciones bien diferenciadas:

1.  Realizar una carga inicial del DW para inicializarlo.

2.  Ejecutar una actualización del DW con nuevos datos que pueden ser
    cargados directamente en la web.

En la
[\[fig:analisis\_datos\_web\]](#fig:analisis_datos_web){reference-type="ref"
reference="fig:analisis_datos_web"} se muestra la pantalla de inicio de
la aplicación y los distintos items del menú:

![\[\[fig:analisis\_datos\_web\]\]{#fig:analisis_datos_web
label="fig:analisis_datos_web"}Aplicación web - Carga y
actualización](Imagenes/analisis_datos_web.png){width="\\textwidth"}

#### Generación de reporte de BI de sección en Informe Anual {#sec:generacion_seccion_informe}

Como requerimiento funcional de uso, específicamente
[\[label:rfuid2\]](#label:rfuid2){reference-type="ref"
reference="label:rfuid2"}, se dispone una acción dentro del aplicativo
web para ejecutar la generación de un reporte de BI de la sección del
Informe Anual para el año que se indique con los datos que se encuentren
almacenados en el DW.

A continuación, en
[\[fig:analisis\_datos\_informe\]](#fig:analisis_datos_informe){reference-type="ref"
reference="fig:analisis_datos_informe"}, se presenta una muestra de la
sección del informe generado:

![\[\[fig:analisis\_datos\_informe\]\]{#fig:analisis_datos_informe
label="fig:analisis_datos_informe"}Aplicación web - Reporte de BI de
sección del Informe
Anual](Imagenes/analisis_datos_informe.png){width="\\textwidth"}

### Análisis {#sec:interfaz_analisis}

Con el objetivo de lograr flexibilidad y completitud para la realización
del análisis de datos sobre los requerimientos definidos y basados en el
antipatrón de no reimplementar componentes que se pueden conseguir
prefabricando de antemano, se utilizan distintas herramientas provistas
por la suite de Pentaho:

#### Saiku {#sec:saiku}

Para poder realizar consultas de forma dinámica, logrando la mayor
flexibilidad posible para analizar los datos, se definen y cargan
múltiples cubos, uno por cada requerimiento definido, y se
disponibilizan para su uso.

**Vehículos Contaminación**

En la
[\[fig:analisis\_datos\_relacion\_contaminacion\_volumen\_vehicular\]](#fig:analisis_datos_relacion_contaminacion_volumen_vehicular){reference-type="ref"
reference="fig:analisis_datos_relacion_contaminacion_volumen_vehicular"}
se muestra cómo se visualiza la relación entre el volumen vehicular y la
contaminación según las distintas horas del día:

![\[\[fig:analisis\_datos\_relacion\_contaminacion\_volumen\_vehicular\]\]{#fig:analisis_datos_relacion_contaminacion_volumen_vehicular
label="fig:analisis_datos_relacion_contaminacion_volumen_vehicular"}Análisis
de Datos - Relación Contaminación - Volumen
Vehicular](Imagenes/prueba_concepto_relacion_contaminacion_volumen_vehicular.png){width="\\textwidth"}

**Industrias Contaminación**

En la
[\[fig:analisis\_datos\_relacion\_contaminacion\_actividad\_industrial\_pm2\]](#fig:analisis_datos_relacion_contaminacion_actividad_industrial_pm2){reference-type="ref"
reference="fig:analisis_datos_relacion_contaminacion_actividad_industrial_pm2"}
se muestra cómo se visualiza, en los distintos días del año, la relación
entre la actividad industrial de la Central Batlle y la contaminación de
PM2:

![\[\[fig:analisis\_datos\_relacion\_contaminacion\_actividad\_industrial\_pm2\]\]{#fig:analisis_datos_relacion_contaminacion_actividad_industrial_pm2
label="fig:analisis_datos_relacion_contaminacion_actividad_industrial_pm2"}Análisis
de Datos - Relación Contaminación en PM2.5 - Actividad
Industrial](Imagenes/prueba_concepto_relacion_contaminacion_actividad_industrial_pm2.png){width="\\textwidth"}

En la
[\[fig:analisis\_datos\_relacion\_contaminacion\_actividad\_industrial\_pm2\]](#fig:analisis_datos_relacion_contaminacion_actividad_industrial_pm2){reference-type="ref"
reference="fig:analisis_datos_relacion_contaminacion_actividad_industrial_pm2"}
se muestra cómo se visualiza, en los distintos días del año, la relación
entre la actividad industrial de la Central Batlle y la contaminación de
HN:

![\[\[fig:analisis\_datos\_relacion\_contaminacion\_actividad\_industrial\_hn\]\]{#fig:analisis_datos_relacion_contaminacion_actividad_industrial_hn
label="fig:analisis_datos_relacion_contaminacion_actividad_industrial_hn"}Análisis
de Datos - Relación Contaminación en Humo Negro - Actividad
Industrial](Imagenes/prueba_concepto_relacion_contaminacion_actividad_industrial_hn.png){width="\\textwidth"}

En la
[\[fig:analisis\_datos\_relacion\_contaminacion\_actividad\_industrial\_so2\]](#fig:analisis_datos_relacion_contaminacion_actividad_industrial_so2){reference-type="ref"
reference="fig:analisis_datos_relacion_contaminacion_actividad_industrial_so2"}
se muestra cómo se visualiza, en los distintos días del año, la relación
entre la actividad industrial de la Central Batlle y la contaminación de
SO2:

![\[\[fig:analisis\_datos\_relacion\_contaminacion\_actividad\_industrial\_so2\]\]{#fig:analisis_datos_relacion_contaminacion_actividad_industrial_so2
label="fig:analisis_datos_relacion_contaminacion_actividad_industrial_so2"}Análisis
de Datos - Relación Contaminación en SO2 - Actividad
Industrial](Imagenes/prueba_concepto_relacion_contaminacion_actividad_industrial_so2.png){width="\\textwidth"}

**Días Importantes Contaminación**

En la
[\[fig:analisis\_datos\_relacion\_contaminacion\_dias\_especiales\_pm2\]](#fig:analisis_datos_relacion_contaminacion_dias_especiales_pm2){reference-type="ref"
reference="fig:analisis_datos_relacion_contaminacion_dias_especiales_pm2"}
se muestra cómo se comporta la contaminación de PM2 en los días
importantes del año:

![\[\[fig:analisis\_datos\_relacion\_contaminacion\_dias\_especiales\_pm2\]\]{#fig:analisis_datos_relacion_contaminacion_dias_especiales_pm2
label="fig:analisis_datos_relacion_contaminacion_dias_especiales_pm2"}Análisis
de Datos - Relación Contaminación en PM2.5 - Días
Importantes](Imagenes/prueba_concepto_relacion_contaminacion_dias_especiales_pm2.png){width="\\textwidth"}

#### Pentaho Dashboard {#sec:dashboard}

Con el objetivo de brindar un acceso eficaz y eficiente a la información
se genera un dashboard con gráficas e indicadores preestablecidos para
poder ser consultado de manera rápida e intuitiva.

En la
[\[fig:analisis\_datos\_dashboard\]](#fig:analisis_datos_dashboard){reference-type="ref"
reference="fig:analisis_datos_dashboard"} se muestran las distintas
gráficas e indicadores del dashboard:

![\[\[fig:analisis\_datos\_dashboard\]\]{#fig:analisis_datos_dashboard
label="fig:analisis_datos_dashboard"}Análisis de Datos -
Dashboard](Imagenes/analisis_datos_dashboard.png){width="\\textwidth"}

Dentro de las posibilidades brindadas por los dashboards es posible
estructuras los datos geográficos, visualizando los datos desplegados en
mapas.

En la
[\[fig:analisis\_datos\_dashboard\_mapas\]](#fig:analisis_datos_dashboard_mapas){reference-type="ref"
reference="fig:analisis_datos_dashboard_mapas"} se presenta una
visualización utilizando un mapa identificando las estaciones de
monitoreo en la ciudad de Montevideo:

![\[\[fig:analisis\_datos\_dashboard\_mapas\]\]{#fig:analisis_datos_dashboard_mapas
label="fig:analisis_datos_dashboard_mapas"}Análisis de Datos - Dashboard
-
Mapas](Imagenes/analisis_datos_dashboard_mapas.png){width="\\textwidth"}
