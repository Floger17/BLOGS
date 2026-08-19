---
layout: post
title: "Topografía al rescate"
date: 27/07/2025
image: /assets/img/MIRA_TOPOGRAFICA.jpg
---

<style> /* Justifica todos los párrafos y listas del artículo */ main p, main ul, main ol { text-align: justify; } /* Mantiene el pie de foto centrado */ figcaption { text-align: center !important; } </style>

# TOPOGRAFÍA AL RESCATE

Tras los trágicos acontecimientos a causa de la DANA del 29 de octubre de 2024 en Valencia. Creo que es interesante explicar cómo se puede cartografiar este fenómeno con tan graves consecuencias para el pueblo valenciano, y como valenciano y estudiante de Ingeniería Geomática y Topografía, siento la obligación moral de exponer qué se ha hecho desde el campo de la geomática y la topografía para dar explicación técnica y objetiva a lo sucedido y cómo la topografía puede dar respuestas a estas cuestiones.

En este blog, se pretende exponer los pasos a seguir, junto con mi experiencia como voluntario en un proyecto realizado por el grupo de Cartografía GeoAmbiental y Teledetección (CGAT) del Departamento de Ingeniería Cartográfica, Geodesia y Fotogrametría de la Universidad Politécnica de Valencia (UPV), universidad de la cual soy estudiante. De este proyecto han participado 9 profesores (de los cuales, algunos trabajan también en el departamento), 8 del CGAT y 5 alumnos (en el que me incluyo).

La topografía, los Sistemas de Información Geográficos (SIG), y la Teledetección han sido herramientas claves para la elaboración del visor cartográfico elaborado por el CGAT. 

El proyecto se llama "DANA carrer a carrer" (en castellano "*DANA calle a calle*") consta de 3 fases.

## Fase 1: Levantamiento de campo con mira topográfica
La primera parte del proyecto, consistió en hacer una salida de campo con una mira topográfica y con una aplicación móvil QField, donde, a partir de mirar la altura de la lámina de agua con una mira topográfica, se sitúa el lugar, poniendo la medición, la altura del agua, alguna observación a tener en cuenta, y con la posibilidad de poder introducir una fotografía con el teléfono.

<figure style="text-align: center; margin: 2rem 0;">
  <img src="/assets/img/MIRA_TOPOGRAFICA.jpg" alt="Descripción de la imagen" style="max-width: 100%; height: auto; border-radius: 8px;">
  <figcaption style="font-size: 0.85rem; color: #64748b; margin-top: 0.5rem; font-style: italic;">
    Imagen de una mira topográfica. Medición en Horno de Alcedo (Valencia).
  </figcaption>
</figure>


Durante los meses de noviembre del 2024 hasta mayo de 2025 se han realizado un total de 6500 mediciones, de las cuales, mis aportaciones fueron considerables, con 1113 mediciones en las pedanías de La Torre, Horno de Alcedo y Castellar-l'Oliveral, y municipios como Sedaví, Alfafar, Massanassa, Mislata, Torrent y área de la Albufera, y todas las mediciones han sido en la comarca de l'Horta Sud, la mayoría en zonas urbanas, como a su vez en áreas rústicas. La localización utilizada fue con el GPS de los propios teléfonos móviles, con el fondo de Open Street Map (OSM) y la ortofoto del PNOA.  se procederá a la validación en gabinete con el software QGIS.

## Fase 2: Validación de datos y generación de los modelos de lamina de agua
En esta segunda fase, se ha realizado en gabinete, primero, la comprobación de los datos obtenidos. Posteriormente la creación de la lámina de agua.

## Fase 3: Mapa final
En la última fase se ha realizado el mapa, con una rampa de colores, en el que los colores azules son cotas bajas, y a mayor color cálido y rojizo mayor altura. Y creación de un visor interactivo.

## Conclusiones
Las conclusiones del trabajo muestran que la apertura de las presas no son las causantes de esta crecida de los ríos Turia, Magro y del barranco del Poyo.

Otras conclusiones que se sacan es que las viviendas próximas a las carreteras y ferrocarriles, más afectados se han visto.

Ejemplos:

