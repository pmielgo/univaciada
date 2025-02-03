# Univaciada: acceso de la españa vaciada al sistema universitario​
Proyecto presentado al concurso "II Datathon UniversiDATA".
El repositorio contiene todos los conjuntos de datos extraídos de las diferentes fuentes abiertas (Universidata, Instituto Nacional de Estadística e Informes del Ministerio de Educación y Deportes) almacenadas en tres carpetas:
- comprimido. Contiene los ficheros que, por su gran tamaño, se cargan comprimidos.
- raw. Contiene los ficheros cargados sin compresión.
- smart. Contiene los ficheros ya procesados y los modelos entrenados.

Por otro lado, se presentan tres cuadernos con código en Python.
- preprocesamiento.ipynb. Contiene las operaciones de preprocesamiento y preparación de datos llevadas a cabo sobre los conjuntos originales.
- modelos.ipynb. Contiene el entrenamiento de los modelos posteriormente utilizados en el dashboard.
- dashboard.ipynb. Contiene el código generado para la creación de la herramienta de visualización propuesta.

# Problemática a resolver. Detalle el problema o desafío que quiere resolver o ayudar a resolver con su proyecto

El término “España vaciada” hace referencia a aquellas zonas de España que han experimentado fuertes olas de emigración desde el éxodo rural de la segunda mitad del siglo XX hasta la actualidad. Aunque la industrialización impulsó el inicio de esa migración del campo a la ciudad, en este siglo XXI la tendencia se está intensificando. Tal es el grado de despoblación, que ha pasado a considerarse uno de los ejes principales de la Estrategia Nacional frente al Reto Demográfico [1]. Por ello, se han llevado a cabo diferentes estudios que analizan el impacto del problema. Uno de ellos, encargado por el Ministerio para la Transición Ecológica y el Reto Demográfico [2], destaca la pérdida de población que han sufrido el 61,9% de los municipios españoles entre 2001 y 2017. Además, esta disminución de habitantes es significativa, puesto casi la mitad de los municipios han sufrido pérdidas de entre el 10% y el 50% de la población. Como es de esperar, esto impacta de lleno en la sociedad, generando desafíos estructurales y de gestión, que también afectan al sistema educativo.

La disminución del número de niños en edad escolar en municipios afectados por la despoblación supone una reducción del número de docentes asignados a ese territorio. Por otro lado, no favorece las inversiones para dotar a los centros de recursos e infraestructuras tecnológicas que sí se están instalando en centros urbanos. Esto genera un alto grado de disparidad en las aulas. Por un lado, se encuentran clases con un número reducido de estudiantes que utilizan métodos tradicionales, como libros y pizarra, mientras que, en el otro extremo, se encuentran aulas con un equipamiento informático avanzado y una posible sobrecarga de alumnado. Por no hablar de que en muchas ocasiones los pequeños centros rurales se ven obligados a cerrar de forma permanente, y sus estudiantes a desplazarse a otros centros educativos que pueden encontrarse a grandes distancias de sus casas.

Podría entonces pensarse que estas diferencias, que dependen del grado de despoblación de los municipios, podrían influir en el proceso de aprendizaje de los alumnos, tanto en etapas tempranas, como en la etapa universitaria. De esta forma, la despoblación podría estar limitando el número de estudiantes que acceden al sistema universitario, y por tanto, discriminando en cierto modo a la “España vaciada”. Por ello, la problemática que se pretende abordar en este proyecto es la posible relación existente entre zonas despobladas y el sistema universitario, analizando si el acceso a la universidad es significativamente diferente según la densidad de población de los municipios de origen del estudiantado.

[1] Estrategia Nacional frente al Reto Demográfico, Ministerio de Política Territorial y Memoria Democrática. Accedido el 17/09/2024 en https://mpt.gob.es/reto_demografico/Estrategia_Nacional.html

[2] Diagnóstico Estrategia Nacional frente al Reto Demográfico. Eje despoblación. Ministerio para la Transición Ecológica y el Reto Demográfico. Accedido el 17/09/2024 en https://www.miteco.gob.es/content/dam/miteco/es/reto-demografico/temas/analisis-cartografia/diagnostico_eje_despoblacion_tcm30-517769.pdf

