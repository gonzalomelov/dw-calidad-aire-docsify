Trabajo a futuro {#sec:trabajo_futuro}
----------------

A continuación se presentan lineamientos generales sobre posibles
mejoras a tener en cuenta para trabajos futuros.

**Nuevos requerimientos de análisis**

Los sistemas de BI sufren cambios constantemente por la necesidad de
apoyar la evolución de la aplicación debido a nuevos requerimientos de
análisis o cambios en los requerimientos existentes.

La habilidad del sistema para evolucionar requiere un esfuerzo especial
para anticipar cuándo y cómo pueden ocurrir estos cambios.

Basado en las métricas de uso de las consultas dinámicas más utilizados
por los especialistas de la IM en Saiku es posible obtener
retroalimentación del usuario para entender cómo debe evolucionar el
sistema con nuevos requerimientos o cambios a los requerimientos ya
existentes.

Con ello es posible identificar las consultas más frecuentes y generar
indicadores o gráficas pre-armadas para hacer la tareas de análisis más
efectiva.

**Aumentar capacidades para monitorear la calidad del agua, suelo y
efluentes industriales.**

El Servicio cumple la función de evaluación y vigilancia ambiental, y
tiene como principales áreas de trabajo el monitoreo de la calidad de
agua, aire, suelo y efluentes industriales, la fiscalización de plantas
de tratamiento y la gestión para una adecuada disposición final de
residuos sólidos industriales.

Con el desarrollo del proyecto actual se disponibiliza un sistema de BI
que cubre las necesidad de monitoreo del aire pero que es extensible a
las otras áreas que son monitoreadas por el servicio ECCA debido a que
las herramientas y componentes de software utilizados son los mismos.

Se dejan sentadas las bases para la realización de un pre-proyecto para
evaluar los requerimientos y necesidades de las otras unidades dentro
del servicio ECCA y definir el impacto y los ajustes requeridos para
abarcarlos.

**Minería de datos (*Data mining*)**

La minería de datos es una técnica de análisis y procesado de grandes
volúmenes de datos con el objeto de extraer información útil y patrones
de fácil comprensión, que sería imposible conseguir por los medios y
herramientas estadísticas tradicionales.

En la actualidad existen múltiples trabajos, basados en dichas técnicas,
con foco en la calidad de aire de distintas ciudades del mundo.

Utilizando los datos disponibles en el momento del desarrollo del
proyecto es posible utilizar técnicas de minería de datos para encontrar
relaciones entre las fuentes de datos utilizadas, como variables
climatológicas, volumen vehicular, actividad industrial y emisiones
contaminantes, y otras fuentes de datos que se puedan descubrir y
utilizar. Además, sobre esa información nueva o sobre la ya disponible,
aplicar técnicas de análisis predictivo para realizar proyecciones de
futuro.

Cabe destacar que para su realización es posible utilizar el paquete
openair, que presenta herramientas de minería sencillas y muy
atractivas, que ya se encuentra disponibilizada en la plataforma y se
utiliza para el cálculo estadístico en la generación de la sección del
Informe Anual.

**Instalación en la intranet e integración con bases de datos de la Red
de Monitoreo de la IM**

Actualmente la carga de fuentes de datos generados por la Red de
Monitoreo se realiza de forma manual debiendo los especialistas de la IM
ingresar al aplicativo web para realizar la carga y actualización de los
datos del sistema de BI. Este procedimiento debe su naturaleza a que los
datos agregados disponibilizados son públicos y se encuentran
disponibles en el trascurso del proyecto.

Este procedimiento tiene múltiples desventajas como ser propenso a
errores humanos, ocupar horas/persona en tareas que pueden ser
automatizables, entre otros.

Se propone el desarrollo de una integración directa desde los procesos
ETL hacia las bases de datos fuentes utilizadas por los aplicativos de
producción que se dispone desde la IM para la Red de Monitoreo. Para
ello sería necesario la instalación del sistema completo de BI en la
intranet de la IM logrando otros aspectos importantes como seguridad y
gobernanza de los datos.

Dicha integración facilitaría la carga y actualización del sistema de
BI, aspecto clave en los proyectos de BI, y podría abrir las puertas a
la incorporación de nuevos tipos de datos que se dispongan en la interna
y no sean públicos.

**Disponibilizar y popularizar el sistema de BI**

Periódicamente los especialistas generan reportes de resultados que son
compartidos a las distintas áreas interesadas dentro de la IM y a otras
organizaciones con las que se mantiene una relación de colaboración.

Actualmente la interfaz de usuario está enfocada al uso interno del
Servicio de Evaluación de la Calidad y Control Ambiental por parte del
personal de la Unidad Calidad de Aire.

Resulta de interés permitir el ingreso al sistema de BI posibilitando a
usuarios externos a la Unidad Calidad de Aire poder realizar el análisis
de los datos cuándo y cómo lo deseen.

El objetivo primordial es el de popularizar la herramienta y enmarcarla
como punto de referencia para el análisis de la información y como
complemento de ayuda a la toma de decisiones.

**Automatizar generación completa del Informe Anual e Informe Semanal**

Simplificar el proceso de redacción de informes es crucial para mejorar
una organización; las horas de trabajo pueden utilizarse indebidamente
durante el proceso de redacción de informes si los datos no son claros y
los gráficos individuales deben generarse manualmente.

Utilizar una solución que proporcione informes automatizados reducirá
fácilmente las horas de redacción de informes mediante la recopilación,
interpretación y presentación automática de datos de una manera
comprensible y automática para que todos los involucrados puedan
entender lo que se intenta transmitir en el informe.

Dicho esto, como resultado inicial del desarrollo del proyecto se logró
automatizar la generación de una sección específica del Informe Anual y
se brinda la posibilidad, utilizando las mismas herramientas, de
extender las automatizaciones para cubrir la generación total del
Informe Anual y además el Informe Semanal.