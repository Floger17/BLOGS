---
layout: post
title: "La Geomática que esconde el SLAM"
date: 20/08/2026
image: /assets/img/SLAM4.jpg
---

<style> /* Justifica todos los párrafos y listas del artículo */ main p, main ul, main ol { text-align: justify; } /* Mantiene el pie de foto centrado */ figcaption { text-align: center !important; } </style>

Hoy en día, con un sensor SLAM cualquiera puede pasearse alegremente por el monte o entre infraestructuras urbanas e industriales escaneando el entorno que le rodea. Cualquiera sabe caminar despacio y trazar eses suaves. Sin embargo, no todos entienden la Geomática que esconde esta tecnología. A menudo, por la facilidad de pulsar un botón y empezar a andar, se olvida que para ejecutar un levantamiento riguroso —sea cual sea el objetivo— es imprescindible aplicar conocimientos de geodesia y topografía. Comprender cómo se comporta el instrumento es la única vía para evitar que el trabajo se transforme en una pérdida de tiempo, esfuerzo y recursos.

En esta entrada abordaremos las claves metodológicas del SLAM a raíz de mi última experiencia en prácticas extracurriculares, donde ejecuté el levantamiento de obras de drenaje transversales (ODTs) e infraestructuras hidráulicas mediante el escáner CHCNAV RS7.

## La georreferenciación

Existen distintas metodologías de georreferenciación que he ido consolidando sobre el terreno y que resultan críticas en cualquier proyecto donde se exija un mínimo de precisión.

### Sin georreferenciación directa en tiempo real (modo Offline / Post-procesado)

Esta manera es la más fiable técnicamente. Ya que no dependes del envío de correcciones diferenciales en tiempo real para obtener la nube georreferenciada durante la captura. Para ello, la metodología idónea consiste en materializar previamente bases de estacionamiento mediante GNSS RTK y registrar dichas bases como puntos de control (GCPs) durante el itinerario del escaneo. Posteriormente, en la fase de gabinete, basta con importar el fichero `.txt` con las coordenadas absolutas de dichas bases para ajustar la trayectoria y encajar el modelo digital. Con un correcto diseño del recorrido y el debido cierre de bucles, el error medio cuadrático resultante oscilará holgadamente en valores iguales o inferiores a 2 cm.

### Mediante correcciones NTRIP en tiempo real (RTK)

Es otra manera de abordarlo, aunque exige evaluar rigurosamente la estabilidad del enlace de datos de la operadora de telefonía y la cobertura de red existente. En entornos con vegetación densa, encajonamientos o cañones urbanos, la señal multipath y las pérdidas de ciclo degradan sensiblemente la calidad del posicionamiento. Esto es un concepto elemental en la profesión: confiar a ciegas en un receptor GNSS entre calles estrechas o bajo dosel boscoso sin un control geométrico independiente es una temeridad metodológica para la rigurosidad del levantamiento.

Mantener un enlace RTK activo mediante un servicio NTRIP agiliza el trabajo, pero no es garante por sí solo de una georreferenciación absoluta precisa. Para garantizar la calidad métrica es imprescindible el apoyo en puntos de control y bases con coordenadas absolutas previamente consolidadas. 

### Una buena configuración previa, un levantamiento de éxito

Dentro de la propia aplicación móvil de captura (*SmartGo Neo*), la parametrización de los servicios RTK —desde la selección del tipo de servicio (*SWAAS*, *CORS*, *API*...) hasta la elección deliberada de la fuente (*VRS3*, *FKP3*, *RTCM*...)— resulta un paso determinante para la viabilidad del proyecto. Seleccionar la configuración idónea según la tipología del terreno y la disponibilidad de red no es un mero trámite operativo; es la decisión técnica que condiciona el rendimiento en campo. Omitir este análisis previo suele ser la causa directa de que, en la fase de procesamiento, surjan anomalías y la nube de puntos no se georreferencie correctamente. El criterio profesional empieza en la Colectora, eligiendo de forma analítica la opción que garantiza la máxima estabilidad del dato.

### La ficha técnica está para algo

A menudo se asume que operar un escáner SLAM consiste únicamente en encender el equipo y caminar. Sin embargo, la propia ficha técnica del CHCNAV RS7 pone de manifiesto la necesidad imperiosa del criterio geomático:

* **Deriva inercial (IMU):** Una inestabilidad de sesgo de giroscopio de 0.5°/h es un dato excelente, pero evidencia matemática de que el error inercial se acumula con el tiempo. Ignorar esto y realizar itinerarios infinitos sin cierres de bucle ni bases de apoyo es condenar la nube a una deformación geométrica.
* **Reflectividad y física del láser:** Un alcance de 40 m sobre un 10% de reflectividad exige al operador entender cómo absorben la onda de 905 nm las superficies húmedas o la vegetación en obras de drenaje, obligando a planificar las distancias de pasada con criterio.
* **Precisión Relativa vs. Absoluta:** Diferenciar entre la consistencia métrica interna (<1cm) y la georreferenciación global (<3cm RMS) evita el mito del "escaneo automático". Sin un diseño geométrico de GCPs y una selección analítica del protocolo de red en la colectora, la precisión absoluta se degrada.

Interpretar los límites físicos de la instrumentación antes de salir a campo es la línea divisoria entre el rigor de la ingeniería geomática y el desconocimiento operativo.

## El terreno no perdona: Geometría, bucles y la física del barranco

Poseer un sensor de última generación no exime de aplicar la planificación clásica de un levantamiento. Durante el trabajo en infraestructuras hidráulicas y obras de drenaje bajo viaductos, el entorno impone restricciones físicas donde el algoritmo SLAM es puesto a prueba en sus cimientos matemáticos.

### La trampa de la simetría y la degeneración geométrica

El algoritmo SLAM necesita "agarrarse" a planos, bordes y características geométricas diferenciadas para encajar fotogramas consecutivos. En el interior de ODTs tubulares, marcos de hormigón continuos o barrancos de morfología homogénea con vegetación densa, el entorno carece de variabilidad espacial. 

Si el sensor no detecta cambios geométricos significativos a medida que se avanza, se produce la **degeneración del SLAM**: el sistema "patina", perdiendo la noción de la distancia recorrida en el eje de avance y provocando un empaquetamiento o estiramiento ficticio del modelo 3D.

### Por qué la física desaconseja el descenso al cauce desde la plataforma

Durante las mediciones, surgió la cuestión operativa de si era conveniente descender a la base del barranco manteniendo las bases de referencia únicamente en la plataforma superior del puente. La respuesta desde la ingeniería geomática es tajante: **no**.

1. **Despalancamiento vertical y pérdida de cota (Z):** Para que los puntos de control (GCPs) garanticen la precisión absoluta, deben envolver tridimensionalmente el objeto medido. Ubicar las bases exclusivamente en la calzada superior crea una geometría plana que deja "volando" el fondo del cauce, degradando la componente altimétrica.
2. **Aceleración de la deriva inercial:** El tránsito por laderas escarpadas, suelos movedizos o vegetación obliga al operador a realizar giros bruscos y perder el paso fluido. Esto fuerza la aceleración del sesgo inercial de la IMU (0.5°/h), introduciendo un error angular acumulado difícil de purgar.
3. **Trayectorias en "callejón sin salida":** Las bajadas a desnivel sin posibilidad de trazar recorridos circulares impiden ejecutar un **cierre de bucle (*Loop Closure*)** efectivo. Al no poder re-visitar un punto conocido para que el software distribuya y minimice el error acumulado, la trayectoria se convierte en una antena abierta propensa a la deformación.

Rechazar un recorrido físicamente inviable en campo no es una negativa injustificada; es la aplicación estricta de la geodesia para garantizar que el producto final sea un plano de ingeniería y no un boceto tridimensional.

## Conclusión: El valor del criterio frente al automatismo

El avance de la tecnología ha democratizado la captura masiva de datos, pero no ha sustituido la necesidad del pensamiento analítico. Un escáner SLAM no es una cámara fotográfica inteligente; es un sensor complejo condicionado por la propagación de errores, la propagación de ondas infrarrojas y el cálculo matricial de trayectorias.

Apretando botones cualquiera puede generar una nube de puntos vistosa. Sin embargo, saber dónde colocar las bases, cómo configurar la colectora, cuándo cerrar un bucle y qué itinerarios rechazar por física elemental es lo que distingue al mero usuario de la tecnología del verdadero profesional de la Geomática.

## Mi experiencia en campo: Cuando la realidad supera a la teoría

Por mucha planificación metodológica que se realice, el trabajo de campo en proyectos reales siempre está condicionado por imprevistos logísticos, limitaciones del terreno y restricciones de recursos. La verdadera Geomática no solo se aplica en las condiciones ideales de laboratorio, sino en la capacidad de adaptar el rigor técnico a las circunstancias de cada jornada.

### El primer test: Criterio propio frente a 8 centímetros de error