# Solución propuesta.

En vista a la existencia de diferencias en el sistema educativo de los municipios según su densidad poblacional, se pretende analizar el potencial impacto que pueden tener en la etapa universitaria. La propuesta es un dashboard interactivo que permita responder a las siguientes cuestiones:

- ¿Existen diferencias porcentuales en el número de estudiantes universitarios según la densidad de su municipio de origen? ¿Y de manera proporcional al número de habitantes en edad universitaria?

- ¿Estas posibles diferencias varían entre universidades?

- ¿Influyen los recursos de los centros educativos en los conocimientos con los que se incorporan los alumnos al sistema universitario?

- ¿Cómo influye el cierre de colegios e institutos en las oportunidades universitarias de sus estudiantes?

Aunque nos hemos planteado analizar otra serie de cuestiones como si el rendimiento académico de estudiantes procedentes de entornos rurales es similar al que presentan estudiantes procedentes de grandes núcleos urbanos, no nos ha sido posible debido al proceso de anonimización. Es por ello que la solución propuesta se centrará únicamente en el acceso a la universidad.
El dashboard se compondrá de tres pestañas, que pretendemos que sean tan interactivas como sea posible:

- La primera de ellas busca presentar información general sobre la presencia de las diferentes regiones del país en el sistema universitario. Para ello se mostrará un mapa de España sobre el que se señalará con burbujas la procedencia de los diferentes estudiantes universitarios. Además, para facilitar la visualización, el mapa permitirá la aplicación de filtros por densidad poblacional, curso y Universidad. Por otro lado, se mostrarán estadísticas generales por género y rama de estudio (ingeniería y arquitectura, ciencias, …) según la densidad poblacional de los municipios de origen. Estas gráficas también serán interactivas de forma que el usuario pueda seleccionar universidades o cursos concretos.

- En la segunda ventana se analizarán las diferencias entre regiones y entre localidades con diferente densidad poblacional en la nota de acceso a la Universidad. Nuevamente, sobre un mapa interactivo se mostrará la nota media de acceso por curso y región, junto con gráficos de barras y de sectores que analicen las diferencias según la densidad poblacional de los centros educativos de origen. En este caso, también se podrán aplicar filtros por Universidades y curso.

- Para la última ventana se busca analizar el impacto del cierre de colegios en el acceso al sistema universitario. Para ello, se mostrará sobre un mapa el número de centros educativos que se han cerrado o abierto en un periodo determinado, que podrá ser elegido de manera interactiva por el usuario. Por otro lado, se presenta sobre un gráfico de líneas la evolución temporal del número de centros en funcionamiento, el número de estudiantes que acceden al sistema universitario y la población media por comunidad autónoma. También se añadirá un modelo predictivo que estime el número de alumnos que accederán en el futuro a una determinada Universidad (a elegir por el usuario) en base a parámetros como el cierre de centros educativos por comunidad. Por último, se incorporará un simulador interactivo, que permita modelar el impacto de la reapertura de centros educativos en el acceso futuro a la Universidad.
  
Desde el punto de vista técnico, se realizará un análisis inicial de los datos con R Studio. Por otro lado, el dashboard se desarrollará con el Framework de Python Plotly Dash y se conectará con una base de datos alojada en un sistema como MongoDB o MariaDB. Además, se pretende desplegar la aplicación en un servidor, permitiendo su acceso desde un dominio público y no solo de manera local.

# Identificación de destinatarios.

En primer lugar, el proyecto sería de gran utilidad para las universidades que colaboran activamente con Universidata (Universidad de Valladolid, Universidad Complutense de Madrid, Universidad Autónoma de Madrid, Universidad Carlos III de Madrid y Universidad Rey Juan Carlos de Madrid), ya que les permitiría conocer el posible impacto que puede tener la educación que reciben sus estudiantes en etapas previas según su región y localidad de origen. Además, podrían basarse en el estudio para identificar regiones poco representadas en sus centros y poder diseñar nuevas estrategias de reclutamiento específicas, orientadas a esos perfiles. Además, a largo plazo, las universidades que se unan a la plataforma de datos abiertos también podrían beneficiarse de la herramienta, puesto que representa la información con independencia de sus conjuntos de datos.

