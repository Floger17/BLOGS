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
