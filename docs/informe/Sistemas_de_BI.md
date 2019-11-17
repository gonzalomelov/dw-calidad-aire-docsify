Marco teórico {#marc_teor}
=============

En el presente capítulo se introducen los conceptos fundamentales
necesarios para el entendimiento del proyecto.

Introducción a los sistemas de BI {#business_intelligence}
---------------------------------

El contexto de la sociedad de la información ha propiciado la necesidad
de tener mejores, más rápidos y más eficientes métodos para extraer y
transformar los datos de una organización en información y distribuirla
a lo largo de la cadena de valor.

El Business Intelligence responde a dicha necesidad. Sin embargo, este
concepto, que actualmente se considera crítico en la gran mayoría de
empresas, no es nuevo. Desde hace décadas el concepto ha evolucionado
aunando diferentes tecnologías, metodologías y términos bajo su
paraguas.

Actualmente se entiende por Business Intelligence al conjunto de
metodologías, aplicaciones, prácticas y capacidades enfocadas a la
creación y administración de información que permite tomar mejores
decisiones a los usuarios de una organización [@diaz2012introduccion].

En los últimos años, el mercado Business Intelligence se ha visto
marcado por una clara evolución que lo destaca como un mercado maduro:

1.  Se ha producido una consolidación del mercado mediante la compra de
    empresas pequeñas por parte de los principales agentes del mercado
    (SAP, IBM, Microsoft y Oracle).

2.  Pentaho, una de las plataformas open source más completas y en la
    cual se basa la solución de este proyecto, fue adquirida por Hitachi
    en 2015.

3.  Se ha enriquecido con soluciones open source que cubren el espectro
    de necesidades de una organización para la explotación de la
    información.

4.  Han aparecido nuevas empresas con foco en la innovación cubriendo
    nuevos nichos en el mercado de la inteligencia de negocio como la
    visualización, el análisis predictivo, los contenedores livianos y/o
    el Business Intelligence en tiempo real.

5.  A pesar de los momentos de la crisis económica el mercado de
    inteligencia de negocio sigue en una fase de crecimiento estable al
    posicionarse como una necesidad crítica para toda organización.

Como se puede visualizar en el cuadrante mágico de Gartner
[\[fig:gartner\]](#fig:gartner){reference-type="ref"
reference="fig:gartner"} para herramientas de integración de datos en
Agosto 2019, Hitachi Vantara (Pentaho) se posiciona como un una empresas
de nicho. En la misma se diferencian del resto en que normalmente están
especializados en segmentos muy específicos de su mercado o trabajan
exclusivamente en sectores verticalizados.

![\[\[fig:gartner\]\]{#fig:gartner label="fig:gartner"}Cuadrante mágico de
Gartner
[@Magic_Quadrant_for_Data_Integration_Tools]](Imagenes/gartner.jpg){width="70%"}

La implantación de estos sistemas de información proporciona diversos
beneficios, entre los que podemos destacar:

1.  Crear un círculo virtuoso de la información
    [\[fig:circulo\_virtuoso\]](#fig:circulo_virtuoso){reference-type="ref"
    reference="fig:circulo_virtuoso"} (los datos se transforman en
    información que genera un conocimiento que permite tomar mejores
    decisiones que se traducen en mejores resultados y que generan
    nuevos datos).

2.  Permitir una visión única, conformada, histórica, persistente y de
    calidad de toda la información.

3.  Crear, manejar y mantener métricas, Key Perfomance Indicador (KPI) y
    Key Goal Indicator (KGI) fundamentales para la empresa.

4.  Aportar información actualizada tanto a nivel agregado como en
    detalle.

5.  Reducir el diferencial de orientación de negocio entre el
    departamento TI y la organización.

6.  Mejorar comprensión y documentación de los sistemas de información
    en el contexto de una organización.

7.  Mejorar de la competitividad de la organización como resultado de
    ser capaces de:

    1.  Diferenciar lo relevante sobre lo superfluo.

    2.  Acceder más rápido a información.

    3.  Tener mayor agilidad en la toma de las decisiones.

![\[\[fig:circulo\_virtuoso\]\]{#fig:circulo_virtuoso
label="fig:circulo_virtuoso"}Círculo Virtuoso - Análisis de
Datos](Imagenes/circulo_virtuoso.png){width="60%"}

Proceso de desarrollo de los sistemas de BI {#business_intelligence_development_process}
-------------------------------------------

La Metodología Kimball, empleada para la construcción de un sistema de
BI y DW, se basa en el Ciclo de Vida Dimensional del Negocio (Business
Dimensional Lifecycle).

Este ciclo de vida del proyecto de BI, está basado en cuatro principios
básicos:

1.  Centrarse en el negocio.

2.  Construir una infraestructura de información adecuada.

3.  Realizar entregas en incrementos significativos (este principio
    consiste en crear el DW en incrementos entregables en plazos de 6 a
    12 meses, en este punto, la metodología se parece a las metodologías
    ágiles de construcción de software).

4.  Ofrecer la solución completa con todos los elementos necesarios para
    entregar valor a los usuarios de negocios:

    1.  Centrarse en el negocio.

    2.  DW bien diseñado.

    3.  Entregar herramientas de consulta ad hoc.

    4.  Aplicaciones para informes y análisis avanzado.

    5.  Capacitación.

    6.  Soporte.

    7.  Sitio web.

    8.  Documentación.

La construcción de una solución de BI y DW es sumamente compleja, y
Kimball propone una metodología que ayuda a simplificar esa complejidad.
Las tareas de esta metodología (ciclo de vida) se describen en
[\[fig:kimball\]](#fig:kimball){reference-type="ref"
reference="fig:kimball"}:

![\[\[fig:kimball\]\]{#fig:kimball label="fig:kimball"}Ciclo de Vida
Dimensional del Negocio](Imagenes/kimball.jpg){width="70%"}

### Planificación y Arquitectura {#sec:business_intelligence_development_process_planning_architecture}

El primer recuadro en el Ciclo de Vida Dimensional del Negocio se centra
en conseguir lanzar el proyecto, incluyendo la determinación del
alcance, la justificación y la dotación de personal. A lo largo del
ciclo de vida, la planificación y la dirección de las tareas del
proyecto mantiene las actividades en marcha.

Los entornos BI/DW se encargan de la integración de numerosas
tecnologías, almacenes de datos y metadatos asociados. La ruta de la
tecnología en el Ciclo de Vida Dimensional del Negocio empieza con el
diseño del sistema de arquitectura para establecer una lista de la
obtención de las capacidades necesarias, seguidas de la selección e
instalación de productos que satisfagan esas necesidades de la
arquitectura.

#### Planificación del Proyecto

En este proceso se determina el propósito del proyecto de BI/DW, sus
objetivos específicos y el alcance del mismo, los principales riesgos y
una aproximación inicial a las necesidades de información.

Esta tarea incluye las siguientes acciones típicas de un plan de
proyecto:

1.  Definir el alcance (entender los requerimientos del negocio).

2.  Identificar las tareas.

3.  Programar las tareas.

4.  Planificar el uso de los recursos.

5.  Asignar la carga de trabajo a los recursos.

6.  Elaboración de un documento final que representa un plan del
    proyecto.

Además en esta parte definimos cómo realizar la administración o gestión
con las siguientes actividades:

1.  Monitoreo del estado de los procesos y actividades.

2.  Rastreo de problemas.

3.  Desarrollo de un plan de comunicación comprensiva que direccione la
    empresa y las áreas de TI.

#### Definición de Requerimientos del Negocio

Identificar las necesidades del negocio es una tarea clave en el ciclo
de vida Kimball ya que estos descubrimientos dirigen la mayoría de
decisiones ascendentes y descendentes. Las necesidades se recogen para
determinar los factores clave que repercuten en el negocio centrándose
en lo que los usuarios de negocio hacen hoy (o lo que quieren hacer en
el futuro) en lugar de preguntar "¿Qué quieres almacenar en el almacén
de datos?", se identifican las oportunidades más significativas en la
empresa, basándose en el valor del negocio y su viabilidad.
Posteriormente las necesidades detalladas son recopiladas en la primera
iteración del sistema de desarrollo BI/DW.

En la etapa de relevamiento de requerimientos se pueden utilizar
distintos enfoques para el análisis según las capacidades y
posibilidades de los datos, del equipo y del proyecto en si.

*Enfoque desde Requerimientos*

En el enfoque desde requerimientos se descubren junto a los usuarios del
proyecto los requerimientos de negocio que necesitan. Dicho enfoque
tiene las siguientes características:

1.  Los requerimientos son el universo de información.

2.  Las bases fuente se relacionarán luego.

3.  Aplicable cuando se tienen Bases Fuentes complejas. (Se analizan con
    los requerimientos en mente).

*Enfoque desde Datos*

En el enfoque desde los datos se analizan los datos fuentes para
visualizar qué respuestas pueden brindar para el negocio. Dicho enfoque
tiene las siguientes características:

1.  Datos fuentes son el universo de información.

2.  El DW se obtiene transformando las fuentes.

3.  Aplicable cuando los requerimientos están poco claros.

#### Gestión de Proyecto

Esta fase tiene como objetivo hacer un seguimiento constante a las
actividades, los progresos obtenidos y los riesgos que se pueden
presentar durante todo el proyecto. En la metodología de Kimball se
incluye una fase de gestión del proyecto, en la cual se realizan las
siguientes actividades:

1.  Reunión de información del estado del proyecto.

2.  Revisar el plan de proyecto.

3.  Administrar el alcance del proyecto.

4.  Controlar los cambios.

5.  Desarrollar un plan de comunicaciones.

#### Diseño de la Arquitectura Técnica

El área de arquitectura técnica cubre los procesos y herramientas que se
aplican a los datos. En el área técnica existen distintos conjuntos que
tienen distintos requerimientos, brindan sus propios servicios y
componentes de almacenaje de datos.

En la
[\[fig:arquitectura\_malinowski\]](#fig:arquitectura_malinowski){reference-type="ref"
reference="fig:arquitectura_malinowski"} se puede observar la
arquitectura típica de un Data Warehouse según Malinowski
[@malinowski2008advanced], que consta de los siguientes componentes:

![\[\[fig:arquitectura\_malinowski\]\]{#fig:arquitectura_malinowski
label="fig:arquitectura_malinowski"}
Arquitectura](Imagenes/arquitectura_malinowski.png){width="80%"}

*Fuentes de datos*

Esta representa las diferentes fuentes de datos que alimentan los datos
del DW. La fuente de datos puede estar en cualquier formato: archivo de
texto plano, base de datos relacional, otros tipos de base de datos,
archivo Excel, etc. Las mismas pueden ser internas o externas a la
organización.

*Capa back-end*

Está compuesta por herramientas de ETL de datos, utilizadas para
alimentar el DW. A continuación se detallan los tres pasos de este
proceso:

1.  Extracción: recopilación de datos de diversas fuentes. Las mismas
    pueden ser bases de datos relacionales u otras fuentes con distintos
    formatos.

2.  Transformación: conversión de los datos del formato de la fuente al
    formato del DW. Incluye tareas de depuración, filtrado, integración
    y agregación de los mismos.

3.  Carga: carga del DW con los datos transformados. Además, comprende
    tareas de actualización periódica del mismo.

Adicionalmente, puede incluir una base de datos temporal sobre la cual
se ejecutan todos los procesos de integración y transformación de datos,
antes de realizar la carga del DW. Esto es lo que se conoce como Data
Staging.

*Capa DW*

Está compuesta por un DW corporativo y/o varios Data Marts, y un
repositorio de metadata que almacena información sobre el DW y su
contenido. Un DW corporativo es un DW centralizado que abarca todas las
áreas funcionales y departamentos de una organización. Por otra parte,
un Data Mart es un DW especializado, orientado hacia un área funcional
particular o un grupo de usuarios en una organización.

*Capa OLAP*

Servidor OLAP que soporta tanto datos multidimensionales como sus
operaciones. Se pueden distinguir distintos tipos de servidores OLAP,
según la forma en que almacenan los datos:

1.  Relational OLAP (ROLAP): almacena los datos en un motor relacional.

2.  Multidimensional OLAP (MOLAP): trabaja sobre almacenamiento
    especializado.

3.  Hybrid OLAP (HOLAP): combina ambas estrategias.

*Capa front-end*

Está compuesta por herramientas clientes, como por ejemplo herramientas
OLAP, de estadísticas y generación de reportes, que permiten visualizar
y analizar interactivamente el contenido del DW.

#### Selección de Productos e Instalación

Durante la fase de selección de productos, Kimball propone hacer una
investigación exhaustiva acerca de los productos que se encuentran
disponibles en el mercado, y opcionalmente desarrollar prototipos para
conocer la forma en la que productos satisfacen sus necesidades.

### Modelado de Datos e Integración {#sec:business_intelligence_development_process_design}

La ruta de datos en el Ciclo de Vida Dimensional del Negocio empieza con
el diseño de un modelo dimensional como objetivo para enfrentarse a los
requisitos del negocio, mientras consideramos las realidades de datos
subyacentes. El mundo Kimball es sinónimo del modelo dimensional donde
los datos se dividen en medidas o dimensiones descriptivas. Los modelos
dimensionales pueden estar instanciados en bases de datos relacionales,
referidas como esquemas de estrella, o bases de datos
multidimensionales, conocidas como los cubos OLAP. Independientemente de
la plataforma, los modelos dimensionales intentar dirigirse a dos
objetivos simultáneos: facilidad de uso desde la perspectiva de los
usuarios y rapidez en la realización de la consulta.

El modelo dimensional se transforma en diseño físico. De esta manera, se
aborda el diseño del sistema ETL y los desafíos para el desarrollo. El
ciclo de vida describe subsistemas del proceso de extracción
transformación. Estos subsistemas se agrupan en 4 operaciones mayores:

1.  Extraer los datos de la fuente.

2.  Llevar a cabo la limpieza y el ajuste de las transformaciones

3.  Proporcionar los datos en la capa de presentación.

4.  Dirigir el proceso ETL de mantenimiento y entorno.

#### Modelado Dimensional

El modelado dimensional es una técnica de diseño que busca presentar la
información en un marco estándar e intuitivo que permita un acceso de
alto rendimiento. Este modelado se vale de los principios de la
disciplina que emplea el modelo relacional con algunas importantes
restricciones. El modelado dimensional es esencialmente útil para
resumir y organizar los datos y la presentación de información para
soportar el análisis de la misma. Existen algunos conceptos básicos para
comprender la filosofía de este tipo de modelado: Temas, Medidas,
Dimensiones y Jerarquías.

*Temas*

Un tema como es una cuestión de interés de una función empresarial. Los
temas en conjunto constituyen el ámbito de implementación del DW.

*Medidas*

Para especificar los temas se deben identificar las medidas. Una medida
o indicador es un cuantificador del desempeño de un ítem o una actividad
del negocio. La información que brinda una medida es usada por los
usuarios en sus consultas para evaluar el desempeño de un tema.

*Dimensiones*

El DW organiza un gran conjunto de datos operacionales mediante
múltiples dimensiones. Una dimensión es una colección de miembros o
entidades del mismo tipo y constituye un calificador conceptual que
provee el contexto o significado para una medida. Los miembros de una
dimensión pueden estar organizados en una o más jerarquías. Una
jerarquía es un conjunto de miembros de una dimensión, los cuales se
definen por su posición relativa con respecto a los otros miembros de la
misma dimensión, y forman en su totalidad una estructura de árbol.
Partiendo de la raíz del árbol, los miembros son progresivamente más
detallados hasta llegar a las hojas, donde obtenemos el mayor nivel de
detalle.

*Jerarquías*

Los miembros de una dimensión pueden estar organizados en una o más
jerarquías. Una jerarquía es un conjunto de miembros de una dimensión,
los cuales se definen por su posición relativa con respecto a los otros
miembros de la misma dimensión, y forman en su totalidad una estructura
de árbol. Partiendo de la raíz del árbol, los miembros son
progresivamente más detallados hasta llegar a las hojas, donde obtenemos
el mayor nivel de detalle.

*Cubos*

La realidad se modela como un conjunto de cubos. Cada cubo, esta formado
por:

1.  Un conjunto de Dimensiones organizadas en jerarquías.

2.  Un conjunto de Medidas asociadas a cada Coordenada.

*Operaciones OLAP*

Es posible moverse en las jerarquías de las dimensiones y observar de
esa forma, diferentes visiones de las medidas. Para esto último se
dispone de un conjunto de operaciones sobre MD:

1.  Slice

2.  Dice

3.  Pivot

4.  Drill-down

5.  Drill-up

6.  Roll-up

7.  Drill-across

8.  Drill-through

El modelado dimensional es un proceso dinámico y altamente iterativo.
Comienza con un modelo dimensional de alto nivel obtenido a partir de
los procesos priorizados y descritos en la tarea anterior. El proceso
iterativo consiste en cuatro pasos:

1.  Elegir el proceso de negocio: que consiste en, elegir el área a
    modelizar. Esta es una decisión de la dirección, y depende
    fundamentalmente del análisis de requerimientos y de los temas
    analíticos anotados en la etapa anterior.

2.  Establecer el nivel de granularidad: La granularidad significa
    especificar el nivel de detalle. La elección de la granularidad
    depende de los requerimientos del negocio y lo que es posible a
    partir de los datos actuales. La sugerencia general es comenzar a
    diseñar el DW al mayor nivel de detalle posible, ya que se podrían
    realizar agrupamientos posteriores, al nivel deseado.

3.  Elegir las dimensiones: Las dimensiones surgen naturalmente de las
    discusiones del equipo, y facilitadas por la elección del nivel de
    granularidad y de la matriz de procesos/dimensiones. Las tablas de
    dimensiones tienen un conjunto de atributos (generalmente textuales)
    que brindan una perspectiva o forma de análisis sobre una medida en
    una tabla hechos. Una forma de identificar las tablas de dimensiones
    es que sus atributos son posibles candidatos para ser encabezado en
    los informes, tablas pivote, cubos, o cualquier forma de
    visualización, unidimensional o multidimensional.

4.  Identificar medidas y las tablas de hechos: Este paso, consiste en
    identificar las medidas que surgen de los procesos de negocios. Una
    medida es un atributo (campo) de una tabla que se desea analizar,
    sumando o agrupando sus datos y usando los criterios de corte
    conocidos como dimensiones. Las medidas habitualmente se vinculan
    con el nivel de granularidad del punto 2, y se encuentran en tablas
    que denominamos tablas de hechos. Cada tabla de hechos tiene como
    atributos una o más medidas de un proceso organizacional, de acuerdo
    a los requerimientos. Un registro contiene una medida expresada en
    números, como ser cantidad, tiempo, dinero, etc., sobre la cual se
    desea realizar una operación de agregación (promedio, conteo, suma,
    etc.) en función de una o más dimensiones. La granularidad, en este
    punto, es el nivel de detalle que posee cada registro de una tabla
    de hechos.

#### Diseño Conceptual

El propósito de esta fase es representar los requerimientos
especificados en la etapa de Definición de Requerimientos del Negocio de
manera clara y concisa, para que pueda ser entendida por los usuarios
del sistema y por los diseñadores en las siguientes etapas de diseño.

El modelo Conceptual MultiDimensional Model (CMDM) [@carpani2000cmdm],
propuesto como tesis de Maestría por el grupo CSI del InCo es utilizado
para la generación de un modelo conceptual y se basa en el Modelo
Dimensional presentado.

El mismo define un modelo que permite la especificación detallada de una
base de datos multidimensional. Esta especificación se construye
mediante un lenguaje gráfico que permite describir las estructuras de
datos y algunas restricciones de integridad, y un lenguaje de
restricciones de integridad que permite dar una descripción precisa de
las relaciones entre los datos. En el mismo se presentan las siguientes
estructuras básicas:

*Niveles*: representan un conjunto de datos del mismo tipo. Existe una
analogía entre un nivel y una entidad en el Modelo Entidad Relación.
Para representar el esquema de un nivel se utiliza un rectángulo que
contiene el nombre y la estructura del mismo.

*Dimensiones*: una dimensión está compuesta por un conjunto de niveles
organizados en jerarquías. En cada una de ellas se tiene una relación
1:N entre objetos de nivel superior y nivel inferior. Cabe señalar que
las medidas también se representan como dimensiones.

*Relaciones dimensionales*: representan cruzamientos entre dimensiones.
Se tiene un elemento en el conjunto relación si y sólo si hay un
cruzamiento. Esto obliga a que las dimensiones participantes realmente
sean cruzables. En otras palabras, representa un conjunto de cubos,
tomado del conjunto de todos los cubos que se pueden construir a partir
de los niveles de un conjunto dado de dimensiones.

#### Diseño Lógico

La etapa de diseño lógico toma como entrada un esquema conceptual y
genera un esquema lógico relacional o multidimensional.

La dificultad principal es encontrar un esquema lógico que satisfaga no
sólo los requerimientos funcionales de información, sino también
requerimientos de performance en la realización de consultas complejas
de análisis de datos.

Existen distintos tipos de almacenamiento según la base de datos que se
utilizará:

*Sistemas MOLAP*

La arquitectura MOLAP usa unas bases de datos multidimensionales para
proporcionar el análisis, su principal premisa es que el OLAP está mejor
implantado almacenando los datos multidimensionalmente. Por el
contrario, la arquitectura ROLAP cree que las capacidades OLAP están
perfectamente implantadas sobre bases de datos relacionales Un sistema
MOLAP usa una base de datos propietaria multidimensional, en la que la
información se almacena multidimensionalmente, para ser visualizada en
varias dimensiones de análisis.

El sistema MOLAP utiliza una arquitectura de dos niveles: la bases de
datos multidimensionales y el motor analítico. La base de datos
multidimensional es la encargada del manejo, acceso y obtención del
dato.

La arquitectura MOLAP requiere unos cálculos intensivos de compilación.
Lee de datos precompilados, y tiene capacidades limitadas de crear
agregaciones dinámicamente o de hallar ratios que no se hayan
precalculados y almacenados previamente.

*Sistemas ROLAP*

La arquitectura ROLAP, accede a los datos almacenados en un DW para
proporcionar los análisis OLAP. La premisa de los sistemas ROLAP es que
las capacidades OLAP se soportan mejor contra las bases de datos
relacionales.

El sistema ROLAP utiliza una arquitectura de tres niveles. La base de
datos relacional maneja los requerimientos de almacenamiento de datos, y
el motor ROLAP proporciona la funcionalidad analítica. El nivel de base
de datos usa bases de datos relacionales para el manejo, acceso y
obtención del dato. El nivel de aplicación es el motor que ejecuta las
consultas multidimensionales de los usuarios.

La arquitectura ROLAP es capaz de usar datos precalculados si estos
están disponibles, o de generar dinámicamente los resultados desde los
datos elementales si es preciso. Esta arquitectura accede directamente a
los datos del DW, y soporta técnicas de optimización de accesos para
acelerar las consultas. Estas optimizaciones son, entre otras,
particionado de los datos a nivel de aplicación, soporte a la
desnormalización y joins múltiples.

*Sistemas HOLAP*

Un desarrollo un poco más reciente ha sido la solución OLAP híbrida
(HOLAP), la cual combina las arquitecturas ROLAP y MOLAP para brindar
una solución con las mejores características de ambas: desempeño
superior y gran escalabilidad. Un tipo de HOLAP mantiene los registros
de detalle (los volúmenes más grandes) en la base de datos relacional,
mientras que mantiene las agregaciones en un almacén MOLAP separado.

La herramienta OLAP utilizada para la implementación de este proyecto,
PBI, requiere que el DW esté almacenado en una base de datos relacional.
Por esta razón el tipo de almacenamiento utilizado fue ROLAP.

El modelo relacional, utilizado en el diseño de bases de datos
relacionales, resulta poco adecuado para realizar consultas
multidimensionales, ya que implica joins entre varias tablas y
sumarizaciones que son costosas y poco optimizables. Por lo tanto, para
los sistemas de DW ROLAP se utiliza el modelo multidimensional, que está
orientado a consultas OLAP y representa los conceptos multidimensionales
sobre estructuras relacionales. Este intenta minimizar joins y
totalizaciones, utilizando redundancias y desnormalizaciones. Dicho
modelo presenta dos estructuras básicas; las tablas de hecho, que son
las tablas principales del modelo y almacenan las medidas numéricas del
negocio, resultantes de la intersección de las dimensiones; y las tablas
de dimensión, donde se guardan las descripciones de las dimensiones.

A la hora de modelar el DW, hay que decidir cuál es el esquema más
apropiado para obtener los resultados que queremos conseguir.

*Star Schema* En el Star Schema hay una única tabla central, la tabla de
hechos, que contiene todas las medidas y una tabla adicional por cada
una de las perspectivas desde las que queremos analizar dicha
información, es decir por cada una de las dimensiones.

*Snowflake Schema* La otra alternativa de modelado es la utilización del
Snowflake Schema. Esta es una estructura más compleja que el esquema en
estrella. La diferencia es que algunas de las dimensiones no están
relacionadas directamente con la tabla de hechos, sino que se relacionan
con ella a través de otras dimensiones. En este caso también tenemos una
tabla de hechos, situada en el centro, que contiene todas las medidas y
una o varias tablas adicionales, con un mayor nivel de normalización.

El Star Schema, aunque ocupa más espacio en disco (dato cada vez menos
significativo), es más simple de entender por el usuario y ofrece un
mejor rendimiento a la hora de ser consultado.

*Star Cluster* Para lograr un mejor balance entre rendimiento,
almacenamiento y mantenimiento se puede utilizar un modelo híbrido
llamado Star Cluster. El mismo, selectivamente, separa los fragmentos de
jerarquías compartidos entre diferentes dimensiones, mientras que el
resto de las jerarquías se desnormalizan. Con este modelo se logra el
mínimo número de tablas y a la vez se evita el solapamiento entre
dimensiones.

#### Diseño Físico

En el diseño físico se implementa el esquema lógico en el manejador de
bases de datos elegido, teniendo en cuenta técnicas de comprensión,
índices, selección de vistas e índices, optimización de consultas, carga
y mantenimiento, los cuales se hace necesario para acelerar los tiempos
de respuesta de las consultas complejas.

#### Diseño e Implementación de ETL

El subsistema de ETL es la base sobre la cual se alimenta el sistema de
BI. Si se diseña adecuadamente, puede extraer los datos de los sistemas
de origen de datos, aplicar diferentes reglas para aumentar la calidad y
consistencia de los mismos, consolidar la información proveniente de
distintos sistemas, y finalmente cargar (grabar) la información en el DW
en un formato acorde para la utilización por parte de las herramientas
de análisis.

### Reportes y Analítica {#sec:business_intelligence_development_process_user_interface}

En está tarea se proporciona, a una gran comunidad de usuarios una forma
más estructurada y por lo tanto, más fácil, de acceder al DW. Se
proporciona este acceso estructurado a través de lo que llamamos,
aplicaciones de BI. Las aplicaciones de BI son la cara visible de la
inteligencia de negocios: los informes y aplicaciones de análisis
proporcionan información útil a los usuarios. Las aplicaciones de BI
incluyen un amplio espectro de tipos de informes y herramientas de
análisis, que van desde informes simples de formato fijo, a sofisticadas
aplicaciones analíticas que usan complejos algoritmos e información del
dominio. Kimball divide a estas aplicaciones en dos categorías basadas
en el nivel de sofisticación, y les llama:

1.  Informes estándar: son informes relativamente simples, de formato
    predefinido, y parámetros de consulta fijos, proporcionan a los
    usuarios un conjunto básico de información acerca de lo que está
    sucediendo en un área determinada de la empresa y se utilizan día a
    día.

2.  Aplicaciones analíticas: Son más complejas que los informes
    estándar. Estas aplicaciones pueden incluir algoritmos y modelos de
    minería de datos, que ayudan a identificar oportunidades o
    cuestiones subyacentes en los datos, y el usuario puede pedir
    cambios en los sistemas transaccionales basándose en los
    conocimientos obtenidos del uso de la aplicación de BI. Algunas
    aplicaciones analíticas comunes incluyen:

    1.  Análisis de la eficacia de la promociones.

    2.  Análisis de rutas de acceso en un sitio Web.

    3.  Análisis de afinidad de programas.

    4.  Planificación del espacio en espacios comerciales.

    5.  Detección de fraudes.

    6.  Administración y manejo de categorías de productos.

#### Diseño y Desarrollo de Herramientas de BI

Mientras que algunos miembros de proyectos están inmersos en la
tecnología y los datos, otros se centran en identificar y construir un
amplio rango de aplicaciones BI, incluyendo informes estandarizados,
consultas parametrizadas, tableros, cuadros de mando, modelos
analíticos, aplicaciones de extracción de datos junto con las interfaces
de navegación asociadas.

### Implantación, Mantenimiento y Crecimiento {#sec:business_intelligence_development_process_deployment}

Las tres rutas en el Ciclo de Vida Dimensional del Negocio convergen en
la implementación, reuniendo la tecnología, los datos y las aplicaciones
BI. La implementación iterada entra en fase de mantenimiento, mientras
que el crecimiento vuelve atrás hacia la planificación del proyecto para
la próxima iteración del sistema BI/DW

Para administrar el entorno del sistema de BI existente es importante
enfocarse en los usuarios de negocio, los cuales son el motivo de su
existencia, además de gestionar adecuadamente las operaciones del
sistema de BI, medir y proyectar su éxito y comunicarse constantemente
con los usuarios para establecer un flujo de retroalimentación, en esto
consiste el Mantenimiento. Finalmente, es importante sentar las bases
para el crecimiento y evolución del sistema de BI en donde el aspecto
clave es manejar el crecimiento y evolución de forma iterativa
utilizando el Ciclo de Vida propuesto, y establecer las oportunidades de
crecimiento y evolución en orden por nivel prioridad.
