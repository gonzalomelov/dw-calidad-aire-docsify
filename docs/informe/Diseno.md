
Diseño {#diseno_data_warehouse}
------

Dado que el área de Servicio de Calidad de Aire se enfoca especialmente
en el monitoreo y evaluación de la calidad de aire, un área de negocio
con objetivos específicos, se utiliza la metodología bottom-up.

A continuación se especifican cada una de las etapas de diseño
realizadas.

### Diseño Conceptual {#diseno_conceptual}

La etapa de Diseño Conceptual se realiza utilizando un enfoque
combinado, haciendo uso paralelamente de los requerimientos
identificados y el modelo conceptual de las fuentes de datos generado,
ambas salidas generadas en la etapa de Análisis. Finalmente se integran
los resultados de ambos enfoques.

Adicionalmente, se incluye la representación gráfica de los distintos
componentes del diseño conceptual utilizando el modelo CMDM.

#### Dimensiones y jerarquías {#diseno_conceptual_dimensiones}

Para modelar la realidad del problema es necesario construir las
siguientes dimensiones que sirven como criterios de análisis de los
datos como se pueden ver en los distintos grupos de dimensiones en las
figuras
[\[fig:dimensiones\_y\_medidas\_red\_monitoreo\_montevideo\]](#fig:dimensiones_y_medidas_red_monitoreo_montevideo){reference-type="ref"
reference="fig:dimensiones_y_medidas_red_monitoreo_montevideo"},
[\[fig:dimensiones\_y\_medidas\_temporales\]](#fig:dimensiones_y_medidas_temporales){reference-type="ref"
reference="fig:dimensiones_y_medidas_temporales"},
[\[fig:dimensiones\_y\_medidas\_meteorologico\]](#fig:dimensiones_y_medidas_meteorologico){reference-type="ref"
reference="fig:dimensiones_y_medidas_meteorologico"}, y
[\[fig:dimensiones\_y\_medidas\_externos\]](#fig:dimensiones_y_medidas_externos){reference-type="ref"
reference="fig:dimensiones_y_medidas_externos"}.

![\[\[fig:dimensiones\_y\_medidas\_red\_monitoreo\_montevideo\]\]{#fig:dimensiones_y_medidas_red_monitoreo_montevideo
label="fig:dimensiones_y_medidas_red_monitoreo_montevideo"}Dimensiones
de Red de Monitoreo de Calidad de Aire de
Montevideo](Imagenes/dimensiones_y_medidas_red_monitoreo_montevideo.png){width="80%"}

![\[\[fig:dimensiones\_y\_medidas\_temporales\]\]{#fig:dimensiones_y_medidas_temporales
label="fig:dimensiones_y_medidas_temporales"}Dimensiones
Temporales](Imagenes/dimensiones_y_medidas_temporales.png){width="80%"}

![\[\[fig:dimensiones\_y\_medidas\_meteorologico\]\]{#fig:dimensiones_y_medidas_meteorologico
label="fig:dimensiones_y_medidas_meteorologico"}Dimensiones
Meteorológicas](Imagenes/dimensiones_y_medidas_meteorologico.png){width="80%"}

![\[\[fig:dimensiones\_y\_medidas\_externos\]\]{#fig:dimensiones_y_medidas_externos
label="fig:dimensiones_y_medidas_externos"}Dimensiones Fuentes
Externas](Imagenes/dimensiones_y_medidas_externos.png){width="80%"}

A continuación se describen las distintas dimensiones en detalle:

**Estaciones de la Red**

La dimensión Estaciones de la Red representa las estaciones que permiten
evaluar la concentración de material particulado en diversas fracciones
y de gases que habitualmente se encuentran en ambientes urbanos (dióxido
de azufre y dióxido de nitrógeno).

[Niveles]{.underline}

*EstacionDeLaRed*: Compuesto por las estaciones de la red de monitoreo.

*Barrio*: Compuesto por los barrios de Montevideo.

*CentroComunal*: Compuesto por los centros comunales zonales de
Montevideo.

*TipoEquipamiento*: Compuesto por los métodos de medición que emplean
las estaciones de la red.

*Objetivo*: Compuesto por los propósitos que cumplen las estaciones de
la red.

[Jerarquías]{.underline}

*Ubicación física*: Se diseñó de forma tal que fuera posible agregar las
medidas por su ubicación física, específicamente, barrios y centros
comunales zonales.

Como se puede visualizar en las siguientes tablas la jerarquía no es de
tipo Estricta y Balanceada debido a que existen barrios que se
encuentran en varios CCZ.

*Tipo de equipamiento*: Las estaciones de la red se pueden agrupar según
el método de medición que emplean en automáticas o manuales. La
jerarquía es de tipo Estricta y Balanceada.

*Objetivo*: Las estaciones de la red se pueden diferenciar según el
propósito u objetivo que cumplen en evaluar la calidad base de la Ciudad
o evaluar el impacto generado por algunas de las fuentes más
significativas del departamento. La jerarquía es de tipo Estricta y
Balanceada.

![\[\[fig:estacionesdelared\]\]{#fig:estacionesdelared
label="fig:estacionesdelared"}Estaciones de la
Red](Imagenes/estacionesdelared.png){width="60%"}

Sigue un ejemplo, en
[\[fig:estacionesdelared\_example\]](#fig:estacionesdelared_example){reference-type="ref"
reference="fig:estacionesdelared_example"},
[\[fig:estacionesdelared\_tipoequipamiento\_example\]](#fig:estacionesdelared_tipoequipamiento_example){reference-type="ref"
reference="fig:estacionesdelared_tipoequipamiento_example"} y
[\[fig:estacionesdelared\_objetivo\_example\]](#fig:estacionesdelared_objetivo_example){reference-type="ref"
reference="fig:estacionesdelared_objetivo_example"}, de los datos que se
contendrán en cada nivel de cada jerarquía:

![\[\[fig:estacionesdelared\_example\]\]{#fig:estacionesdelared_example
label="fig:estacionesdelared_example"}Estaciones de la Red - Ubicación
física](Imagenes/estacionesdelared_example.png){width="80%"}

![\[\[fig:estacionesdelared\_tipoequipamiento\_example\]\]{#fig:estacionesdelared_tipoequipamiento_example
label="fig:estacionesdelared_tipoequipamiento_example"}Estaciones de la
Red - Tipo
Equipamiento](Imagenes/estacionesdelared_tipoequipamiento_example.png){width="80%"}

![\[\[fig:estacionesdelared\_objetivo\_example\]\]{#fig:estacionesdelared_objetivo_example
label="fig:estacionesdelared_objetivo_example"}Estaciones de la Red -
Objetivo](Imagenes/estacionesdelared_objetivo_example.png){width="80%"}

**Contaminantes**

La dimensión Contaminantes representan tanto los contaminantes gaseosos
(dióxido de carbono, el monóxido de carbono, los hidrocarburos, los
óxidos de nitrógeno, los óxidos de azufre y el ozono) como el material
particulado (mezcla heterogénea de partículas sólidas o líquidas
suspendidas en un gas).

[Niveles]{.underline}

*Contaminante*: Compuesto por los contaminantes medidos por las
estaciones de la red.

*Subtipo*: Compuesto por los subtipos de los contaminantes.

*Tipo*: Compuesto por los tipos de los contaminantes.

[Jerarquías]{.underline}

*Tipo de contaminante*: Los contaminantes se pueden agrupar según el
subtipo y tipo en contaminantes gaseosos y material particulado. La
jerarquía es de tipo Estricta y Balanceada.

![\[\[fig:contaminantes\]\]{#fig:contaminantes
label="fig:contaminantes"}Contaminantes](Imagenes/contaminantes.png){width="20%"}

Sigue un ejemplo, en
[\[fig:contaminantes\_example\]](#fig:contaminantes_example){reference-type="ref"
reference="fig:contaminantes_example"}, los datos que se contendrán en
cada nivel de cada jerarquía:

![\[\[fig:contaminantes\_example\]\]{#fig:contaminantes_example
label="fig:contaminantes_example"}Contaminantes
Ejemplo](Imagenes/contaminantes_example.png){width="80%"}

**Métodos**

La dimensión Métodos representan los distintos métodos de medida de los
contaminantes en el aire, donde se abarcan métodos químicos simples ó
métodos de algunas técnicas electrónicas más sofisticadas.

[Niveles]{.underline}

*Método*: Compuesto por los métodos utilizados para la realización de
las mediciones por las estaciones de la red.

[Jerarquías]{.underline}

Para este criterio de análisis se definió una jerarquía compuesta por un
único nivel.

![\[\[fig:metodos\]\]{#fig:metodos
label="fig:metodos"}Métodos](Imagenes/metodos.png){width="20%"}

Sigue un ejemplo, en
[\[fig:metodos\_example\]](#fig:metodos_example){reference-type="ref"
reference="fig:metodos_example"}, de los datos que se contendrán en cada
nivel de cada jerarquía:

![\[\[fig:metodos\_example\]\]{#fig:metodos_example
label="fig:metodos_example"}Métodos
Ejemplo](Imagenes/metodos_example.png){width="80%"}

**Días de la Semana**

La dimensión Días de la Semana representan los 7 días de la semana.

[Niveles]{.underline}

*DiaDeLaSemana*: Compuesto por los 7 días de la semana.

*Tipo*: Compuesto por los distintos tipos de día de la semana.

[Jerarquías]{.underline}

*Ciclo de trabajo y de descanso*: Los días de la semana se diferencian
entre días laborables y de descanso. La jerarquía es de tipo Estricta y
Balanceada.

![\[\[fig:diasdelasemana\]\]{#fig:diasdelasemana
label="fig:diasdelasemana"}Días de la
Semana](Imagenes/diasdelasemana.png){width="20%"}

Sigue un ejemplo, en
[\[fig:diasdelasemana\_example\]](#fig:diasdelasemana_example){reference-type="ref"
reference="fig:diasdelasemana_example"}, de los datos que se contendrán
en cada nivel de cada jerarquía:

![\[\[fig:diasdelasemana\_example\]\]{#fig:diasdelasemana_example
label="fig:diasdelasemana_example"}Días de la Semana
Ejemplo](Imagenes/diasdelasemana_example.png){width="80%"}

**Estaciones del Año**

La dimensión Estaciones del Año representa los períodos en los que las
condiciones climáticas imperantes se mantienen, en una determinada
región, dentro de un cierto rango. En este caso, nos basamos en las
estaciones que aplican a Uruguay.

[Niveles]{.underline}

*EstacionDelAnio*: Compuesto por las estaciones del año según el
contexto uruguayo.

[Jerarquías]{.underline}

Para este criterio de análisis se definió una jerarquía compuesta por un
único nivel.

![\[\[fig:estacionesdelanio\]\]{#fig:estacionesdelanio
label="fig:estacionesdelanio"}Estaciones del
Año](Imagenes/estacionesdelanio.png){width="20%"}

Sigue un ejemplo, en
[\[fig:estacionesdelanio\_example\]](#fig:estacionesdelanio_example){reference-type="ref"
reference="fig:estacionesdelanio_example"}, de los datos que se
contendrán en cada nivel de cada jerarquía:

![\[\[fig:estacionesdelanio\_example\]\]{#fig:estacionesdelanio_example
label="fig:estacionesdelanio_example"}Estaciones del Año
Ejemplo](Imagenes/estacionesdelanio_example.png){width="80%"}

**Contaminantes Categorías**

**Tiempo**

La dimensión Tiempo representa el criterio de análisis temporal.

[Niveles]{.underline}

*Fecha*: Compuesto por todos los días de cada año.

*Mes*: Compuesto por todos los meses de cada año.

*Trimestre*: Compuesto por todos trimestres de cada año.

*Semestre*: Compuesto por todos semestres de cada año.

*Año*: Compuesto por todos años.

[Jerarquías]{.underline}

Períodos: Se se diseñó de forma tal que fuera posible agregar las
medidas por los rangos de tiempo Mes, Trimestre, Semestre y Año. La
jerarquía es de tipo Estricta y Balanceada.

![\[\[fig:tiempo\]\]{#fig:tiempo
label="fig:tiempo"}Tiempo](Imagenes/tiempo.png){width="20%"}

Sigue un ejemplo, en
[\[fig:tiempo\_example\]](#fig:tiempo_example){reference-type="ref"
reference="fig:tiempo_example"}, de los datos que se contendrán en cada
nivel de cada jerarquía:

![\[\[fig:tiempo\_example\]\]{#fig:tiempo_example
label="fig:tiempo_example"}Tiempo
Ejemplo](Imagenes/tiempo_example.png){width="80%"}

**Horas**

La dimensión Horas representa la una unidad de tiempo.

[Niveles]{.underline}

*Hora*: Compuesto por todas las horas del día.

*RangoHora*: Compuesto por los rangos de horas según la parte del día.

[Jerarquías]{.underline}

*Períodos*: Se se diseñó de forma tal que fuera posible agregar las
horas por los rangos según las partes del día en, entre otros, Mañana,
Tarde y Noche. La jerarquía es de tipo Estricta y Balanceada.

![\[\[fig:horas\]\]{#fig:horas
label="fig:horas"}Horas](Imagenes/horas.png){width="20%"}

Sigue un ejemplo, en
[\[fig:horas\_example\]](#fig:horas_example){reference-type="ref"
reference="fig:horas_example"}, de los datos que se contendrán en cada
nivel de cada jerarquía:

![\[\[fig:horas\_example\]\]{#fig:horas_example
label="fig:horas_example"}Horas
Ejemplo](Imagenes/horas_example.png){width="80%"}

**Radiación Solar Global**

La dimensión Radiación Solar Global representa la energía proveniente
del sol que incide en una superficie plana (suelo) en forma de ondas
electromagnéticas.

[Niveles]{.underline}

*RadiacionSolarGlobal*: Compuesto por todos los valores posibles de
radiación solar medidos.

*RangoRadiacionSolarGlobal*: Compuesto por rangos de radiación solar
definidos con los especialistas.

[Jerarquías]{.underline}

*Rangos*: Los valores de la radiación solar
[@radiacionsolarglobalrangos] se pueden agrupar según la intensidad. La
jerarquía es de tipo Estricta y Balanceada.

![\[\[fig:radiacionsolarglobal\]\]{#fig:radiacionsolarglobal
label="fig:radiacionsolarglobal"}Radiación Solar
Global](Imagenes/radiacionsolarglobal.png){width="20%"}

Sigue un ejemplo, en
[\[fig:radiacionsolarglobal\_example\]](#fig:radiacionsolarglobal_example){reference-type="ref"
reference="fig:radiacionsolarglobal_example"}, de los datos que se
contendrán en cada nivel de cada jerarquía:

![\[\[fig:radiacionsolarglobal\_example\]\]{#fig:radiacionsolarglobal_example
label="fig:radiacionsolarglobal_example"}Radiación Solar Global
Ejemplo](Imagenes/radiacionsolarglobal_example.png){width="80%"}

**Humedad Relativa**

La dimensión Humedad Relativa representa la relación entre la presión
parcial del vapor de agua y la presión de vapor de equilibrio del agua a
una temperatura dada.

[Niveles]{.underline}

*HumedadRelativa*: Compuesto por todos los valores posibles de humedad
relativa medidos.

*RangoHumedadRelativa*: Compuesto por rangos de humedad relativa
estándar.

[Jerarquías]{.underline}

*Rangos*: Los valores de la humedad relativa se pueden agrupar según el
orden de saturación basado en el porcentaje [@humedadrelativarangos]. La
jerarquía es de tipo Estricta y Balanceada.

![\[\[fig:humedadrelativa\]\]{#fig:humedadrelativa
label="fig:humedadrelativa"}Humedad
Relativa](Imagenes/humedadrelativa.png){width="20%"}

Sigue un ejemplo, en
[\[fig:humedadrelativa\_example\]](#fig:humedadrelativa_example){reference-type="ref"
reference="fig:humedadrelativa_example"}, de los datos que se contendrán
en cada nivel de cada jerarquía:

![\[\[fig:humedadrelativa\_example\]\]{#fig:humedadrelativa_example
label="fig:humedadrelativa_example"}Humedad Relativa
Ejemplo](Imagenes/humedadrelativa_example.png){width="80%"}

**Temperatura Externa**

La dimensión Temperatura Externa representa la magnitud referida a la
noción de calor medible mediante un termómetro.

[Niveles]{.underline}

*TemperaturaExterna*: Compuesto por todos los valores posibles de
temperatura externa medidos.

*RangoTemperaturaExterna*: Compuesto por rangos de temperatura externa
estándar.

[Jerarquías]{.underline}

*Rangos*: Los valores de la temperatura externa se pueden agrupar según
el grado de nivel térmico de la atmósfera. La jerarquía es de tipo
Estricta y Balanceada.

![\[\[fig:temperaturaexterna\]\]{#fig:temperaturaexterna
label="fig:temperaturaexterna"}Temperatura
Externa](Imagenes/temperaturaexterna.png){width="20%"}

Sigue un ejemplo, en
[\[fig:temperaturaexterna\_example\]](#fig:temperaturaexterna_example){reference-type="ref"
reference="fig:temperaturaexterna_example"}, de los datos que se
contendrán en cada nivel de cada jerarquía:

![\[\[fig:temperaturaexterna\_example\]\]{#fig:temperaturaexterna_example
label="fig:temperaturaexterna_example"}Temperatura Externa
Ejemplo](Imagenes/temperaturaexterna_example.png){width="80%"}

**Viento Dirección**

La dimensión Viento Dirección representa la dirección desde la cual
sopla el viento, y se mide en grados en la dirección de las agujas del
reloj a partir del norte verdadero.

[Niveles]{.underline}

*VientoDireccion*: Compuesto por todos los valores posibles de la
dirección del viento medidos.

*RangoVientoDireccion*: Compuesto por rangos según la rosa de los
vientos.

[Jerarquías]{.underline}

*Rangos*: Los valores de la dirección del viento se pueden agrupar en
los rumbos en que se divide la circunferencia del horizonte
[@vientodireccionrangos]. La jerarquía es de tipo Estricta y Balanceada.

![\[\[fig:vientodireccion\]\]{#fig:vientodireccion
label="fig:vientodireccion"}Viento
Dirección](Imagenes/vientodireccion.png){width="20%"}

Sigue un ejemplo, en
[\[fig:vientodireccion\_example\]](#fig:vientodireccion_example){reference-type="ref"
reference="fig:vientodireccion_example"}, de los datos que se contendrán
en cada nivel de cada jerarquía:

![\[\[fig:vientodireccion\_example\]\]{#fig:vientodireccion_example
label="fig:vientodireccion_example"}Viento Dirección
Ejemplo](Imagenes/vientodireccion_example.png){width="100%"}

**Viento Velocidad**

La dimensión Viento Velocidad representa la medición de la componente
horizontal del desplazamiento del aire en un punto y en un instante
determinados.

[Niveles]{.underline}

*VientoVelocidad*: Compuesto por todos los valores posibles de la
velocidad del viento medidos.

*RangoVientoVelocidad*: Compuesto por rangos según la Escala de Beaufort
[@vientovelocidadescaladebeaufort] en relación a las distintas velocidad
[@vientovelocidadrangos].

[Jerarquías]{.underline}

*Rangos*: Los valores de la velocidad del viento se pueden agrupar según
la intensidad [@vientovelocidadintensidad] del viento basada
principalmente en el estado del mar, de sus olas y la fuerza del viento.
La jerarquía es de tipo Estricta y Balanceada.

![\[\[fig:vientovelocidad\]\]{#fig:vientovelocidad
label="fig:vientovelocidad"}Viento
Velocidad](Imagenes/vientovelocidad.png){width="20%"}

Sigue un ejemplo, en
[\[fig:vientovelocidad\_example\]](#fig:vientovelocidad_example){reference-type="ref"
reference="fig:vientovelocidad_example"}, de los datos que se contendrán
en cada nivel de cada jerarquía:

![\[\[fig:vientovelocidad\_example\]\]{#fig:vientovelocidad_example
label="fig:vientovelocidad_example"}Viento Velocidad
Ejemplo](Imagenes/vientovelocidad_example.png){width="100%"}

**Cámaras**

La dimensión Cámaras representa las cámaras de la IM que sirven a
monitorear el tránsito y tráfico en distintos puntos de la ciudad.

[Niveles]{.underline}

*Cámaras*: Compuesto por todas las cámaras de tránsito.

[Jerarquías]{.underline}

Para este criterio de análisis se definió una jerarquía compuesta por un
único nivel.

![\[\[fig:camaras\]\]{#fig:camaras
label="fig:camaras"}Cámaras](Imagenes/camaras.png){width="20%"}

Sigue un ejemplo, en
[\[fig:camaras\_example\]](#fig:camaras_example){reference-type="ref"
reference="fig:camaras_example"}, de los datos que se contendrán en cada
nivel de cada jerarquía:

![\[\[fig:camaras\_example\]\]{#fig:camaras_example
label="fig:camaras_example"}Cámaras
Ejemplo](Imagenes/camaras_example.png){width="100%"}

**Industrias**

La dimensión Industrias representan las industrias que se encuentran en
el área de Montevideo.

[Niveles]{.underline}

*Industria*: Compuesto por los todas las industrias.

*Tipo*: Compuesto por los tipos de industrias existentes según su rubro.

[Jerarquías]{.underline}

*Tipo de industria*: Las industrias se pueden agrupar según el rubro en
el cual se encuentren. La jerarquía es de tipo Estricta y Balanceada.

![\[\[fig:industrias\]\]{#fig:industrias
label="fig:industrias"}Industrias](Imagenes/industrias.png){width="20%"}

Sigue un ejemplo, en
[\[fig:industrias\_example\]](#fig:industrias_example){reference-type="ref"
reference="fig:industrias_example"}, de los datos que se contendrán en
cada nivel de cada jerarquía:

![\[\[fig:industrias\_example\]\]{#fig:industrias_example
label="fig:industrias_example"}Industrias
Ejemplo](Imagenes/industrias_example.png){width="100%"}

**Días Importantes**

La dimensión Días Importantes representan los días que interesan
analizar debido a su carácter festivo o de descanso que aumenta
considerablemente la posibilidad de combustión, específicamente la quema
de leña generada por los asados.

[Niveles]{.underline}

*Día Importante*: Compuesto por los todos los días importantes
definidos.

*Tipo*: Compuesto por los tipos de días importantes según sean festivos,
patrios o eventos relevantes.

[Jerarquías]{.underline}

*Tipo de días importantes*: Los días importantes se pueden generalizar
según el motivo por el cual es importante. La jerarquía es de tipo
Estricta y Balanceada.

![\[\[fig:diasimportantes\]\]{#fig:diasimportantes
label="fig:diasimportantes"}Días
Importantes](Imagenes/diasimportantes.png){width="20%"}

Sigue un ejemplo, en
[\[fig:diasimportantes\_example\]](#fig:diasimportantes_example){reference-type="ref"
reference="fig:diasimportantes_example"}, de los datos que se contendrán
en cada nivel de cada jerarquía:

![\[\[fig:diasimportantes\_example\]\]{#fig:diasimportantes_example
label="fig:diasimportantes_example"}Días Importantes
Ejemplo](Imagenes/diasimportantes_example.png){width="100%"}

#### Medidas {#diseno_conceptual_medidas}

En la siguiente sección se presentan las medidas definidas para el
análisis según la especificación de requerimientos realizada.

![\[\[fig:medidas\]\]{#fig:medidas
label="fig:medidas"}Medidas](Imagenes/medidas.png){width="100%"}

**Vehículos Contaminación**

Basado en el [\[label:rfaid1\]](#label:rfaid1){reference-type="ref"
reference="label:rfaid1"}, relativo a analizar la evolución en el tiempo
de la contaminación en el aire relacionándolo con la densidad vehicular,
se definen los indicadores de contaminación y densidad vehicular, como
se puede visualizar en
[\[fig:vehiculoscontaminacion\]](#fig:vehiculoscontaminacion){reference-type="ref"
reference="fig:vehiculoscontaminacion"}.

![\[\[fig:vehiculoscontaminacion\]\]{#fig:vehiculoscontaminacion
label="fig:vehiculoscontaminacion"}Vehículos
Contaminación](Imagenes/vehiculoscontaminacion.png){width="30%"}

**Industrias Contaminación**

Basado en el [\[label:rfaid2\]](#label:rfaid2){reference-type="ref"
reference="label:rfaid2"}, relativo a analizar la evolución en el tiempo
de la contaminación en el aire relacionándolo con la actividad
industrial, se definen los indicadores de contaminación y actividad
industrial, como se puede visualizar en
[\[fig:industriascontaminacion\]](#fig:industriascontaminacion){reference-type="ref"
reference="fig:industriascontaminacion"}.

![\[\[fig:industriascontaminacion\]\]{#fig:industriascontaminacion
label="fig:industriascontaminacion"}Industrias
Contaminación](Imagenes/industriascontaminacion.png){width="30%"}

**Días Importantes Contaminación**

Basado en el [\[label:rfaid3\]](#label:rfaid3){reference-type="ref"
reference="label:rfaid3"}, relativo a analizar la evolución en el tiempo
de la contaminación en el aire relacionándolo con la los días
especiales, se define el indicador de contaminación, como se puede
visualizar en
[\[fig:diasimportantescontaminacion\]](#fig:diasimportantescontaminacion){reference-type="ref"
reference="fig:diasimportantescontaminacion"}.

![\[\[fig:diasimportantescontaminacion\]\]{#fig:diasimportantescontaminacion
label="fig:diasimportantescontaminacion"}Días Importantes
Contaminación](Imagenes/diasimportantescontaminacion.png){width="30%"}

#### Esquema Conceptual Multi-Dimensional {#diseno_conceptual_dimensiones}

El Esquema Conceptual Multi-Dimensional está formado por el siguiente
conjunto de Relaciones Dimensionales.

Las Relaciones Dimensionales comparten distintas dimensiones entre
ellas. En la siguiente tabla se puede visualizar que será posible
realizar Drill-Across mediante:

  -------------------------- ---------------------------------------------------------------------------------- ---------------------------------------------------------------------------------- ----------------------------------------------------------------------------------
  Dimensión                  [\[label:rfaid1\]](#label:rfaid1){reference-type="ref" reference="label:rfaid1"}   [\[label:rfaid2\]](#label:rfaid2){reference-type="ref" reference="label:rfaid2"}   [\[label:rfaid3\]](#label:rfaid3){reference-type="ref" reference="label:rfaid3"}
  Estaciones de la Red       X                                                                                  X                                                                                  X
  Contaminantes              X                                                                                  X                                                                                  X
  Métodos                    X                                                                                  X                                                                                  X
  Días de la Semana          X                                                                                  X                                                                                  X
  Estaciones del Año         X                                                                                  X                                                                                  X
  Contaminantes Categorías   X                                                                                  X                                                                                  X
  Tiempo                     X                                                                                  X                                                                                  X
  Horas                      X                                                                                  X                                                                                  X
  Radiación Solar Global     X                                                                                  X                                                                                  X
  Humedad Relativa           X                                                                                  X                                                                                  X
  Temperatura Externa        X                                                                                  X                                                                                  X
  Viento Dirección           X                                                                                  X                                                                                  X
  Viento Velocidad           X                                                                                  X                                                                                  X
  Cámaras                    X                                                                                  \-                                                                                 \-
  Industrias                 \-                                                                                 X                                                                                  \-
  Días Importantes           \-                                                                                 \-                                                                                 X
  -------------------------- ---------------------------------------------------------------------------------- ---------------------------------------------------------------------------------- ----------------------------------------------------------------------------------

**Vehículos Contaminación**

La relación dimensional Vehículos Contaminación permite examinar la
relación entre la contaminación y la densidad vehicular según los
distintos criterios dimensionales indicados en
[\[fig:relaciondimensional\_vehiculoscontaminacion\]](#fig:relaciondimensional_vehiculoscontaminacion){reference-type="ref"
reference="fig:relaciondimensional_vehiculoscontaminacion"}:

![\[\[fig:relaciondimensional\_vehiculoscontaminacion\]\]{#fig:relaciondimensional_vehiculoscontaminacion
label="fig:relaciondimensional_vehiculoscontaminacion"}Vehículos
Contaminación](Imagenes/relaciondimensional_vehiculoscontaminacion.png){width="80%"}

*Cubos*

Entre los distintos cubos potenciales a generar para realizar el
análisis, es posible visualizar la contaminación y la densidad vehicular
utilizando, por ejemplo, los siguientes niveles de las dimensiones, como
se muestra en
[\[fig:cubo\_vehiculos\_contaminacion\]](#fig:cubo_vehiculos_contaminacion){reference-type="ref"
reference="fig:cubo_vehiculos_contaminacion"}.

![\[\[fig:cubo\_vehiculos\_contaminacion\]\]{#fig:cubo_vehiculos_contaminacion
label="fig:cubo_vehiculos_contaminacion"}Cubo - Vehículos
Contaminación](Imagenes/cubo_vehiculos_contaminacion.png){width="80%"}

Lo que permite examinar la relación entre la contaminación y la densidad
vehicular según distintos criterios como: los barrios de Montevideo, los
tipos de contaminante, los métodos de medición, el tipo de día de la
semana, las estaciones del año, los rangos definidos de concentración de
cada contaminante según los parámetros de calidad de aire, los meses del
año, los períodos del día, los rangos de radiación solar global, humedad
relativa, temperatura externa, velocidad y dirección del viento y los
barrios en los que se encuentran las cámaras.

**Industrias Contaminación**

La relación dimensional Industrias Contaminación permite examinar la
relación entre la contaminación y la actividad industrial según los
distintos criterios dimensionales indicados en
[\[fig:relaciondimensional\_industriascontaminacion\]](#fig:relaciondimensional_industriascontaminacion){reference-type="ref"
reference="fig:relaciondimensional_industriascontaminacion"}:

![\[\[fig:relaciondimensional\_industriascontaminacion\]\]{#fig:relaciondimensional_industriascontaminacion
label="fig:relaciondimensional_industriascontaminacion"}Industrias
Contaminación](Imagenes/relaciondimensional_industriascontaminacion.png){width="80%"}

*Cubos*

Entre los distintos cubos potenciales a generar para realizar el
análisis, es posible visualizar la contaminación y la actividad
industrial utilizando, por ejemplo, los siguientes niveles de las
dimensiones, como se muestra en
[\[fig:cubo\_industriascontaminacion\]](#fig:cubo_industriascontaminacion){reference-type="ref"
reference="fig:cubo_industriascontaminacion"}.

![\[\[fig:cubo\_industriascontaminacion\]\]{#fig:cubo_industriascontaminacion
label="fig:cubo_industriascontaminacion"}Cubo - Industrias
Contaminación](Imagenes/cubo_industriascontaminacion.png){width="80%"}

Lo que permite examinar la relación entre la contaminación y la
actividad industrial según distintos criterios como: los centros
comunales zonales de Montevideo, los subtipos de contaminante, los
métodos de medición, las estaciones del año, los rangos definidos de
concentración de cada contaminante según los parámetros de calidad de
aire, los distintos años, los períodos del día, los rangos de radiación
solar global, humedad relativa, temperatura externa, velocidad y
dirección del viento y las industrias por sí solas.

**Días Importantes Contaminación**

La relación dimensional Días Importantes Contaminación permite examinar
la contaminación según los distintos criterios dimensionales indicados
en
[\[fig:relaciondimensional\_diasimportantescontaminacion\]](#fig:relaciondimensional_diasimportantescontaminacion){reference-type="ref"
reference="fig:relaciondimensional_diasimportantescontaminacion"}:

![\[\[fig:relaciondimensional\_diasimportantescontaminacion\]\]{#fig:relaciondimensional_diasimportantescontaminacion
label="fig:relaciondimensional_diasimportantescontaminacion"}Días
Importantes
Contaminación](Imagenes/relaciondimensional_diasimportantescontaminacion.png){width="80%"}

*Cubos*

Entre los distintos cubos potenciales a generar para realizar el
análisis, es posible visualizar la contaminación y los días importantes
utilizando, por ejemplo, los siguientes niveles de las dimensiones, como
se muestra en
[\[fig:cubo\_diasimportantescontaminacion\]](#fig:cubo_diasimportantescontaminacion){reference-type="ref"
reference="fig:cubo_diasimportantescontaminacion"}.

![\[\[fig:cubo\_diasimportantescontaminacion\]\]{#fig:cubo_diasimportantescontaminacion
label="fig:cubo_diasimportantescontaminacion"}Cubo - Días Importantes
Contaminación](Imagenes/cubo_diasimportantescontaminacion.png){width="80%"}

Lo que permite examinar la contaminación según distintos criterios como:
la estación de la red, los contaminantes, los métodos de medición, los
días de la semana, las estaciones del año, los rangos definidos de
concentración de cada contaminante según los parámetros de calidad de
aire, los semestres, los rangos de radiación solar global, humedad
relativa, temperatura externa, velocidad y dirección del viento y los
tipos de días importantes.

#### Estudio de aditividad {#diseno_logico_aditividad}

A continuación se presentan los estudios de aditividad separados por
cada relación dimensional.

**Vehículos Contaminación**

![\[\[fig:estudioaditividad\_vehiculoscontaminacion\]\]{#fig:estudioaditividad_vehiculoscontaminacion
label="fig:estudioaditividad_vehiculoscontaminacion"}Estudio Aditividad
- Vehículos
Contaminación](Imagenes/estudioaditividad_vehiculoscontaminacion.png){width="80%"}

**Industrias Contaminación**

![\[\[fig:estudioaditividad\_industriascontaminacion\]\]{#fig:estudioaditividad_industriascontaminacion
label="fig:estudioaditividad_industriascontaminacion"}Estudio Aditividad
- Industrias
Contaminación](Imagenes/estudioaditividad_industriascontaminacion.png){width="80%"}

**Días Importantes Contaminación**

![\[\[fig:estudioaditividad\_diasimportantescontaminacion\]\]{#fig:estudioaditividad_diasimportantescontaminacion
label="fig:estudioaditividad_diasimportantescontaminacion"}Estudio
Aditividad - Días Importantes
Contaminación](Imagenes/estudioaditividad_diasimportantescontaminacion.png){width="80%"}

### Diseño Lógico {#diseno_logico}

En la etapa de Diseño Lógico se realiza una especificación más detallada
que el esquema conceptual, donde se incorporan nociones de
almacenamiento y estructuración de los datos.

Se realiza la transformación al Esquema Lógico utilizando como puntos de
entrada:

1.  Esquema Conceptual abstracto generado en el Diseño Conceptual.

2.  Características de las Fuentes de Datos presentadas en la etapa de
    Análisis.

3.  Estrategias para resolver los requerimientos de performance y
    almacenamiento indicados en la Especificación de Requerimientos No
    Funcionales.

El enfoque tomado para la realización del Diseño Lógico es el
pasaje/traducción del Esquema Conceptual Multi-Dimensional al Esquema
Lógico. Dentro de los pasos a realizar para construir las estructuras
del DW se tienen:

1.  Incorporar al Esquema Conceptual los requerimientos no funcionales:

    1.  Operaciones críticas.

    2.  Frecuencias de operaciones.

    3.  Volúmenes de datos.

2.  Aplicar lineamientos de diseño.

3.  Realizar un mapeo con las Fuentes de Datos.

#### Incorporación al Esquema Conceptual de los requerimientos no funcionales {#diseno_logico_transformacion_relaciones_dimensionales}

Basados en el Modelo Dimensional presentado por Kimball, en el modo de
almacenamiento ROLAP, ya que así lo requería la herramienta Pentaho
utilizada para la implementación del proyecto, y en los aspectos y
características del sistema de BI en cuanto a frecuencia y criticidad de
operaciones y volúmenes de datos, se presenta el esquema lógico para
cada una de las Relaciones Dimensionales.

El esquema utilizado para definir la estructura de la base de datos
relacional del DW para cada relación fue el Star Cluster, combinación de
los esquemas Star y Snowflake. A su vez, debido a que se identifican
dimensiones compartidas entre los Star Cluster, se agrupan las mismas
para generar una Constelación.

Específicamente, se puede visualizar en
[\[fig:diseno\_logico\_star\_cluster\]](#fig:diseno_logico_star_cluster){reference-type="ref"
reference="fig:diseno_logico_star_cluster"} que se comparte la tabla de
Barrios y CCZ entre las dimensiones de Cámaras, Industrias y Estaciones
de la Red que forman parte de distintos Star Cluster.

![\[\[fig:diseno\_logico\_star\_cluster\]\]{#fig:diseno_logico_star_cluster
label="fig:diseno_logico_star_cluster"}Diseño Lógico - Star
Cluster](Imagenes/diseno_logico_star_cluster.png){width="80%"}

Teniendo en cuentas las Relaciones Dimensionales presentadas en el
Diseño Conceptual, se deben seguir los siguientes pasos para cada una:

1.  Identificar las tablas de dimensión y la tabla de hecho. Las tablas
    de dimensión se encontrarán en su mayoría desnormalizadas, al
    contener sus jerarquías embebidas, menos las que se encuentren
    compartidas entre distintas dimensiones.

2.  Unir la tabla de hecho con cada dimensión por una relación 1:N y
    asignar como clave de la tabla de hecho la unión de las claves de
    las dimensiones relacionadas.

Durante la etapa de diseño conceptual se definieron tres relaciones
dimensionales: Vehículos Contaminación, Industrias Contaminación y Días
Importantes Contaminación. A continuación se detalla el resultado de
traducir cada relación dimensional a su correspondiente esquema lógico
utilizando el procedimiento descrito.

**Vehículos Contaminación**

Como se puede apreciar en
[\[fig:diseno\_logico\_vehiculos\_contaminacion\]](#fig:diseno_logico_vehiculos_contaminacion){reference-type="ref"
reference="fig:diseno_logico_vehiculos_contaminacion"}, el esquema
lógico que se obtiene a partir de la relación dimensional Vehículos
Contaminación se estructura en torno a la tabla de hecho
*VehiculosContaminacion*. En cuanto a las medidas, existen atributos que
sirven a efectos del análisis definido para la relación dimensional. El
atributo *contaminacion* representa el valor de una medida histórica de
calidad de aire para un momento en específico, mientras que el atributo
*volumenVehiculos* corresponden a la suma de todos los vehículos de la
hora anterior a la fecha y hora del registro. En cuanto al resto de los
atributos son las claves foráneas a las tablas dimensionales
relacionadas, estas representan los objetos específicos relacionados a
cada valor como el contaminante que se mide, las unidades, el método de
medición y la cámara vehicular.

Asociado a la tabla de hechos, se pueden visualizar las distintas tablas
de dimensión, de las cuales es fácil notar que en su mayoría contienen
los atributos de todas sus jerarquías embebidos en ellas. Como ejemplo
se puede observar la tabla de la dimensión *Tiempo* que contiene los
atributos idFecha y fecha pertenecientes al nivel Fecha, idMes y mes
pertenecientes al nivel Mes y anio perteneciente al nivel Anio. La única
dimensión que no se encuentra desnormalizada es la *Barrios* y *CCZ*
debido a que es compartida por múltiples jerarquías de otras dimensiones
como *Estaciones de la Red* y *Cámaras*.

![\[\[fig:diseno\_logico\_vehiculos\_contaminacion\]\]{#fig:diseno_logico_vehiculos_contaminacion
label="fig:diseno_logico_vehiculos_contaminacion"}Diseño Lógico -
Vehículos
Contaminación](Imagenes/diseno_logico_vehiculos_contaminacion.png){width="80%"}

**Industrias Contaminación**

Como se puede apreciar en
[\[fig:diseno\_logico\_industrias\_contaminacion\]](#fig:diseno_logico_industrias_contaminacion){reference-type="ref"
reference="fig:diseno_logico_industrias_contaminacion"}, el esquema
lógico que se obtiene a partir de la relación dimensional Industrias
Contaminación se estructura en torno a la tabla de hecho
*IndustriasContaminacion*. En cuanto a las medidas, existen atributos
que sirven a efectos del análisis definido para la relación dimensional.
El atributo *contaminacion* representa el valor de una medida histórica
de calidad de aire promedio para el día, mientras que el atributo
*actividad* corresponde al nivel de actividad industrial promedio del
día. En cuanto al resto de los atributos son las claves foráneas a las
tablas dimensionales relacionadas, estas representan los objetos
específicos relacionados a cada valor como el contaminante que se mide,
las unidades, el método de medición y la industria.

Asociado a la tabla de hechos, se pueden visualizar las distintas tablas
de dimensión, de las cuales es fácil notar que en su mayoría contienen
los atributos de todas sus jerarquías embebidos en ellas. Como ejemplo
se puede observar la tabla de la dimensión *Contaminantes* que contiene
los atributos idContaminante y nomContaminante pertenecientes al nivel
Contaminante, idSubTipo y nomSubTipo pertenecientes al nivel SubTipo e
idTipo y nomTipo perteneciente al nivel Tipo. La única dimensión que no
se encuentra desnormalizada es la *Barrios* y *CCZ* debido a que es
compartida por múltiples jerarquías de otras dimensiones como
*Estaciones de la Red* y en dimensiones de otras relaciones
dimensionales como *Cámaras*.

![\[\[fig:diseno\_logico\_industrias\_contaminacion\]\]{#fig:diseno_logico_industrias_contaminacion
label="fig:diseno_logico_industrias_contaminacion"}Diseño Lógico -
Industrias
Contaminación](Imagenes/diseno_logico_industrias_contaminacion.png){width="80%"}

**Días Importantes Contaminación**

Como se puede apreciar en
[\[fig:diseno\_logico\_dias\_importantes\_contaminacion\]](#fig:diseno_logico_dias_importantes_contaminacion){reference-type="ref"
reference="fig:diseno_logico_dias_importantes_contaminacion"}, el
esquema lógico que se obtiene a partir de la relación dimensional Días
Importantes Contaminación se estructura en torno a la tabla de hecho
*DiasImportantesContaminacion*. En cuanto a las medidas, existen
atributos que sirven a efectos del análisis definido para la relación
dimensional. El atributo *contaminacion* representa el valor de una
medida histórica de calidad de aire promedio para el día y el único
atributo en la medida. En cuanto al resto de los atributos son las
claves foráneas a las tablas dimensionales relacionadas, estas
representan los objetos específicos relacionados a cada valor como el
contaminante que se mide, las unidades, el método de medición y el día
importante específico.

De forma análoga a los casos anteriores, asociado a la tabla de hechos,
se pueden visualizar las distintas tablas de dimensión, de las cuales es
fácil notar que en su mayoría contienen los atributos de todas sus
jerarquías embebidos en ellas, menos la jerarquía *Estaciones de la
Red*, *Barrios* y *CCZ*.

![\[\[fig:diseno\_logico\_dias\_importantes\_contaminacion\]\]{#fig:diseno_logico_dias_importantes_contaminacion
label="fig:diseno_logico_dias_importantes_contaminacion"}Diseño Lógico -
Días Importantes
Contaminación](Imagenes/diseno_logico_dias_importantes_contaminacion.png){width="80%"}

#### Aplicación de Lineamientos de Diseño {#diseno_logico_lineamientos_diseno}

Luego de la etapa de transformación del Esquema Conceptual al Lógico, es
necesario complementarla con indicaciones para resolver requerimientos
no funcionales. Para tal fin, se siguen distintos tipos de lineamientos
de diseño presentados en la sección de Marco teórico.

**Materialización de Relaciones Dimensionales**

Teniendo en cuenta las distintas relaciones dimensionales que se
presentan, se materializa un cubo por cada una con la mayor granularidad
posible para no perder información.

**Fragmentación Vertical de Dimensiones**

Basado en el diseño presentado, la dimensión *Estaciones de la Red*
contiene distintas jerarquías:

1.  Ubicación física.

2.  Tipo de equipamiento.

3.  Objetivo.

Debido a que la cantidad de datos almacenados en los distintos niveles
de la dimensión es relativamente pequeño y los mismos cambian
lentamente, entonces se define un único fragmento para todas las
jerarquías. Este enfoque tiene como características una redundancia
mínima, un mantenimiento y carga acorde debido a que se maneja sólo un
fragmento y una performance buena.

### Diseño Físico {#diseno_fisico}

En la etapa de Diseño Físico se realiza la representación de cómo se
implementará el modelo lógico en la base de datos específica a utilizar.
PostgreSQL es la base utilizada para el proyecto.

Se realiza la transformación al Esquema de Base de Datos utilizando como
puntos de entrada:

1.  Esquema Lógico generado en el Diseño Lógico.

2.  Características de las Fuentes de Datos presentadas en la etapa de
    Análisis.

3.  Aspectos específicos de PostgreSQL.

El enfoque y los pasos tomados para la realización del Diseño Físico
son:

1.  Convertir entidades en tablas.

2.  Convertir relaciones en claves externas.

3.  Convertir atributos en columnas.

4.  Modificar el modelo de datos físicos en función de las restricciones
    / requisitos físicos.

Con los objetivos de lograr un diseño de base de datos eficiente y
eficaz, teniendo en cuenta los tipos de datos que se almacenarán y los
requerimientos de carga de trabajo y tiempos de respuesta requeridos, se
realiza una investigación a fondo de los aspectos de la base de datos
seleccionada para cumplir los objetivos.

PostgreSQL provee varios tipos de datos con los que se puede trabajar,
facilitando de esta forma el diseño eficiente de la base de datos
[@postgreslql_data_types].

![\[\[fig:diseno\_fisico\_postgresql\]\]{#fig:diseno_fisico_postgresql
label="fig:diseno_fisico_postgresql"}PostgreSQL - Data
Types](Imagenes/diseno_fisico_postgresql.png){width="80%"}

Implementación {#implementacion_data_warehouse}
--------------

A continuación se presentan los distintos aspectos relacionados a la
implementación del sistema de BI y del DW.

### Extracción, transformación y carga (ETL) {#implementacion_carga_actualiación_etl}

Los procesos ETL son cruciales en la integración de datos, en
definitiva, es la fase de la etapa de Implementación que requiere una
mayor dedicación, esfuerzos y recursos para su completitud.

A continuación se dividen en dos secciones diferenciadas entre los
procesos de extracción, transformación y carga de las dimensiones y de
las tablas de hecho del DW.

#### Dimensiones {#implementacion_dimensiones}

**Estaciones de la Red**

En la
[\[fig:CargaEstacionesDeLaRed\]](#fig:CargaEstacionesDeLaRed){reference-type="ref"
reference="fig:CargaEstacionesDeLaRed"} se ilustra, en términos
generales, el proceso de carga de la dimensión Estaciones de la Red.

![\[\[fig:CargaEstacionesDeLaRed\]\]{#fig:CargaEstacionesDeLaRed
label="fig:CargaEstacionesDeLaRed"}Carga Estaciones De La
Red](Imagenes/CargaEstacionesDeLaRed.png){width="60%"}

*Obtener Estaciones de la Red*

En primera instancia se extraen los datos del archivo CSV fuente de
Estaciones de la Red.

*Obtener Barrios*

Se obtienen los Barrios de Montevideo desde la fuente de datos obtenida.

*Obtener CCZ*

Se obtienen los Centros Comunales Zonales de Montevideo desde la fuente
de datos obtenida.

*Consolidar Datos*

Se asocian los datos de Estaciones de la Red con los Barrios y los CCZ
de Montevideo.

*Generar Campos Geográficos*

Basado en los datos de ubicación de la estación de la red se genera el
campo de la base de datos geográfica para su posterior uso en los ETLs.

*Almacenar en DW*

En última instancia, se guardan los datos generados en la tabla
*dw.estacionesdelared*.

**Contaminantes**

En la
[\[fig:CargaContaminantes\]](#fig:CargaContaminantes){reference-type="ref"
reference="fig:CargaContaminantes"} se ilustra, en términos generales,
el proceso de carga de la dimensión Contaminantes.

![\[\[fig:CargaContaminantes\]\]{#fig:CargaContaminantes
label="fig:CargaContaminantes"}Carga
Contaminantes](Imagenes/CargaContaminantes.png){width="60%"}

*Obtener Contaminantes*

En primera instancia se extraen los datos del archivo CSV fuente de
Contaminantes.

*Obtener Categorías Contaminantes*

Se obtienen los datos de las distintas franjas para categorías de
calidad de aire según el valor de contaminación.

Se puede visualizar en
[\[fig:CargaContaminantesObtenerCategoriasContaminantes\]](#fig:CargaContaminantesObtenerCategoriasContaminantes){reference-type="ref"
reference="fig:CargaContaminantesObtenerCategoriasContaminantes"} las
categorías para cada contaminante:

![\[\[fig:CargaContaminantesObtenerCategoriasContaminantes\]\]{#fig:CargaContaminantesObtenerCategoriasContaminantes
label="fig:CargaContaminantesObtenerCategoriasContaminantes"}Carga
Contaminantes Obtener Categorías
Contaminantes](Imagenes/CargaContaminantesObtenerCategoriasContaminantes.png){width="60%"}

*Obtener Tipos y Subtipos de Contaminantes*

Se obtienen los datos de los distintos tipos y subtipos de
contaminantes.

*Consolidar Datos*

Se asocian los datos de Contaminantes y las franjas de Categorías de
Contaminantes.

*Almacenar en DW*

En última instancia, se guardan los datos generados en la tabla
*dw.contaminantes*.

**Métodos**

En la [\[fig:CargaMetodos\]](#fig:CargaMetodos){reference-type="ref"
reference="fig:CargaMetodos"} se ilustra, en términos generales, el
proceso de carga de la dimensión Métodos.

![\[\[fig:CargaMetodos\]\]{#fig:CargaMetodos
label="fig:CargaMetodos"}Carga
Métodos](Imagenes/CargaMetodos.png){width="60%"}

*Obtener Métodos*

En primera instancia se extraen los datos del archivo CSV fuente de
Métodos.

*Almacenar en DW*

En última instancia, se guardan los datos generados en la tabla
*dw.metodos*.

**Días de la Semana**

En la
[\[fig:CargaDiasDeLaSemana\]](#fig:CargaDiasDeLaSemana){reference-type="ref"
reference="fig:CargaDiasDeLaSemana"} se ilustra, en términos generales,
el proceso de carga de la dimensión Días de la Semana.

![\[\[fig:CargaDiasDeLaSemana\]\]{#fig:CargaDiasDeLaSemana
label="fig:CargaDiasDeLaSemana"}Carga Días de la
Semana](Imagenes/CargaDiasDeLaSemana.png){width="60%"}

*Generar Días de la Semana*

En primera instancia, se generan 7 filas (cantidad de días que hay en 1
semana). Se define para cada fila un único identificador secuencial que
comienza en 1 y finaliza en 7 para diferenciar los días.

*Calcular Campos*

Una vez generados los días de la semana, se calculan los demás campos
que forman parte de la dimensión. Para identificar el día de la semana
se utiliza una función de Date para poder definir el día de la semana
específico.

*Almacenar en DW*

En última instancia, se guardan los datos generados en la tabla
*dw.diassemana*.

**Estaciones del Año**

En la
[\[fig:CargaEstacionesDelAnio\]](#fig:CargaEstacionesDelAnio){reference-type="ref"
reference="fig:CargaEstacionesDelAnio"} se ilustra, en términos
generales, el proceso de carga de la dimensión Estaciones del Año.

![\[\[fig:CargaEstacionesDelAnio\]\]{#fig:CargaEstacionesDelAnio
label="fig:CargaEstacionesDelAnio"}Carga Estaciones del
Año](Imagenes/CargaEstacionesDelAnio.png){width="60%"}

*Generar Estaciones del Año*

En primera instancia, se generan 4 filas (cantidad de estaciones que hay
en 1 año). Se define para cada fila un único identificador secuencial
que comienza en 1 y finaliza en 4 para diferenciar las estaciones del
año.

*Calcular Campos*

Una vez generadas las estaciones del año, se calculan los demás campos
que forman parte de la dimensión. Para identificar la estación del año
se utiliza una función de Date para poder definir la estación del año
específica.

*Almacenar en DW*

En última instancia, se guardan los datos generados en la tabla
*dw.estacionesdelanio*.

**Contaminantes Categorías**

**Tiempo**

En la [\[fig:CargaTiempo\]](#fig:CargaTiempo){reference-type="ref"
reference="fig:CargaTiempo"} se ilustra, en términos generales, el
proceso de carga de la dimensión Tiempo.

![\[\[fig:CargaTiempo\]\]{#fig:CargaTiempo label="fig:CargaTiempo"}Carga
Tiempo](Imagenes/CargaTiempo.png){width="60%"}

*Generar Fechas*

En primera instancia, se generan 10.950 filas (cantidad de días que hay
en 30 años) con fechas consecutivas a partir de una fecha base. La fecha
base configurada en la ETL, elegida en base a que la Red de Monitoreo
comenzó a operar en 2005 pero existen datos desde 2003, es 01/01/2000.

*Calcular Campos*

Una vez generadas las fechas, se calculan los demás campos que forman
parte de la jerarquía. Para identificar la fecha, se utiliza una clave
subrogada de 8 dígitos con el siguiente formato AAAAMMDD, donde AAAA
representa el año, MM el mes y DD el día. En cuanto al nivel Mes se
calculan los siguientes dos campos: el identificador, que es un número
de 6 dígitos con el siguiente formato AAAAMM (análogo al identificador
de la fecha) y la descripción, que consiste del nombre del mes.
Finalmente, se calcula el año, completando así todos los niveles de la
jerarquía.

*Almacenar en DW*

En última instancia, se guardan los datos generados en la tabla
*dw.tiempo*.

**Horas**

En la [\[fig:CargaHoras\]](#fig:CargaHoras){reference-type="ref"
reference="fig:CargaHoras"} se ilustra, en términos generales, el
proceso de carga de la dimensión Horas.

![\[\[fig:CargaHoras\]\]{#fig:CargaHoras label="fig:CargaHoras"}Carga
Horas](Imagenes/CargaHoras.png){width="60%"}

*Generar Horas*

En primera instancia, se generan 24 filas (cantidad de horas que hay en
1 día). Se define para cada fila un único identificador secuencial que
comienza en 0 y finaliza en 23 para diferenciar las horas.

*Calcular Campos*

Una vez generadas las horas, se calculan los demás campos que forman
parte de la jerarquía. Para identificar los rangos de horas según la
parte del día se realiza el cálculo basado en la siguiente tabla:

  --------- -------------
  Hora      Descripción
  00 - 06   Madrugada
  07 - 12   Mañana
  13 - 19   Tarde
  20 - 23   Noche
  --------- -------------

*Almacenar en DW*

En última instancia, se guardan los datos generados en la tabla
*dw.horas*.

**Radiación Solar Global**

En la
[\[fig:CargaRadiacionSolarGlobal\]](#fig:CargaRadiacionSolarGlobal){reference-type="ref"
reference="fig:CargaRadiacionSolarGlobal"} se ilustra, en términos
generales, el proceso de carga de la dimensión Radiación Global Solar.

![\[\[fig:CargaRadiacionSolarGlobal\]\]{#fig:CargaRadiacionSolarGlobal
label="fig:CargaRadiacionSolarGlobal"}Carga Radiación Global
Solar](Imagenes/CargaRadiacionSolarGlobal.png){width="60%"}

*Generar Rangos Radiación Global Solar*

En primera instancia, se generan 3 filas (número de rangos) para
identificar cada rango. Se define para cada fila un único identificador
secuencial que comienza en 1 y finaliza en 3 para diferenciar los
rangos.

*Calcular Campos*

Una vez generados los rangos, se calculan los demás campos que forman
parte de la dimensión. Para identificar los rangos de radiación según
sus valores se realiza el cálculo basado en la siguiente tabla:

  ------------- -------------
  Valor         Descripción
  0 - 250       Bajo
  750 - 1000    Medio
  1000 - 1500   Alto
  ------------- -------------

*Almacenar en DW*

En última instancia, se guardan los datos generados en la tabla
*dw.radiacionsolarglobal*.

**Humedad Relativa**

En la
[\[fig:CargaHumedadRelativa\]](#fig:CargaHumedadRelativa){reference-type="ref"
reference="fig:CargaHumedadRelativa"} se ilustra, en términos generales,
el proceso de carga de la dimensión Humedad Relativa.

![\[\[fig:CargaHumedadRelativa\]\]{#fig:CargaHumedadRelativa
label="fig:CargaHumedadRelativa"}Carga Humedad
Relativa](Imagenes/CargaHumedadRelativa.png){width="60%"}

*Generar Rangos Humedad Relativa*

En primera instancia, se generan 3 filas (número de rangos) para
identificar cada rango. Se define para cada fila un único identificador
secuencial que comienza en 1 y finaliza en 3 para diferenciar los
rangos.

*Calcular Campos*

Una vez generados los rangos, se calculan los demás campos que forman
parte de la dimensión. Para identificar los rangos de humedad relativa
según sus valores se realiza el cálculo basado en la siguiente tabla:

  ------------ -------------
  Valor        Descripción
  0% - 40%     Baja
  40% - 70%    Media
  70% - 100%   Alta
  ------------ -------------

*Almacenar en DW*

En última instancia, se guardan los datos generados en la tabla
*dw.humedadrelativa*.

**Temperatura Externa**

En la
[\[fig:CargaTemperaturaExterna\]](#fig:CargaTemperaturaExterna){reference-type="ref"
reference="fig:CargaTemperaturaExterna"} se ilustra, en términos
generales, el proceso de carga de la dimensión Temperatura Externa.

![\[\[fig:CargaTemperaturaExterna\]\]{#fig:CargaTemperaturaExterna
label="fig:CargaTemperaturaExterna"}Carga Temperatura
Externa](Imagenes/CargaTemperaturaExterna.png){width="60%"}

*Generar Rangos Temperatura Externa*

En primera instancia, se generan 4 filas (número de rangos) para
identificar cada rango. Se define para cada fila un único identificador
secuencial que comienza en 1 y finaliza en 4 para diferenciar los
rangos.

*Calcular Campos*

Una vez generados los rangos, se calculan los demás campos que forman
parte de la dimensión. Para identificar los rangos de temperatura
externa según sus valores se realiza el cálculo basado en la siguiente
tabla:

  ---------- -------------
  Valor      Descripción
  Hasta 5    Baja
  5 - 20     Media
  20 - 35    Alta
  Desde 35   Muy Alta
  ---------- -------------

*Almacenar en DW*

En última instancia, se guardan los datos generados en la tabla
*dw.temperaturaexterna*.

**Viento Dirección**

En la
[\[fig:CargaVientoDireccion\]](#fig:CargaVientoDireccion){reference-type="ref"
reference="fig:CargaVientoDireccion"} se ilustra, en términos generales,
el proceso de carga de la dimensión Viento Dirección.

![\[\[fig:CargaVientoDireccion\]\]{#fig:CargaVientoDireccion
label="fig:CargaVientoDireccion"}Carga Viento
Dirección](Imagenes/CargaVientoDireccion.png){width="60%"}

*Generar Rangos Viento Dirección*

En primera instancia, se generan 8 filas (número de rangos) para
identificar cada rango. Se define para cada fila un único identificador
secuencial que comienza en 1 y finaliza en 8 para diferenciar los
rangos.

*Calcular Campos*

Una vez generados los rangos, se calculan los demás campos que forman
parte de la dimensión. Para identificar los rangos de la dirección del
viento según su rumbo se realiza el cálculo basado en la siguiente
tabla:

  ------- -------------
  Valor   Descripción
  \-      N
  \-      NE
  \-      E
  \-      SE
  \-      S
  \-      SW
  \-      W
  \-      NW
  ------- -------------

*Almacenar en DW*

En última instancia, se guardan los datos generados en la tabla
*dw.vientodireccion*.

**Viento Velocidad**

En la
[\[fig:CargaVientoVelocidad\]](#fig:CargaVientoVelocidad){reference-type="ref"
reference="fig:CargaVientoVelocidad"} se ilustra, en términos generales,
el proceso de carga de la dimensión Viento Velocidad.

![\[\[fig:CargaVientoVelocidad\]\]{#fig:CargaVientoVelocidad
label="fig:CargaVientoVelocidad"}Carga Viento
Velocidad](Imagenes/CargaVientoVelocidad.png){width="60%"}

*Generar Rangos Viento Velocidad*

En primera instancia, se generan 13 filas (número de rangos) para
identificar cada rango. Se define para cada fila un único identificador
secuencial que comienza en 1 y finaliza en 13 para diferenciar los
rangos.

*Calcular Campos*

Una vez generados los rangos, se calculan los demás campos que forman
parte de la dimensión. Para identificar los rangos de la velocidad del
viento según su intensidad se realiza el cálculo basado en la siguiente
tabla:

  --------- -----------------
  Valor     Descripción
  0-1       Calma
  2-5       Ventolina
  6-11      Brisa muy débil
  12-19     Brisa ligera
  20-28     Brisa moderada
  29-38     Brisa fresca
  39-49     Brisa fuerte
  50-61     Viento fuerte
  62-74     Viento duro
  75-88     Viento muy duro
  89-102    Temporal
  103-117   Borrasca
  118 \>    Huracán
  --------- -----------------

*Almacenar en DW*

En última instancia, se guardan los datos generados en la tabla
*dw.vientovelocidad*.

**Cámaras**

En la [\[fig:CargaCamaras\]](#fig:CargaCamaras){reference-type="ref"
reference="fig:CargaCamaras"} se ilustra, en términos generales, el
proceso de carga de la dimensión Cámaras.

![\[\[fig:CargaCamaras\]\]{#fig:CargaCamaras
label="fig:CargaCamaras"}Carga
Cámaras](Imagenes/CargaCamaras.png){width="60%"}

*Obtener Conteo Vehicular*

En primera instancia se extraen los datos del archivo CSV fuente de
Conteo Vehicular.

*Extraer Cámaras*

Se agrupan los datos para obtener las cámaras que se encuentran
asociados a los valores de conteo vehicular. Para ello, se utiliza como
clave los datos de identificación de las cámaras.

*Obtener Barrios*

Se obtienen los Barrios de Montevideo desde la fuente de datos obtenida.

*Obtener CCZ*

Se obtienen los Centros Comunales Zonales de Montevideo desde la fuente
de datos obtenida.

*Consolidar Datos*

Se asocian los datos de Cámaras con los Barrios y los CCZ de Montevideo.

*Generar Campos Geográficos*

Basado en los datos de ubicación de la cámara se genera el campo de la
base de datos geográfica para su posterior uso en los ETLs.

*Almacenar en DW*

En última instancia, se guardan los datos generados en la tabla
*dw.camaras*.

**Industrias**

En la
[\[fig:CargaIndustrias\]](#fig:CargaIndustrias){reference-type="ref"
reference="fig:CargaIndustrias"} se ilustra, en términos generales, el
proceso de carga de la dimensión Industrias.

![\[\[fig:CargaIndustrias\]\]{#fig:CargaIndustrias
label="fig:CargaIndustrias"}Carga
Industrias](Imagenes/CargaIndustrias.png){width="60%"}

*Generar Industrias*

Con el objetivo de cargar industrias a medida que se obtienen datos de
actividad, y en una primer instancia se obtienen datos de ADME, se
genera 1 fila para ingresarla. Se adicionan datos de descripción y
ubicación geográfica.

*Obtener Barrios*

Se obtienen los Barrios de Montevideo desde la fuente de datos obtenida.

*Obtener CCZ*

Se obtienen los Centros Comunales Zonales de Montevideo desde la fuente
de datos obtenida.

*Consolidar Datos*

Se asocian los datos de Industrias con los Barrios y los CCZ de
Montevideo.

*Generar Campos Geográficos*

Basado en los datos de ubicación de la industria se genera el campo de
la base de datos geográfica para su posterior uso en los ETLs.

*Almacenar en DW*

En última instancia, se guardan los datos generados en la tabla
*dw.industrias*.

**Días Importantes**

En la
[\[fig:CargaDiasImportantes\]](#fig:CargaDiasImportantes){reference-type="ref"
reference="fig:CargaDiasImportantes"} se ilustra, en términos generales,
el proceso de carga de la dimensión Días Importantes.

![\[\[fig:CargaDiasImportantes\]\]{#fig:CargaDiasImportantes
label="fig:CargaDiasImportantes"}Carga Días
Importantes](Imagenes/CargaDiasImportantes.png){width="60%"}

*Generar Días Importantes*

Con el objetivo de cargar días importantes a medida que se identifican,
en una primer instancia se obtienen datos días festivos en Uruguay y se
generan tantas filas para ingresarlos. Se adicionan datos de descripción
y su tipo. Posteriormente los especialistas de la IM podrán cargar los
días importantes que deseen.

*Almacenar en DW*

En última instancia, se guardan los datos generados en la tabla
*dw.diasimportantes*.

#### Tablas de Hecho {#implementacion_tablas_hecho}

**Vehículos Contaminación**

En la
[\[fig:CargaVehiculosContaminacion\]](#fig:CargaVehiculosContaminacion){reference-type="ref"
reference="fig:CargaVehiculosContaminacion"} se ilustra, en términos
generales, el proceso de carga de la tabla de hechos Vehículos
Contaminación.

![\[\[fig:CargaVehiculosContaminacion\]\]{#fig:CargaVehiculosContaminacion
label="fig:CargaVehiculosContaminacion"}Carga Vehículos
Contaminación](Imagenes/CargaVehiculosContaminacion.png){width="60%"}

*Obtener Conteo Vehicular*

Se extraen los datos del archivo CSV fuente de Conteo Vehicular.

*Obtener Cámaras del DW*

Se obtienen los datos de la dimensión Cámaras con el objetivo de ser
utilizado posteriormente.

*Obtener Mediciones Históricas*

Se extraen los datos del archivo CSV de Mediciones Históricas.

*Obtener Contaminantes, Contaminantes Categorías, Métodos y Estaciones
de la Red del DW*

Se obtienen los datos de las distintas dimensiones relacionadas a las
Mediciones Históricas con el objetivo de ser utilizado posteriormente.

*Obtener Datos Meteorológicos*

Se extraen los datos del archivo XLS provisto por ANCAP de Datos
Meteorológicos obtenidos en la refinería de ANCAP.

*Obtener Radiación Solar Global, Humedad Relativa, Temperatura Externa,
Viento Dirección y Viento Velocidad del DW*

Se obtienen los datos de las distintas dimensiones relacionadas a los
Datos Meteorológicos con el objetivo de ser utilizado posteriormente.

*Consolidar Datos Conteo Vehicular*

Se asocian los datos obtenidos de Conteo Vehicular con los datos de la
dimensión Cámaras.

*Consolidar Datos Mediciones Históricas*

Se asocian los datos obtenidos de Mediciones Históricas con los datos de
las distintas dimensiones relacionadas.

*Consolidar Datos Meteorológicos*

Se asocian los datos Meteorológicos obtenidos con los datos de las
distintas dimensiones relacionadas. Cabe destacar que no se realiza un
filtrado de los datos meteorológicos teniendo en cuenta la distancia de
la fuente de medición de los mismos con las cámaras o estaciones de la
red debido a que se indica por los especialistas que los datos medidos
son representativos para el departamento de Montevideo en general.

*Join por distancia \< 1km*

Se realiza un join entre los datos obtenidos de Conteo Vehicular y
Mediciones Históricas para filtrar y relacionar los datos obtenidos de
estaciones de monitoreo y cámaras de conteo vehicular que se encuentren
a un radio de más de *1km*, como se definió en la etapa de Análisis.

*Consolidar Datos Temporales*

Se asocian, los datos relacionados y filtrados de contaminación y
volumen vehicular, con los datos temporales para su posterior uso.

*Almacenar en DW*

En última instancia, se guardan los datos relacionados en la tabla
*dw.vehiculoscontaminacion*.

**Industrias Contaminación**

En la
[\[fig:CargaIndustriasContaminacion\]](#fig:CargaIndustriasContaminacion){reference-type="ref"
reference="fig:CargaIndustriasContaminacion"} se ilustra, en términos
generales, el proceso de carga de la tabla de hechos Industrias
Contaminación.

![\[\[fig:CargaIndustriasContaminacion\]\]{#fig:CargaIndustriasContaminacion
label="fig:CargaIndustriasContaminacion"}Carga Industrias
Contaminación](Imagenes/CargaIndustriasContaminacion.png){width="60%"}

*Obtener Actividad Industrial*

Se extraen los datos del archivo CSV fuente de Actividad Industrial.

*Obtener Industrias del DW*

Se obtienen los datos de la dimensión Industrias con el objetivo de ser
utilizado posteriormente.

*Obtener Mediciones Históricas*

Se extraen los datos del archivo CSV de Mediciones Históricas.

*Obtener Contaminantes, Contaminantes Categorías, Métodos y Estaciones
de la Red del DW*

Se obtienen los datos de las distintas dimensiones relacionadas a las
Mediciones Históricas con el objetivo de ser utilizado posteriormente.

*Obtener Datos Meteorológicos*

Se extraen los datos del archivo XLS provisto por ANCAP de Datos
Meteorológicos obtenidos en la refinería de ANCAP.

*Obtener Radiación Solar Global, Humedad Relativa, Temperatura Externa,
Viento Dirección y Viento Velocidad del DW*

Se obtienen los datos de las distintas dimensiones relacionadas a los
Datos Meteorológicos con el objetivo de ser utilizado posteriormente.

*Consolidar Datos Actividad Industrial*

Se asocian los datos obtenidos de Actividad Industrial con los datos de
la dimensión Industrias.

*Consolidar Datos Mediciones Históricas*

Se asocian los datos obtenidos de Mediciones Históricas con los datos de
las distintas dimensiones relacionadas.

*Consolidar Datos Meteorológicos*

Se asocian los datos Meteorológicos obtenidos con los datos de las
distintas dimensiones relacionadas. Cabe destacar que no se realiza un
filtrado de los datos meteorológicos teniendo en cuenta la distancia de
la fuente de medición de los mismos con las industrias o estaciones de
la red debido a que se indica por los especialistas que los datos
medidos son representativos para el departamento de Montevideo en
general.

*Join por distancia \< 3km*

Se realiza un join entre los datos obtenidos de Actividad Industrial y
Mediciones Históricas para filtrar y relacionar los datos obtenidos de
estaciones de monitoreo e industrias de actividad industrial que se
encuentren a un radio de más de *3km*, como se definió en la etapa de
Análisis.

*Consolidar Datos Temporales*

Se asocian, los datos relacionados y filtrados de contaminación y
actividad industrial, con los datos temporales para su posterior uso.

*Almacenar en DW*

En última instancia, se guardan los datos relacionados en la tabla
*dw.industriascontaminacion*.

**Días Importantes Contaminación**

En la
[\[fig:CargaDiasImportantesContaminacion\]](#fig:CargaDiasImportantesContaminacion){reference-type="ref"
reference="fig:CargaDiasImportantesContaminacion"} se ilustra, en
términos generales, el proceso de carga de la tabla de hechos Días
Importantes Contaminación.

![\[\[fig:CargaDiasImportantesContaminacion\]\]{#fig:CargaDiasImportantesContaminacion
label="fig:CargaDiasImportantesContaminacion"}Carga Días Importantes
Contaminación](Imagenes/CargaDiasImportantesContaminacion.png){width="60%"}

*Obtener Días Importantes del DW*

Se obtienen los datos de la dimensión Días Importantes con el objetivo
de ser utilizado posteriormente.

*Obtener Mediciones Históricas*

Se extraen los datos del archivo CSV de Mediciones Históricas.

*Obtener Contaminantes, Contaminantes Categorías, Métodos y Estaciones
de la Red del DW*

Se obtienen los datos de las distintas dimensiones relacionadas a las
Mediciones Históricas con el objetivo de ser utilizado posteriormente.

*Obtener Datos Meteorológicos*

Se extraen los datos del archivo XLS provisto por ANCAP de Datos
Meteorológicos obtenidos en la refinería de ANCAP.

*Obtener Radiación Solar Global, Humedad Relativa, Temperatura Externa,
Viento Dirección y Viento Velocidad del DW*

Se obtienen los datos de las distintas dimensiones relacionadas a los
Datos Meteorológicos con el objetivo de ser utilizado posteriormente.

*Consolidar Datos Mediciones Históricas*

Se asocian los datos obtenidos de Mediciones Históricas con los datos de
las distintas dimensiones relacionadas.

*Consolidar Datos Meteorológicos*

Se asocian los datos Meteorológicos obtenidos con los datos de las
distintas dimensiones relacionadas. Cabe destacar que no se realiza un
filtrado de los datos meteorológicos teniendo en cuenta la distancia de
la fuente de medición de los mismos estaciones de la red debido a que se
indica por los especialistas que los datos medidos son representativos
para el departamento de Montevideo en general.

*Consolidar Datos Temporales*

Se asocian los datos relacionados y filtrados de contaminación con los
datos temporales para su posterior uso.

*Almacenar en DW*

En última instancia, se guardan los datos relacionados en la tabla
*dw.diasimportantescontaminacion*.

### Implementación de cubos {#implementacion_de_cubos}

[Implementación de cubos]{style="color: red"}

### Generación de reporte de BI de sección en Informe Anual {#generacion_reporte_seccion}

[Generación de reporte de BI de sección en Informe
Anual]{style="color: red"}