* **La Torre:** Sitiada por el ferrocarril, CV-407, la avenida del Sur (CV-400) y el nuevo cauce del Turia. Con cotas de 1.925 en las casitas que están cerca de la CV-406 y de la Avenida Real de Madrid y cotas de más de 2 metros en el campo de fútbol del Discóbolo A.C y de 1.79 en la C/Ismael Blat Pintor y C/de Giménez i Costa.

* **Horno de Alcedo:** Sitiada por el ferrocarril, cauce nuevo del Turia y la pista de Silla (V-31). A mayor proximidad del cauce nuevo del Turia (llegaba a superar fácilmente el metro de altura en las edificaciones próximas al cauce y de la Avenida Europa) y cuanto mayor sea la proximidad a la V-31 mayor era la cota (superando sin dificultades los 2 metros, como en la barraca que hay en la calle camino de Alabau) y edificios próximos a la pista de Silla.

* **Castellar-l'Oliveral:** Comprendida entre la pista de Silla y la Avenida del Doctor Ruiz i Comes, las edificaciones próximas a esta avenida superaba el metro sin dificultades.

* **Pinedo:** La autopista del Saler (CV-500) al estar más elevado sirvió de dique de contención, salvando a la población de la inundación.
Con estos ejemplos se expresa que las carreteras y ferrocarriles pueden alterar las inundaciones.

Otra conclusión es que la topografía, (como es de esperar), es también un agente importante.

*¿Por qué Catarroja estuvo más afectada que Massanassa si ambas poblaciones están a orillas del barranco del Poyo?*

Se debe simplemente a un factor de la topografía del propio terreno, es decir, que Catarroja está más próxima al nivel del mar que Massanassa, y el nombre de algunas avenidas o calles también revelan información topográfica, como en la "Avenida de la Rambleta" (también en Catarroja), y no es descabellado pensar que el nombre refleja una realidad geográfica, ya no es casualidad que esa misma calle estuviera más afectada que otras calles de la propia población de Catarroja, con cotas de más de los dos metros y medio de altura.

Otro ejemplo lo encontramos en la localidad vecina de Massanassa, en la Avenida de Blasco Ibáñez, donde a la derecha de la carretera en dirección a Valencia estuvo menos afectada que la de la izquierda.

*¿Por qué los barrios de San Isidro, San Marcelino, La Punta y Nazaret no han sido afectados y sin embargo La Torre, Horno de Alcedo y Castellar-l'Oliveral sí?*

Esto se debe a la disposición del cauce nuevo del Turia, en el que los barrios de la ciudad de Valencia están más elevados que los del otro lado del cauce nuevo del Turia. Por lo que, se puede decir que el Plan Sur ha salvado a la ciudad de Valencia y ha cumplido su función, que no era otra que la de desviar el agua de su cauce natural para evitar inundaciones, esta obra (el Plan Sur) se realizó en consecuencia a la riada del 57, otro episodio traumático para el pueblo valenciano en el que hubieron muchos muertos (los datos oficiales indican más de 80, pero se estima que fue mayor el número de muertos) y daños materiales muy importantes. Y lo mismo sucede con Manises, Paterna y Quart de Poblet, por estar elevados, no se han inundado.

Y por último, un factor posible que explique cómo es posible que en zonas próximas al barranco del Poyo llegara al metro de altura del agua mientras que en otros sitios a orillas del barranco son de más de 3 metros, o calles que estando a la misma altura del mar esté una de ellas con mayor altura de agua que la otra calle, esto es debido a la posibilidad de que la concentración de vehículos arrastrado por la fuerza del agua hicieran de dique, por lo que, este factor, es también relevante.

## Experiencia personal
Al ser voluntario en este proyecto del CGAT es entendible que no haya participado en todas las fases del proyecto dado que soy estudiante. La primera salida de campo fue a inicios del mes de diciembre, empezando con un compañero en Massanassa, después por mi cuenta empecé a realizar mediciones en La Torre, y una vez finalicé la zona, me desplacé a Sedaví, así, de manera ordenada, empezando en un sitio y no cambiando hasta terminar la zona. Mi cronología de sitios fue Massanassa (con un compañero de clase), La Torre, Sedaví, Alfafar (con el mismo compañero de clase la primera vez, y el resto de salidas por mi cuenta), Horno de Alcedo, Castellar-l'Oliveral, Mislata (la zona que está al otro lado del cauce nuevo del Turia) y Torrent (estos dos últimos fueron casi simultáneos, y a Torrent fui en bici cuando aun no funcionaba el transporte público).

