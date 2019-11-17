Introducción {#introduction}
============

Montevideo tiene --en líneas generales-- una buena calidad de aire. La
predominancia de vientos, el suave relieve donde no destacan accidentes
topográficos de importancia y la cercanía del Río de la Plata proveen
una situación favorable para la dispersión natural de posibles
contaminantes.

La calidad del aire de una ciudad se ve presionada constantemente por
las numerosas actividades que en ella se desarrollan. Estas incluyen la
quema de combustible para el transporte y la industria; el uso de leña
tanto en el área comercial como residencial para la calefacción y
cocción de alimentos, la generación de energía eléctrica a partir de
centrales térmicas y quema de residuos a cielo abierto, entre otras.

Es evidente que todas estas actividades conviven en Montevideo y son
responsables de que se emitan continuamente gases y partículas con
potencial impacto en la calidad del aire. Por tanto, es posible que, en
algunas oportunidades, la capacidad depuradora natural no sea suficiente
y en algunas zonas de la ciudad se observe mayor concentración de
contaminantes, lo que eventualmente podría hacer que la calidad de aire
fuera inadecuada.

Por esta situación resulta imprescindible que la IM mantenga el
monitoreo y evaluación de la calidad de aire en forma continua, una
tarea que realiza a través de la Unidad Calidad de Aire del Servicio de
Evaluación de la Calidad y Control Ambiental (ECCA).

Para desarrollar este cometido se ha implementado un programa de
monitoreo de calidad del aire, que incluye una Red de Monitoreo que
comenzó a operar en 2005.

Las distintas estaciones realizan mediciones que luego son extraídos y
estudiados de manualmente por los especialistas de la IM y su equipo, a
saber, Ing. Quím. Andrea De Nigris (<andrea.denigris@imm.gub.uy>) y Ing.
Quím. Pablo Franco (<pablo.franco@imm.gub.uy>).

Este trabajo se plantea como objetivo desarrollar sistema de BI que
permita la automatización de la extracción, integración, limpieza y
carga de los datos y brinde una interfaz a medida para que los usuarios
puedan analizar toda la información de interés.

En este capítulo se presenta el alcance del proyectos y finalmente se
especifica la estructura del informe.

Alcance del proyecto {#sec:alcance_proy}
--------------------

Este proyecto tiene como objetivo desarrollar e implantar una
herramienta de BI para el análisis de información relativa a la calidad
del aire en Montevideo.

### Objetivos {#sec:alcance_proy_objetivos}

Entre los distintos objetivos del proyecto se pueden identificar:

1.  Lograr integrar datos de distintas fuentes de interés para los
    especialistas de la IM.

2.  Proveer una interfaz sencilla que permita las cargas sucesivas de
    los datos al DW.

3.  Proveer diferentes herramientas de BI, implementadas a medida de los
    requerimientos de los usuarios, para el análisis de los datos,
    incluyendo herramientas Online Analytical Processing (OLAP)
    [@marotta2017dcdw], tableros de control, reportes, visualización de
    los datos desplegados en mapas, etc.

4.  Lograr satisfacer los requerimientos de análisis de los usuarios y
    sea amigable en su utilización.

### Resultados esperados {#sec:alcance_proy_resultados_esperados}

Los resultados esperados son:

1.  Prototipo de la herramienta de BI.

2.  Documentación del proyecto y manual de la herramienta.

3.  Adquisición por parte de los estudiantes de conocimiento a fondo de
    los problemas y soluciones en la implementación de este tipo de
    sistemas.

Estructura del informe {#sec:estruc_info}
----------------------

El resto del informe tiene la siguiente estructura:

En el segundo capítulo consta de una introducción a la Red de Monitoreo
de Calidad de Aire de Montevideo donde se brinda un acercamiento al
contexto del proyecto.

En el tercer capítulo se brinda un abordaje teórico de los sistemas de
BI y DW. Además se presentan las herramientas y tecnologías utilizadas
en la plataforma.

El cuarto capítulo concentra completamente el . En el mismo se
encuentran las principales etapas del proceso como donde se encuentran
la especificación de requerimientos y obtención de datos fuente, pasando
por el diseño y carga del DW en , la , , hasta las herramientas de
análisis de BI utilizadas por los usuarios finales en .

El quinto capítulo engloba los aspectos relacionados a la instalación,
monitorización y uso del sistema.

Posteriormente, el sexto capítulo consta de las conclusiones logradas
del trabajo y una visión de los próximos puntos de acción.

Al final se detalla la bibliografía utilizada y se anexa el contenido
agregado que sirve a brindar la completitud de la documentación del
sistema.