Recuerdo mi primer día en la empresa. Me entregaron el escáner SLAM con la consigna de comprobar la medición que había realizado previamente otro compañero. En el plano final, elaborado tras procesar la nube de puntos, la estructura medía **8.30 m**, mientras que la cota real sobre el terreno era de **8.38 m**. Una discrepancia de **8 cm**: un margen inasumible para un levantamiento con pretensiones de ingeniería.

Sin haber utilizado un escáner SLAM hasta ese momento, pero con la base conceptual adquirida, decidí bajar al terreno con el plano en mano. Antes de realizar el primer recorrido:
* **Analicé la ficha técnica** del instrumento para comprender sus parámetros de captura y drift inercial.
* **Diseñé un croquis de recorrido** lógico dentro del jardín del parque empresarial, definiendo un itinerario con bucles cerrados y seleccionando la ubicación estratégica de los puntos de control (GCPs).
* **Afronté el procesamiento en gabinete:** Aunque nadie en la empresa me explicó el flujo de trabajo en *CoPre*, apliqué la lógica de ajuste vectorial e importación de puntos.

El resultado del procesado arrojó una dimensión de **8.394 m**, reduciendo el error a tan solo **1.4 cm**. Comprobar que el rigor metodológico y la planificación previa daban frutos inmediatos confirmó mi enfoque: ese mismo estándar analítico debía aplicarse a cada una de las obras de drenaje transversal (ODTs) que me asignaran.

### Adaptación en ODTs y la paradoja del hardware

En las salidas a campo para el levantamiento de obras hidráulicas bajo viaductos, líneas férreas o carreteras, la realidad imponía sus propias restricciones:
* **Incompatibilidad de enlaces:** Muchas laderas y cauces secos impedían ejecutar un recorrido continuo (empezar arriba en la calzada, descender al cauce y volver a subir). Tampoco era viable dividir la captura en dos nubes independientes (una superior y otra inferior) al no disponer de dianas físicas ni geometría de solape para el registro posterior.
* **Limitaciones extremas en gabinete:** Para el procesado en remoto desde el hotel, se me asignó un equipo portátil muy limitado (*HP ZBook 15*, 8 GB de RAM). El equipo de escritorio del despacho —un i5 con 8 GB de RAM— contaba únicamente con **15 GB de almacenamiento libre** en su disco interno, una capacidad del todo insuficiente para gestionar el volumen de datos de nubes de puntos pesadas. Para evitar el colapso del sistema y garantizar las entregas, tuve que estructurar un flujo de trabajo mediante unidades de almacenamiento externo de alta velocidad.

### Automatización, GIS y control de datos por iniciativa propia

Para no solapar los trabajos de campo con el topógrafo encargado de materializar las bases, establecí una ventana de coordinación de al menos 24 horas. A partir de sus archivos `.dwg`, desarrollé un flujo de automatización propio para optimizar la toma de datos y el gabinete:

1. **Extracción y contextualización espacial en QGIS:** Mediante scripts y complementos de AutoCAD, extraía las coordenadas absolutas de las bases a ficheros `.txt`. En QGIS, combinaba espacialmente estos puntos con las capas `.kml` del proyecto para vincular los atributos del código de obra, el identificador único y el término municipal correspondiente, evitando trabajar con bases "anónimas".
2. **Generación automática de ficheros de control en Python:** Desarrollé un script en Python para parsear la base de datos exportada (`.csv`) y generar automáticamente archivos `.txt` estructurados exclusivamente por nombre y código. Así, al importar los GCPs en *CoPre*, la asignación de bases era directa y libre de errores humanos.
3. **Control de campo en tiempo real con QField:** Diseñé un formulario personalizado en *QField* para la colectora móvil. Registraba la fecha, el operador, fotografías del entorno, observaciones técnicas de la estructura y el estado de finalización del municipio (configurado con reglas de estilo para tachar automáticamente las zonas completadas).

Ninguno de estos protocolos me fue exigido. Nacieron de la necesidad de sustituir la improvisación por una metodología ordenada, garantizando la trazabilidad total del dato desde la colectora en campo hasta el entregable final. Después, extraía esa nueva capa en un .csv, y con un script en Pyhon, hice que me generase archivos `.txt` que eran únicamente y exclusivamente por Nombre y código, para luego, en CoPre, a la hora de introducir las bases del topógrafo, no tenía que estar buscando cuál era cuál y asiganrla a los puntos de control. A su vez, para llevar un control en tiempo real durante la salida de campo, usé Qfield, donde me generé una capa, en la que rellenaba fecha, autor del escaneado (ya que no iba solo), la opción a subir foto, comentario de alguna observación a tener en cuenta. Y tachar municpio que terminaba, que se tachara automáticamente al rellenar la casilla de si se había finalizado el municipio o no. Todo con el fin para llevar un control y un orden. Y esto, por cuenta propia, ya que nadie en su día me exigió que lo hiciera.

