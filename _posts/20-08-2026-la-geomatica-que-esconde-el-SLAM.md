---
layout: post
title: "La Geomática que esconde el SLAM"
date: 20/08/2026
image: /assets/img/MIRA_TOPOGRAFICA.jpg
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

### La ficha técnica está para algo.

A menudo se asume que operar un escáner SLAM consiste únicamente en encender el equipo y caminar. Sin embargo, la propia ficha técnica del CHCNAV RS7 pone de manifiesto la necesidad imperiosa del criterio geomático:

* **Deriva inercial (IMU):** Una inestabilidad de sesgo de giroscopio de 0.5/h es un dato excelente, pero evidencia matemática de que el error inercial se acumula con el tiempo. Ignorar esto y realizar itinerarios infinitos sin cierres de bucle ni bases de apoyo es condenar la nube a una deformación geométrica.
* **Reflectividad y física del láser:** Un alcance de 40m sobre un $10\%$ de reflectividad exige al operador entender cómo absorben la onda de 905nm las superficies húmedas o la vegetación en obras de drenaje, obligando a planificar las distancias de pasada con criterio.
* **Precisión Relativa vs. Absoluta:** Diferenciar entre la consistencia métrica interna (<1cm) y la georreferenciación global (<3cmRMS) evita el mito del "escaneo automático". Sin un diseño geométrico de GCPs y una selección analítica del protocolo de red en la colectora, la precisión absoluta se degrada.

Interpretar los límites físicos de la instrumentación antes de salir a campo es la línea divisoria entre el rigor de la ingeniería geomática y el desconocimiento operativo.