En esta última localidad fue curioso, porque fue la última población de estudio que faltaba por hacer, y fui el primero en empezar en la toma de datos, los tomé cerca de los barrios de Benissaet y del Chenillet, a orillas del barranco.

Tras mis salidas de campo, dada la gran cantidad de mediciones que hice (1113/6500 mediciones con la mira topográfica) tuve el privilegio de poder participar en una parte de la segunda fase, en la validación de mis puntos con QGIS y en gabinete. Todos los 1113 puntos fueron supervisados y comprobados.

Recuerdo que esto del gabinete, iba después de mis clases por las mañanas me pasaba por el CGAT y hacía mi tarea, algunas veces empezaba a las 12:00 y terminaba a las 18:00 o incluso más tarde. Pero a mi entender, sí mereció la pena, porque el 29 de enero de 2025 salió el proyecto publicado, y tuvo mucha repercusión mediática y en los periódicos. Saliendo en periódicos como El País, Las Provincias, El Levante E.M.V, Valencia Secreta, Europa Press, y en páginas web de RTVE, Onda Cero, y otros medios como La Cuatro, Telecinco... y otros medios locales como À Punt o la 7TeleValencia. Y como no, al ser un proyecto del CGAT, perteneciente a mi escuela, la ETSIGCT, también publicaron la noticia en sus páginas webs y redes sociales, tanto la ETSIGCT, como la UPV como a su vez, el COIGT, el Ilustre Colegio Oficial de Ingenieros en Geomática y Topografía, del cual, soy precolegiado, y a su vez, estuvimos en la Feria del Invento de la Ciudad de las Artes y las Ciencias del viernes 9 de mayo, evento que fue abierta al público, y este proyecto, sus frutos dio, al ser datos que manejan ayuntamientos afectados por la DANA, la Confederación Hidrográfica del Júcar (CHJ) y el Institut Cartogràfic Valencià (ICV) con la capa de "UPV" como ente que ha aportado datos.

<figure style="text-align: center; margin: 2rem 0;">
  <img src="assets/img/Captura_ICV.png" alt="Descripción de la imagen" style="max-width: 100%; height: auto; border-radius: 8px;">
  <figcaption style="font-size: 0.85rem; color: #64748b; margin-top: 0.5rem; font-style: italic;">
    Captura de pantalla del visor del ICV.
  </figcaption>
</figure>

Y dejando de lado la parte técnica, ha sido un proyecto realmente enriquecedor en lo personal, porque es ver con tus propios ojos las aplicaciones reales de los conocimientos técnicos sobre geomática y topografía para entender, de una manera objetiva y libre de fanatismos ideológicos, entender y comprender qué ha sucedido, cómo ha sucedido y qué se puede hacer para evitar que otra catástrofe como esta vuelva a hacer tanto daño en lo material y humanitario de los valencianos.

Cuando iba con la mira topográfica por las calles, algunos, me paraban y me preguntaban si era del ayuntamiento, a lo que siempre respondía que era voluntario que estaba en un proyecto de la universidad. Muchos me miraron con muy buenos ojos, me enseñaron videos, me contaron sus experiencias durante la DANA y de los días posteriores donde la ayuda era inexistente. Y sobre todo, el ver las noticias a través de una pantalla era una cosa, pero una vez allí, con zapatillas sucias para poder usarlas para meterme en lugares donde aun tras 2 meses seguían con barro y polvo, y olor a tuberías atascadas de las calles, el ver los coches en los descampados, todo destrozado y con un ambiente grisáceo, sucio, verlo con tus ojos, y ver y escuchar las experiencias de quienes me pararon para hablarme, eso es lo impactante, lo enriquecedor.

Ningún vecino me puso mala cara, nadie me habló de malas formas, todo lo contrario, me enseñaron vídeos, fotos, que me servían para ver la marca de agua en las calles, ya que, también se daba el caso de que cuando iba buscando marcas, algunas veces no las encontraba, y algunos vecinos, gracias a su vídeos, fotos y experiencias pude dar una medición para el proyecto. Y también, agradecer al Ejército de Tierra que me permitió estar en zonas y calles que no estaban permitidas el paso, como los bomberos que actuaban en la zona, estaban cortadas al público, dejando que hiciera la medición y contentos de que lo que estaba haciendo valía para algo y que era de importancia para la causa y para futuras riadas de este tipo, por lo que, en lo personal estoy muy agradecido y es una anécdota de la experiencia de la salida de campo para la toma de datos.