### Visualizando el flujo: Del campo a la colectora

Para entender este despliegue de control y organización, nada como ver la herramienta en su entorno real. Durante las jornadas en las ODTs, la combinación entre la colectora móvil y la planificación espacial fue la clave para no perder el rumbo entre decenas de infraestructuras:

![Interfaz de QField utilizada en campo para el control de ODTs y bases](/assets/img/TU_FOTO_QFIELD.jpg)
*Figura 1: Capa personalizada en QField para el seguimiento en tiempo real, registro de observaciones y control de estado por municipios.*

![Captura del escáner SLAM CHCNAV RS7 durante el levantamiento de una ODT](/assets/img/TU_FOTO_ODT.jpg)
*Figura 2: Posicionamiento y flujo de pasada del CHCNAV RS7 en el entorno de una obra de drenaje transversal.*

---

## El contrapunto perfecto: La EDAR de Pinedo y el valor del trabajo en equipo

Mi trayectoria en estas prácticas no se limitó a lidiar con barrancos complejos o limitaciones de hardware. El verdadero potencial de la tecnología SLAM —combinada con una metodología impecable— se hizo evidente cuando me asignaron el levantamiento de la Estación Depuradora de Aguas Residuales (EDAR) de Pinedo.

En esta ocasión, compartí jornada con un compañero arquitecto: un profesional excepcional, con una calidad humana intachable y un respeto absoluto por el criterio geomático. A diferencia de otros escenarios donde se primaba la prisa sobre la técnica, aquí se estableció un diálogo técnico fluido desde el primer minuto.

### Georreferenciación por NTRIP y encadenamiento de nubes en Pinedo

En la EDAR de Pinedo prescindimos de la materialización previa de bases GNSS clásicas. En su lugar, configuré por primera vez en la colectora la conexión por correcciones **NTRIP en tiempo real** aprovechando la buena cobertura del entorno. Sin embargo, consciente de que el RTK por sí solo no garantiza la rigidez geométrica de nubes complejas, diseñé una estrategia de **encadenamiento relativo con puntos de apoyo en elementos claros**:

1. **Selección de puntos de control naturales:** Identifiqué elementos estructurales indiscutibles y bien definidos en el propio recinto de la depuradora (esquinas de arquetas, vértices de tanques, marcas fijas) para usarlos como referencias de amarre.
2. **Estrategia de enlace por solape (Puntos de transferencia):** Para dar continuidad entre escaneos sin generar descalibres, estructuré las pasadas de forma encadenada. Si la Nube 1 finalizaba apoyándose en un elemento claro (Punto D), la Nube 2 comenzaba tomando como origen exacto ese mismo Punto D de la Nube 1.
3. **Aprovechamiento de la riqueza geométrica:** Los tanques de decantación, canalizaciones y edificaciones auxiliares ofrecían planos limpios continuos. Esto permitió que el algoritmo SLAM trabajara holgadamente, sin riesgo de degeneración ni pérdidas de trayectoria.

![Nube de puntos / Escaneo de la EDAR de Pinedo](/assets/img/TU_FOTO_PINEDO.jpg)
*Figura 3: Levantamiento mediante SLAM en la EDAR de Pinedo, combinando NTRIP y puntos de apoyo encadenados.*

El resultado final fue **excelente**. La nube global no solo quedó correctamente orientada y georreferenciada en el sistema de referencia, sino que la continuidad entre pasadas presentó una consistencia métrica impecable, situándose holgadamente dentro de las tolerancias admisibles para ingeniería e infraestructura hidráulica.

## Reflexión final

Esta experiencia en Pinedo demostró la conclusión definitiva de mi paso por estas prácticas: **el escáner SLAM no es una varita mágica ni un instrumento caprichoso; es un sensor condicionado al 100% por el factor humano y la estrategia del operador**. 

Cuando se minusvalora la geodesia, se escatima en control geométrico o se trabaja a ciegas, la tecnología responde con datos inservibles. Pero cuando se comprende la física del sensor, se planifica el encadenamiento de datos con criterio técnico y existe una colaboración profesional basada en el respeto mutuo, los resultados rozan la perfección.