En segundo lugar, también sería útil para el Ministerio de Universidades, que podría valorar la posible brecha existente entre zonas despobladas frente a grandes núcleos urbanos. De esta forma, el análisis del acceso a la Universidad en diferentes entornos permitiría identificar posibles disparidades y favorecer la creación de políticas y programas más equitativos y justos.

Por otro lado, el proyecto también está destinado a los responsables políticos del sector educativo, tanto a nivel regional como nacional. El proyecto puede ser una herramienta útil para evaluar la calidad de las políticas educativas vigentes en las etapas básicas (Infantil, Primaria, Secundaria y Bachillerato) y analizar cómo estas pueden influir en etapas posteriores. A través de los datos recogidos, se podrán identificar las regiones con menores tasas de acceso a estudios superiores, lo que facilitaría la toma de decisiones más informadas en la asignación de recursos, inversiones, becas y programas de apoyo.

Por último, el proyecto también tendría un impacto directo sobre los estudiantes y familias que residen en zonas despobladas. Estos colectivos podrían estar percibiendo la existencia de una barrera de acceso a la Universidad, debido a la falta de recursos tecnológicos o a la necesidad de mudarse a grandes ciudades. El dashboard presentará casos de estudiantes procedentes de entornos similares, pero también resaltará los desafíos y las desigualdades existentes, creando conciencia sobre la problemática existente.

# Utilidad del proyecto

La finalidad principal del proyecto es estudiar la posible relación existente entre las localidades de origen de los estudiantes con el acceso a la Universidad. Aunque hemos encontrado trabajos que analizan la educación en zonas rurales, no tenemos constancia de que estos estudios se hayan centrado nunca en el impacto de la despoblación en la posterior etapa universitaria. Por tanto, nos parece una propuesta muy novedosa. Además, consideramos que los datos proporcionados en la plataforma Universidata presentan un caso de estudio ideal, al permitirnos comparar Universidades de una de las comunidades que está recibiendo más afluencia de migración en los últimos años, como es Madrid, con datos de la Universidad de Valladolid, ubicada en Castilla y León, una de las comunidades más afectadas por la despoblación. No obstante, queremos mencionar que esto constituiría un análisis inicial de la problemática descrita en apartados superiores. En el proyecto se plantea el estudio del acceso a la Universidad, pero sería interesante utilizar datos de la propia etapa universitaria (como créditos matriculados, superados, …) para valorar posibles diferencias en el rendimiento. Esto en la actualidad no es posible puesto que el proceso de anonimización utilizado por la plataforma sitúa en diferentes bloques de coherencia los municipios de origen y otros datos académicos.

La utilidad principal del proyecto es la de informar y sensibilizar de la problemática que pueden tener las tendencias de despoblación, así como visibilizar cómo las medidas que se toman en consecuencia pueden influir en una posible marginación de minorías en la etapa universitaria. De esta forma, en un futuro podrían diseñarse políticas educativas centradas en disminuir las brechas existentes entre áreas rurales y urbanas, creando, por ejemplo, programas específicos de apoyo financiero, realizando mejoras en la infraestructura o facilitando el acceso a recursos educativos. Todo esto contribuiría a alcanzar un sistema más equitativo y justo, en el que el lugar de nacimiento no fuera un condicionante.

Por otro lado, la mejora en las condiciones educativas podría tener un impacto indirecto al incentivar el retorno de la población a las zonas rurales, dado que, en muchas ocasiones, la preocupación por la baja calidad educativa constituye uno de los factores que impulsan a la migración a núcleos urbanos. Adicionalmente, esta mejora podría generar un efecto económico positivo reflejado en la creación de empleo o la inversión en materiales y recursos tecnológicos. Por último, aunque el proyecto solo busca visibilizar las dificultades presentes en zonas rurales en el sector educativo, también podría suscitar cuestionamientos respecto a la calidad de otros servicios, como el sanitario.