Y a su vez, un profesor mío, y director del CGAT, y quien fue el segundo perito que fue a declarar sobre el juicio de la DANA, me felicitó en lo personal, por mi contribución al proyecto y que mis aportaciones, a parte de haber sido grandes, han sido buenas y de calidad. Y es un halago y un orgullo recibir ese reconocimiento. Pero claro, no se me ha pagado por ello, lo único que me consuela es el saber que mi contribución ha podido ser útil para las poblaciones afectadas.

En lineas generales estoy muy agradecido a los vecinos por su hospitalidad y amabilidad.

# Reflexiones personales
## La DANA
Mis reflexiones, tras lo sucedido de la DANA y mis aportaciones técnicos al proyecto sobre la DANA son muy claras. 

La primera de ellas es que la DANA ha hecho mucho daño a los valencianos, y es una herida aun latente, se buscan responsables, como es obvio, pero lo que realmente deberíamos preguntarnos como valencianos es: "*¿Por qué no se han realizado obras hidráulicas tenido en cuenta que el territorio valenciano es proclive a estas riadas?*" Porque tenemos experiencias como la riada del 57, o la Pantanà' de Tous del 82, o los testimonios recogidos por el valenciano Antonio José Cavanilles y Palop de 1766, y como las innumerables riadas que el territorio valenciano ha sufrido y que valencianos dejaron testimonio de estos sucesos. Es decir, el territorio valenciano es propensa a recibir este tipo de fenómenos que ocurren cada ciertos años. ¿Por qué no se han hecho obras en la rambla del Poyo sabiendo la virulencia de ésta?

Y respecto a mi experiencia en la DANA. Estos acontecimientos sacan lo peor y lo mejor del ser humano, las dos caras de la moneda. Como a su vez, mi enriquecedora experiencia durante la salida de campo en el que pude hablar con vecinos de La Torre, Sedaví, Alfafar, Horno de Alcedo, Castellar-l'Oliveral, Massanassa, Mislata y Torrent. Me contaron sus experiencias, muchas de ellas eran muy duras, complicadas, algunas tristes, otras alegres por su final feliz... y ver los cementerios de coches que habían en los descampados de La Torre, Sedaví, Massanassa y Catarroja, el desastre en la Rambla del Poyo a la altura de Paiporta y Picanya, oler a barro en las calles, ambiente gris, calles sucias y con polvo. Lo verdaderamente enriquecedor fue la interacción con estos vecinos quienes amablemente me ayudaron y me pasaron fotos, videos y experiencias, e incluso, algunos tuvieron la gran amabilidad de ofrecerme algo de beber o pasar a dentro de sus casas, esa hospitalidad de gente que han perdido tanto y pese a ello han sido hospitalarios conmigo, eso, me parte el alma y la mismo tiempo, siento admiración por la bondad de estos vecinos. 

# Rol de la geomática y la topografía
Y por último, respecto a mi formación académica en esta ingeniería, como lo es la geomática y la topografía me ha dejado muy claro lo siguiente. Y es que la ingeniería en geomática y topografía no es solamente replantear una obra cualquiera, sino que se está replenteando una carretera o ferrocarril (para comunicar poblaciones y naciones) como un edificio (ya sea un colegio, una residencia de ancianos, un lugar de ocio, un hospital o viviendas), la geomática y la topografía tiene un impacto muy importante en la vida de las personas, por lo que, se puede decir entonces que es una disciplina que está al servicio de la sociedad, es una disciplina que tiene un impacto real en la vida de las personas, y una de esos impactos, es el entendimiento de la DANA, ayuda a entender qué ha sucedido, y cómo se podría actuar en consecuencia, y en definitiva, el proyecto en el que tuve el privilegio de participar en este proyecto, ya que ha ayudado a que los ayuntamientos afectados puedan diseñar un plan de evacuación o replantear sus planes urbanísticos... y todo esto tiene un impacto directo en la vida de las personas. Y no hay mayor orgullo que saber que mi gremio puede aportar tantísimo a la sociedad, tal vez, los topógrafos no seamos personas muy reconocidas por nuestra labor y por nuestro trabajo, pero no hay mayor orgullo personal que podemos hacer grandes contribuciones y muy importantes ante catástrofes naturales como la sucedida en el 29 de octubre de 2024 en Valencia. Y con otras tecnologías como la teledetección y la fotogrametría pueden ser de ayuda para la elaboración de cartografiado que ayude a interpretar lo sucedido y ayudar a poner remedio ante catástrofes naturales, para dar esperanzas a todos los valencianos que tanto han sufrido y padecido las consecuencias materiales y humanas.

Para más información acerca del proyecto y de las noticias respecto al proyecto está a continuación.

Proyecto CGAT:
https://dana2024.upvusig.car.upv.es/

ETSIGCT:
(https://www.upv.es/entidades/etsigct/2025/01/28/el-grupo-cgat-del-dicgf-junto-con-la-etsigct-crea-un-mapa-de-la-inundacion-en-lhorta-sud-tras-el-episodio-del-29-de-octubre-de-2024/

UPV:
https://www.upv.es/noticias-upv/noticia-15013-mapa-de-inunda-es.html

COIGT:
https://www.coigt.com/noticia/3877

Periódicos:
[El País](https://elpais.com/espana/2025-02-06/paiporta-picanya-catarroja-hasta-que-altura-llego-el-agua-en-cada-calle-el-dia-de-la-dana.html), [La Razón](https://www.larazon.es/comunidad-valenciana/aqui-llego-dana-mapa-upv-permite-saber-donde-llego-agua-calle-calle_202501296799f16e0b2ad20001ac621b.html), [Las Provincias](https://www.lasprovincias.es/comunitat/mapa-dana-calle-calle-20250129002825-nt.html), [El Levante E.M.V](https://www.levante-emv.com/comunitat-valenciana/2025/01/29/mapa-permite-conocer-altura-alcanzo-upv-agua-dana-valencia-calles-lhorta-sud-113805938.html), [Valencia Secreta](https://valenciasecreta.com/mapa-dana/), [Elperiodic.com](https://www.elperiodic.com/pvalencia/descubre-hasta-donde-llego-agua-calle-mapa-interactivo-muestra-como-inundo-lhorta-calle-calle-tras-dana_999086), [elDiario.es](https://www.eldiario.es/comunitat-valenciana/val/comarques/upv-mapeja-inundacio-dana-l-horta-sud-catastrofe-carrer-carrer_1_12004730.html), [europa press](https://www.europapress.es/comunitat-valenciana/noticia-elaboran-mapa-inundacion-calle-calle-municipios-lhorta-sud-afectados-dana-20250129103155.html), [Economía Digital](https://www.economiadigital.es/valencia/actualidad/upv-mapa-inundacion-calle-zona-cero-dana.html).

Cadenas televisivas:
[À Punt](https://www.apuntmedia.es/noticies/societat/l-alcaria-inundacio-dana-l-horta-sud-carrer-carrer_1_1761370.html), [RTVE](https://www.rtve.es/noticias/20250129/mapa-inundacion-calle-lhorta-sud-zona-cero-dana/16426688.shtml), [La Cuatro](https://www.cuatro.com/noticias/sociedad/20250130/mapa-dana-valencia-altura-agua-proyecto_18_014634652.html), [Telecinco](https://www.telecinco.es/noticias/valencia/20250130/universidad-politecnica-elabora-mapa-inundaciones-horta-sud-dana_18_014626718.html), [La 7TeleValencia](https://7televalencia.com/upv-mapa-inundaciones-causadas-dana/), 

Radios:
[Onda Cero](https://www.ondacero.es/emisoras/comunidad-valenciana/valencia/noticias/investigadores-upv-elaboran-mapa-calle-calle-inundaciones-lhorta-sud_20250129679a065ae95c0600017f0047.html), [La COPE](https://www.cope.es/emisoras/comunidad-valenciana/valencia-provincia/valencia/noticias/asi-mapa-inundacion-calle-calle-elaborado-equipo-upv-20250201_3087374.html), [Cadena SER](https://cadenaser.com/comunitat-valenciana/2025/01/29/los-puntos-donde-la-riada-llego-a-los-tres-metros-investigadores-elaboran-un-mapa-calle-a-calle-de-la-inundacion-de-la-dana-radio-valencia/)