# Conjuntos de datos a utilizar

Para desarrollar el proyecto utilizaremos distintos conjuntos de datos, tanto del banco de documentos de la página web de UniversiDATA, como datos extraídos del INE y algunos informes publicados por el Gobierno.


1 UNIVERSIDATA

De los datos abiertos universitarios publicados en el portal de UniversiDATA, vamos a utilizar todos aquellos relativos al acceso y matriculación tanto de la Universidad de Valladolid como de las distintas universidades de la Comunidad de Madrid de los cursos que están disponibles (esto es, desde el curso académico 2017/18 hasta el curso 2022/23). Tanto en los conjuntos de datos relativos al acceso como en los relativos a las matrículas tenemos como variables pivotes del proceso de anonimización el código del centro (cod_centro) y su correspondiente descodificación (des_centro), el código de la titulación (cod_titulación) y su correspondiente descodificación (des_titulacion) y el código que representa el género del estudiante (cod_genero) y su correspondiente descodificación (des_genero).

Nosotras vamos a centrar nuestro interés en las variables que recogen los códigos de los municipios de residencia. En particular, para el caso de los conjuntos de datos relativos al acceso nos vamos a fijar en la variable que contiene el código del municipio donde cada estudiante realizó sus estudios de secundaria (cod_municipio_centro_sec) que pertenece al tercer bloque de coherencia. Por otro lado, en el caso de los datos relativos a las matrículas nos vamos a centrar en la variable que alberga el municipio de residencia habitual del estudiante (cod_municipio_residencia) que se encuentra en el quinto bloque de coherencia.

Teniendo en cuenta que ninguna de las variables en las que centramos nuestro estudio se trata de una variable pivote de los distintos procesos de anonimización de los conjuntos de datos, no podemos realizar un estudio tan profundo como nos gustaría, ya que nos tenemos que ceñir a trabajar únicamente con las variables pertenecientes a los bloques de coherencia 3 y 5 de los distintos procesos de anonimización. Por ejemplo, este inconveniente nos impide poder realizar un estudio del rendimiento académico de los estudiantes universitarios procedentes de zonas menos pobladas respecto a los que provienen de grandes ciudades por no pertenecer a los mismos bloques de coherencia las variables relativas al municipio de residencia y las relativas a los créditos matriculados, superados y no superados, en el caso del conjunto de datos de las matrículas, que también sería de gran interés.
(Estos conjuntos de datos pueden consultarse en el siguiente enlace: https://www.universidata.es/ )

2 INE

Para poder desarrollar nuestro proyecto necesitamos separar los municipios españoles en distintos grupos siguiendo como criterio la población, por lo tanto, haremos uso de un conjunto de datos extraído de la página web del INE, que recoge la población de los distintos municipios del país con una periodicidad anual desde 1998 hasta 2023.

(Los datos pueden consultarse en el siguiente enlace: https://www.ine.es/jaxiT3/Tabla.htm?t=2904&L=0 )


3 INFORMES DEL MINISTERIO DE EDUCACIÓN Y DEPORTE

Por último, para poder desarrollar el simulador necesitamos saber el número de colegios/institutos que han estado activos en los diferentes cursos escolares. Esta información la hemos recogido de unos anuarios estadísticos que publica el Gobierno sobre las cifras de la educación en España.

De todos los datos disponibles en dichos anuarios, centraremos nuestra atención en las tablas que contabilizan el número de centros docentes según el tamaño del municipio. La división que se hace para los tamaños de los municipios es la siguiente: hasta 1000 habitantes, entre 1.001 y 2.000, entre 2.001 y 5.000, entre 5.001 y 10.000, entre 10.001 y 25.000, entre 25.001 y 100.000, entre 100.001 y 500.000 y más de 500.001 habitantes. Estos mismos rangos son los que utilizaremos para dividir los municipios españoles por población con los datos extraídos del INE anteriormente comentados.

(Estos conjuntos de datos se pueden consultar en el siguiente enlace: https://www.educacionfpydeportes.gob.es/servicios-al-ciudadano/estadisticas/indicadores/cifras-educacion-espana.html )
