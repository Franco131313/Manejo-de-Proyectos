Catálogo de <u>proyectos</u> 

Geoinformática S2 2026 

# **Catálogo de proyectos Geoinformática, semestre 2 de 2026** 

Ingeniería Civil en Informática, USACH | Prof. Francisco Parra O. 

## **1. Cómo usar este catálogo** 

Este catálogo trae doce proyectos para que cada grupo elija uno, o para que lo use como punto de partida de un proyecto propio. Seis son de la **ruta científica** y seis de la **ruta comercial** . Las dos rutas valen lo mismo y exigen lo mismo: cambian los criterios de evaluación, no el nivel. Todos los proyectos combinan dos cosas: 

un **análisis espacial real** sobre datos chilenos abiertos, que es el centro del proyecto; 

- un **componente agéntico** : un agente de IA (un modelo de lenguaje que usa herramientas) que planifica, consulta datos, ejecuta análisis o revisa resultados. Los agentes se trabajan en la segunda mitad del semestre. 

Los temas salen de trabajos publicados entre 2023 y 2026: agentes para SIG, bancos de prueba que miden dónde fallan esos agentes y modelos fundacionales de observación de la Tierra que hoy se pueden usar sin una GPU grande. Las referencias están al final, y cada ficha dice qué trabajo hace posible el proyecto. 

### **Calendario** 

|**Fecha**|**Hito**|
|---|---|
|jueves 8 de octubre|Se presenta el catálogo en la clase 05|
|**martes 13 de octubre, 23:59**|**Inscripción del proyecto** (sección 7)|
|jueves 22 de octubre|Checkpoint de avance: 10 minutos por grupo, sin nota|
|jueves 12 de noviembre|PEP 1: análisis espacial funcionando y diseño del agente|
|jueves 7 de enero|PEP 2, Demo Day: agente integrado y evaluado|



**Un proyecto del catálogo por grupo.** Si dos grupos inscriben el mismo, queda con él el que lo inscribió primero, según la hora del commit; el otro elige otro o lo adapta hasta que sea un proyecto distinto. 

## **2. La regla del agente** 

El agente tiene que hacer algo que sin él no se podría hacer igual. **Si se saca el agente y el producto sigue funcionando igual, el proyecto no califica** . Además, todos los proyectos cumplen tres reglas, que vienen de lo que muestran los bancos de prueba publicados: 

1. **Ninguna cifra sin herramienta.** El agente no puede afirmar un número que no haya salido de una herramienta (una consulta, un cálculo, una lectura de archivo). Cada respuesta trae su traza: qué herramienta llamó, con qué parámetros y qué devolvió. 

2. **Un set de control.** Cada grupo arma entre 20 y 40 preguntas con respuesta conocida, calculada sin el agente. Algunas deben ser **imposibles de responder** con los datos disponibles: un buen agente dice que no puede, en vez de inventar. 

3. **Herramientas deterministas.** Los cálculos espaciales los hace código del grupo (GeoPandas, Rasterio, PostGIS, SurtGIS), no el modelo. El agente decide qué calcular; las herramientas calculan. 

1 

Catálogo de <u>proyectos</u> 

Geoinformática S2 2026 

### Por qué estas reglas 

Los bancos de prueba de 2025 coinciden: los agentes para SIG fallan sobre todo en relaciones espaciales y en selección de sitios, y algunos modelos prefieren dar cualquier respuesta antes que reconocer que una tarea es imposible (GeoBenchX, GeoAnalystBench). Con herramientas bien documentadas y un revisor que ejecuta, los resultados mejoran mucho (ShapefileGPT, Kazazi et al. 2025). Las reglas convierten «el agente no alucina» en algo que se puede medir y evaluar. 

## **3. Resumen** 

||**Proyecto**|**Dato central**|**El agente. . .**|
|---|---|---|---|
|**Ru**|**ta científica**|||
|C1|Glaciaretes que desaparecen|Ráster (embeddings,<br>Sentinel-2)|recorre el inventario|
|C2|Incendio de 2024 e interfaz<br>urbano-forestal|Ráster + manzanas|arma variables y modelo|
|C3|Campamentos: crecimiento y acceso|Vector + ráster|redacta fichas con evidencia|
|C4|Benchmark chileno de agentes SIG|Vector|es el objeto de estudio|
|C5|Hipersequía y vegetación por cuenca|Ráster + cuencas|repite el análisis por cuenca|
|C6|Alucinación geoespacial sobre Chile|Vector|se compara con y sin herramientas|
|**Ru**|**ta comercial**|||
|M1|Asistente text-to-PostGIS municipal|PostGIS|traduce preguntas a SQL espacial|
|M2|Copiloto de accesibilidad a<br>CESFAM|Red + puntos + manzanas|simula escenarios|
|M3|«Encuéntrame lugares como este»|Embeddings|busca sitios similares|
|M4|Alertas de cambio para un cliente|Sentinel-2|prioriza y redacta alertas|
|M5|Servidor MCP de datos abiertos<br>chilenos|Servicios del Estado|usa las herramientas que construyen|
|M6|Agente cartógrafo|Cualquiera|diseña y revisa mapas|



## **4. Ruta científica** 

|**C1. Glaciaretes **|**que desaparecen en los Andes centrales (2017–2024)**|
|---|---|
|**Pregunta o**<br>**propuesta**|¿Detectan los embeddings satelitales la desaparición de glaciaretes antes que el<br>índice de nieve (NDSI)?|
|**Por qué ahora**|Google publicó embeddings anuales de 10 m para todo el planeta (AlphaEarth,<br>2025), y un estudio de 2025 identificó qué glaciaretes del Desierto y los Andes Cen-<br>trales desaparecieron entre 2018 y 2023 (Ugalde et al.). Hay contra qué comparar.|
|**Qué hace el**<br>**agente**|Recorre el inventario polígono por polígono, calcula el cambio entre años en los<br>embeddings y en el NDSI, y redacta una ficha por glaciar con la evidencia.|
|**Cómo se verifica**|Comparar con los glaciaretes que el estudio de 2025 da por desaparecidos. Cada<br>ficha cita las herramientas que produjeron sus cifras.|
|**Datos**|Inventario Público de Glaciares (DGA); embeddings AlphaEarth en Google Earth<br>Engine (requiere cuenta); Sentinel-2 en Planetary Computer; Copernicus DEM.|
|**Lo que usa del**<br>**curso**|Ráster, interacciones ráster-vector, estadística zonal, Earth Engine.|
|**PEP 1 (12 nov)**|Una cuenca (por ejemplo, Maipo alto): NDSI y cambio en embeddings por glaciar,<br>sin agente.|
|**PEP 2 (7 ene)**|Agente que procesa el inventario completo de la cuenca y genera las fichas; com-<br>paración contra el estudio publicado.|
|**Riesgo principal**|Glaciaretes más chicos que unos pocos píxeles de 10 m.|



2 

Catálogo de <u>proyectos</u> 

Geoinformática S2 2026 

|**C2. Incendio de **|**2024 e interfaz urbano-forestal en la Región de Valparaíso**|
|---|---|
|**Pregunta o**<br>**propuesta**|¿Se repiten, para el incendio de febrero de 2024, los factores que predicen daño<br>en viviendas según Aguirre et al. (2024): distancia a la vegetación y densidad de<br>vecinos?|
|**Por qué ahora**|El Censo 2024 publicó datos por manzana, y la severidad de un incendio se calcula<br>con Sentinel-2 (dNBR). El estudio de 2024 encontró que la disposición espacial<br>pesa más que la estructura de la vivienda.|
|**Qué hace el**<br>**agente**|Construye las variables por manzana, corre el modelo con validación cruzada es-<br>pacial (clase 02) y documenta cada paso con su traza.|
|**Cómo se verifica**|Recalcular a mano una muestra de las variables; validación cruzada por bloques,<br>no aleatoria.|
|**Datos**|Sentinel-2 (antes y después del incendio); Censo 2024 por manzana (INE); detec-<br>ciones de fuego FIRMS (NASA); vegetación y red vial de OpenStreetMap.|
|**Lo que usa del**<br>**curso**|Operaciones vectoriales, ráster, interacciones ráster-vector, análisis espacial esta-<br>dístico, modelos predictivos.|
|**PEP 1 (12 nov)**|dNBR y variables por manzana en Viña del Mar, Quilpué y Villa Alemana; regre-<br>sión logística.|
|**PEP 2 (7 ene)**|Agente que reproduce el análisis con otros parámetros y redacta el informe con<br>trazas.|
|**Riesgo principal**|Confundir manzana quemada con manzana dañada.|



|**C3. Campamen**|**tos: cómo crecen y a qué servicios acceden (2019–2026)**|
|---|---|
|**Pregunta o**<br>**propuesta**|¿Cómo cambiaron la superficie y el acceso a CESFAM y colegios de los campa-<br>mentos catastrados entre 2019 y 2026?|
|**Por qué ahora**|El MINVU publica el Catastro de Campamentos con polígonos de 2019, 2022, 2024<br>y 2026, y hay embeddings anuales gratuitos que detectan cambio dentro de esos<br>polígonos.|
|**Qué hace el**<br>**agente**|Para cada campamento del catastro, consulta los cambios de superficie, calcula<br>distancias a servicios y redacta una ficha con evidencia. Un integrante del grupo<br>revisa cada ficha.|
|**Cómo se verifica**|Recalcular a mano cinco fichas; contrastar el cambio detectado con las imágenes<br>Sentinel-2.|
|**Datos**|Catastro de Campamentos (MINVU); establecimientos de salud (DEIS) y de edu-<br>cación (Mineduc); embeddings AlphaEarth.|
|**Lo que usa del**<br>**curso**|Operaciones vectoriales, interacciones ráster-vector, redes y accesibilidad.|
|**PEP 1 (12 nov)**|Una región: superficie por año y acceso a servicios, sin agente.|
|**PEP 2 (7 ene)**|Agente que genera y actualiza las fichas de todos los campamentos de la región.|
|**Riesgo principal**|Tema sensible: se trabaja con los polígonos públicos del catastro, con resultados<br>agregados y sin identificar personas. No se proponen ubicaciones de campamentos<br>nuevos.|



3 

Catálogo de <u>proyectos</u> 

Geoinformática S2 2026 

## **C4. Un banco de prueba chileno para agentes SIG** 

|**Pregunta o**<br>**propuesta**|¿Cuánto peor rinden los agentes SIG con datos chilenos: UTM 19S, nombres en<br>español, comunas con el mismo nombre en regiones distintas?<br>|
|---|---|
|**Por qué ahora**|GeoBenchX (2025) publicó más de 200 tareas con código abierto, pero ninguna<br>sobre Chile. Ya existen servidores MCP con decenas de herramientas SIG listas<br>(gis-mcp).|
|**Qué hace el**<br>**agente**|Es el objeto de estudio. Se comparan al menos tres configuraciones: un modelo<br>comercial vía API, uno local (Ollama) y uno con servidor MCP.|
|**Cómo se verifica**|Cada tarea tiene una respuesta de referencia calculada con código. Si se usa un<br>modelo como juez, se valida contra la corrección de una persona.|
|**Datos**|Comunas (BCN), establecimientos (DEIS), Censo 2024, OpenStreetMap.|
|**Lo que usa del**<br>**curso**|Todo el curso, porque cada tarea del banco es una operación vista en clase.|
|**PEP 1 (12 nov)**|60 tareas con respuesta de referencia y una corrida con un modelo.|
|**PEP 2 (7 ene)**|Tres configuraciones comparadas, con análisis de errores por tipo de tarea.|
|**Riesgo principal**|Costo de las llamadas a la API: hay que presupuestar y registrar los tokens por<br>corrida.|



## **C5. Hipersequía y respuesta de la vegetación por cuenca** 

|**Pregunta o**|¿Responde la vegetación de forma no lineal en los años de hipersequía (2019 y|
|---|---|
|**propuesta**|2021), como sugieren Garreaud et al. (2025), y lo capturan los embeddings mejor<br>que el NDVI?|
|**Por qué ahora**|El estudio de 2025 describe una respuesta no lineal de la vegetación y el agua<br>subterránea en Chile central. Las cuencas de CAMELS-CL y los datos grillados<br>CR2MET permiten repetirlo por cuenca.|
|**Qué hace el**<br>**agente**|Corre el mismo análisis cuenca por cuenca y produce fichas comparables entre sí.|
|**Cómo se verifica**|Semillas fijas y reejecución independiente de tres cuencas por otra persona del<br>grupo.|
|**Datos**|CAMELS-CL (CR2); CR2MET (precipitación y temperatura); NDVI de Sentinel-<br>2 o Landsat; embeddings AlphaEarth.|
|**Lo que usa del**<br>**curso**|Ráster, estadística zonal, series de tiempo, análisis espacial estadístico.|
|**PEP 1 (12 nov)**|Diez cuencas entre Coquimbo y el Maule, con anomalías de NDVI.|
|**PEP 2 (7 ene)**|Agente que extiende el análisis a todas las cuencas y redacta la comparación.|
|**Riesgo principal**|Atribuir causalidad donde solo hay correlación.|



4 

Catálogo de <u>proyectos</u> 

Geoinformática S2 2026 

|**C6. Alucinación **|**geoespacial sobre Chile**|
|---|---|
|**Pregunta o**<br>**propuesta**|¿Cuánto reduce las respuestas inventadas darle herramientas al modelo (geoco-<br>dificador, PostGIS, OpenStreetMap) en preguntas sobre comunas, distancias y<br>coordenadas de Chile?|
|**Por qué ahora**|GPSBench (2026) mostró que los modelos fallan más en cálculo geométrico que<br>en conocimiento geográfico, y peor a escala de ciudad que de país. GeoHaluBench<br>(2025) midió la alucinación en veinte modelos.|
|**Qué hace el**<br>**agente**|Responde las mismas preguntas en dos condiciones: solo el modelo, y el modelo<br>con herramientas.|
|**Cómo se verifica**|La respuesta correcta de cada pregunta se calcula con GeoPandas.|
|**Datos**|Comunas (BCN), Censo 2024, OpenStreetMap, establecimientos (DEIS).|
|**Lo que usa del**<br>**curso**|Sistemas de referencia, operaciones vectoriales, geocodificación.|
|**PEP 1 (12 nov)**|300 preguntas en cinco categorías, con respuesta de referencia; condición sin he-<br>rramientas.|
|**PEP 2 (7 ene)**|Condición con herramientas y análisis de qué tipo de pregunta mejora y cuál no.|
|**Riesgo principal**|Que las preguntas resulten triviales: hay que diseñarlas para que discriminen.|



## **5. Ruta comercial** 

|**M1. Asistente t**|**ext-to-PostGIS para un municipio**|
|---|---|
|**Pregunta o**<br>**propuesta**|Que un funcionario municipal consulte datos territoriales en lenguaje natural sin<br>saber SQL.|
|**Por qué ahora**|GeoSQL-Bench (2025) evaluó 24 modelos en consultas PostGIS, y un agente revisor<br>que ejecuta la consulta antes de responder subió la precisión de 76,7 % a 87,7 %<br>(Kazazi et al. 2025).|
|**Qué hace el**<br>**agente**|Lee el esquema, planifica, escribe el SQL, lo ejecuta y lo revisa. Solo responde si<br>la consulta corrió y el resultado tiene sentido.|
|**Cómo se verifica**|50 preguntas con resultado esperado, incluidas trampas de SRID y unidades.|
|**Datos**|Censo 2024 por manzana; comunas; OpenStreetMap de una comuna.|
|**Lo que usa del**<br>**curso**|Bases de datos espaciales, sistemas de referencia, APIs, WebGIS.|
|**PEP 1 (12 nov)**|Base PostGIS cargada y 20 consultas resueltas a mano, documentadas.|
|**PEP 2 (7 ene)**|Asistente con interfaz web, evaluado con las 50 preguntas.|
|**Riesgo principal**|Conseguir datos reales de un municipio; se puede partir con datos públicos.|



5 

Catálogo de <u>proyectos</u> 

Geoinformática S2 2026 

## **M2. Copiloto de accesibilidad a CESFAM** 

|**Pregunta o**<br>**propuesta**|Responder escenarios como «si cierra este CESFAM, ¿cuántas personas quedan a<br>más de 20 minutos a pie?» para un Servicio de Salud o un municipio.|
|---|---|
|**Por qué ahora**|La demo de la clase 05 mide la cobertura por área; el Censo 2024 por manzana<br>permite medirla por población, que es lo que importa.|
|**Qué hace el**<br>**agente**|Planifica el escenario y llama herramientas deterministas: red peatonal, estableci-<br>mientos y población. Devuelve la cifra con su traza.|
|**Cómo se verifica**|Recalcular a mano cinco escenarios.|
|**Datos**|Establecimientos de salud (DEIS); Censo 2024 por manzana; red peatonal de<br>OpenStreetMap (OSMnx).|
|**Lo que usa del**<br>**curso**|Operaciones vectoriales, redes y conectividad, WebGIS, APIs.|
|**PEP 1 (12 nov)**|Accesibilidad por población en tres comunas, sin agente.|
|**PEP 2 (7 ene)**|Copiloto que simula escenarios, con interfaz y evaluación.|
|**Riesgo principal**|Red peatonal incompleta en OpenStreetMap: hay que medir y declarar su calidad.|



## **M3. «Encuéntrame lugares como este»** 

|**Pregunta o**<br>**propuesta**|A partir de un polígono de ejemplo (un huerto de paltos, una zona comercial), en-<br>contrar sitios parecidos para una empresa agrícola, una inmobiliaria o una cadena.|
|---|---|
|**Por qué ahora**|Los embeddings satelitales (AlphaEarth, TESSERA, Major TOM) resumen cada<br>píxel en un vector, y un índice vectorial (FAISS o pgvector) los busca en milise-<br>gundos.|
|**Qué hace el**<br>**agente**|Traduce la intención del cliente, filtra por restricciones vectoriales (zonificación,<br>distancia a rutas) y justifica cada resultado con capas.|
|**Cómo se verifica**|Una persona evalúa la precisión de los 20 primeros resultados.|
|**Datos**|Embeddings AlphaEarth (Earth Engine) o TESSERA (2024, cobertura global);<br>OpenStreetMap.|
|**Lo que usa del**<br>**curso**|Ráster, operaciones vectoriales, bases de datos espaciales, machine learning geoes-<br>pacial.|
|**PEP 1 (12 nov)**|Búsqueda por similitud en una región, sin agente.|
|**PEP 2 (7 ene)**|Producto con agente, interfaz y evaluación de precisión.|
|**Riesgo principal**|Condiciones de uso comercial de Earth Engine: hay que revisarlas antes de elegir<br>la fuente.|



## **M4. Alertas de cambio para un cliente** 

**Pregunta o** Un servicio mensual que avisa a una forestal, una minera o un municipio de los **propuesta** cambios en su territorio, con evidencia. **Por qué ahora** Change-Agent (2024), Forest-Chat (2026) y Earth-Agent (2025) muestran agentes que detectan y describen cambios en imágenes satelitales. **Qué hace el** Un proceso programado detecta cambios con Sentinel-2; el agente los prioriza, **agente** descarta los debidos a nubes y redacta la alerta con imágenes antes y después. **Cómo se verifica** Traza completa y revisión humana antes de cada envío. **Datos** Sentinel-2 en Planetary Computer; embeddings AlphaEarth; límites prediales o comunales. **Lo que usa del** Ráster, operaciones ráster, automatización y pipelines. **curso PEP 1 (12 nov)** Detección de cambio en un área de interés, sin agente. **PEP 2 (7 ene)** Servicio con alertas por correo, priorizadas por el agente. **Riesgo principal** Falsos positivos por estacionalidad. 

6 

Catálogo de <u>proyectos</u> 

Geoinformática S2 2026 

## **M5. Servidor MCP de datos abiertos chilenos** 

**Pregunta o** Que cualquier agente de IA pueda consultar datos territoriales del Estado (MIN- **propuesta** VU, INE, DGA, CR2) con herramientas bien documentadas. **Por qué ahora** El protocolo MCP se volvió el estándar para dar herramientas a los agentes, y LLM-Find (2024) mostró que los agentes eligen mejor la fuente de datos cuando tienen «manuales» de metadatos. **Qué hace el** El producto es la capa de herramientas. Se evalúa con un agente cliente que resuelve **agente** tareas usándolas. **Cómo se verifica** Tests de contrato por herramienta y 40 tareas de evaluación. **Datos** IDE Chile; catastros del MINVU; INE; DGA; CR2. **Lo que usa del** APIs, formatos, automatización y pipelines, sistemas de referencia. **curso PEP 1 (12 nov)** Cuatro fuentes y diez herramientas, con sus tests. **PEP 2 (7 ene)** Servidor publicado en GitHub y evaluado con un agente cliente. **Riesgo principal** Los servicios del Estado cambian o se caen: hay que manejar errores y caché. 

## **M6. Agente cartógrafo** 

|**Pregunta o**<br>**propuesta**|Mapas para los informes de una ONG o un municipio que cumplan la norma del<br>curso: título, leyenda, escala, norte, fuente y EPSG:32719.|
|---|---|
|**Por qué ahora**|CartoAgent (2025) separa el estilo de los datos para que el agente diseñe el mapa<br>sin alterar la geometría, y un crítico multimodal lo revisa.|
|**Qué hace el**<br>**agente**|Genera el estilo del mapa y un segundo agente lo revisa contra una lista de chequeo.|
|**Cómo se verifica**|Pruebas automáticas sobre el proyecto (CRS, elementos presentes) y evaluación<br>de personas.|
|**Datos**|Los del cliente real; si no hay, datos públicos de su comuna.|
|**Lo que usa del**<br>**curso**|Cartografía, creación de mapas con Python, sistemas de referencia.|
|**PEP 1 (12 nov)**|Tres tipos de mapa hechos a mano y la lista de chequeo como código.|
|**PEP 2 (7 ene)**|Agente que produce y corrige los tres tipos de mapa para el cliente.|
|**Riesgo principal**|Que la evaluación estética quede subjetiva: hay que definir criterios medibles.|



## **6. Proyecto propio** 

Un grupo puede proponer su propio proyecto si cumple estas cinco condiciones: 

1. **El espacio es central.** Si se quitan las coordenadas, el proyecto deja de tener sentido. Un sistema de inventario con un mapa decorativo no califica. 

2. **El agente no es decorativo** (sección 2). 

3. **Los datos existen y son accesibles** , y el grupo lo comprueba descargando una muestra antes de inscribirse. 

4. **Cabe en el semestre** : hay una versión mínima para la PEP 1. 

5. **Tiene un usuario o una pregunta concreta** : para quién es, o qué se quiere saber. 

## **7. Inscripción** 

Hasta el **martes 13 de octubre a las 23:59** , cada grupo agrega esta sección al `README.md` de su repositorio y hace commit. La hora del commit es la hora de inscripción. 

7 

Catálogo de <u>proyectos</u> 

Geoinformática S2 2026 

### Sección para el README 

```
##Proyecto
Códigodelcatálogo:C1...M6,o«propio»
Título:
```

```
Ruta:científica/comercial
Preguntaopropuestadevalor(dosfrases):
Datos(fuenteyenlacedecadauno;yadescargamosunamuestra:sí/no):
Quéharáelagente(tresfrases):
VersiónmínimaparalaPEP1:
Riesgoprincipalycómolovamosaenfrentar:
```

## **8. Advertencias** 

- **Costos.** Las llamadas a modelos comerciales cuestan dinero. Registren los tokens de cada corrida y guarden en caché las salidas de las herramientas. Un modelo local (Ollama) sirve como línea base, aunque rinde bastante menos: en GeoAnalystBench, un modelo local de 7 mil millones de parámetros logró 48,5 % de respuestas válidas contra 95 % de GPT-4o-mini. 

- **Seguridad.** Algunos servidores MCP ejecutan código arbitrario. Úsenlos en un contenedor, con credenciales de solo lectura en las bases de datos, y nunca manden datos personales a una API externa. 

- **Embeddings.** TESSERA cubre Chile solo en 2024; para series de tiempo usen AlphaEarth (2017–2024), que requiere una cuenta de Earth Engine. 

- **Procedencia.** Todo dato va declarado en `PROCEDENCIA_DATOS.md` , como en cualquier proyecto del curso. 

## **9. Referencias** 

### **Agentes para SIG** 

- Li, Z. y Ning, H. (2023). Autonomous GIS: the next-generation AI-powered GIS. arXiv:2305.06453. 

- Ning, H., Li, Z., Akinboyewa, T. y Lessani, M. N. (2024). An autonomous GIS agent framework for geospatial data retrieval (LLM-Find). arXiv:2407.21024. 

- Akinboyewa, T., Li, Z., Ning, H. y Lessani, M. N. (2024). GIS Copilot. arXiv:2411.03205. 

- Lin, Q. et al. (2024). ShapefileGPT. arXiv:2410.12376. 

- Li, Z., Ning, H., Gao, S., Janowicz, K., Li, W. et al. (2025). GIScience in the era of AI: a research agenda towards autonomous GIS. arXiv:2503.23633. 

- Krechetova, V. y Kochedykov, D. (2025). GeoBenchX: benchmarking LLMs in agent solving multistep geospatial tasks. arXiv:2503.18129. Código: `https://github.com/Solirinai/GeoBenchX` 

- Zhang, Q., Gao, S. et al. (2025). GeoAnalystBench. _Transactions in GIS_ . arXiv:2509.05881. 

- Hou, S. et al. (2025). GeoSQL-Eval: first evaluation of LLMs on PostGIS-based NL2GeoSQL queries. arXiv:2509.25264. 

- Khosravi Kazazi, A., Li, Z., Lessani, M. N. y Cervone, G. (2025). From questions to queries: an AI-powered multi-agent framework for spatial text-to-SQL. arXiv:2510.21045. 

- Wang, C., Kang, Y. et al. (2025). CartoAgent. arXiv:2505.09936. 

- gis-mcp: servidor MCP con herramientas SIG en Python. `https://github.com/mahdin75/gis-mcp` 

### **Modelos fundacionales y embeddings** 

- Brown, C. F. et al. (2025). AlphaEarth Foundations. arXiv:2507.22291. Embeddings: `https://developers.goo gle.com/earth-engine/datasets/catalog/GOOGLE_SATELLITE_EMBEDDING_V1_ANNUAL` 

- Feng, Z. et al. (2025). TESSERA. arXiv:2506.20380. `https://github.com/ucam-eo/tessera` 

8 

Catálogo de <u>proyectos</u> 

Geoinformática S2 2026 

- Czerkawski, M., Kluczek, M. y Bojanowski, J. S. (2024). Major TOM floating in the latent space. arXiv:2412.05600. Szwarcman, D. et al. (2024). Prithvi-EO-2.0. arXiv:2412.02732. 

### **Monitoreo y alucinación** 

- Liu, C. et al. (2024). Change-Agent. _IEEE TGRS_ . arXiv:2403.19646. 

- Brock, J., Zhang, C. y Anantrasirichai, N. (2026). Forest-Chat. arXiv:2601.14637. 

- Feng, P. et al. (2025). Earth-Agent. arXiv:2509.23141. 

- Wang, S., Feng, J., Liu, T., Pei, D. y Li, Y. (2025). Mitigating geospatial knowledge hallucination in LLMs. arXiv:2507.19586. 

- Truong, T. H., Lau, J. H. y Qi, J. (2026). GPSBench. arXiv:2602.16105. 

### **Chile** 

- Aguirre, P. et al. (2024). Modelling the vulnerability of urban settings to wildland–urban interface fires in Chile. _NHESS_ , 24, 1521–1537. doi:10.5194/nhess-24-1521-2024. 

- Garreaud, R. et al. (2025). Hyperdroughts in central Chile: drivers, impacts, and projections. _HESS_ , 29, 5347–5369. doi:10.5194/hess-29-5347-2025. 

- Ugalde, F. et al. (2025). Ice loss detection of glacierets in the Desert and Central Andes of Chile 2018–2023. _Frontiers in Earth Science_ , 13. doi:10.3389/feart.2025.1565290. 

### **Fuentes de datos** 

- Establecimientos de salud (DEIS): `https://datos.gob.cl` (buscar «Establecimientos de Salud») 

- Directorio de establecimientos educacionales (Mineduc): `https://datosabiertos.mineduc.cl` 

- Censo 2024 (INE): `https://censo2024.ine.gob.cl` y `https://www.ine.gob.cl/herramientas/portal-de-map as/geodatos-abiertos` 

- Catastro de Campamentos (MINVU): `https://www.minvu.gob.cl/catastro-de-campamentos/` 

- Inventario Público de Glaciares (DGA): `https://dga.mop.gob.cl/inventario-publico-de-glaciares/` 

- CAMELS-CL y CR2MET (CR2): `https://camels.cr2.cl` y `https://www.cr2.cl/datos-productos-grillados /` 

- Sentinel-2, Landsat y Copernicus DEM: `https://planetarycomputer.microsoft.com` 

- Detecciones de fuego FIRMS (NASA): `https://firms.modaps.eosdis.nasa.gov` 

- OpenStreetMap: `https://download.geofabrik.de/south-america/chile.html` 

- Infraestructura de Datos Geoespaciales: `https://www.ide.cl` 

- SurtGIS, motor ráster del curso: Parra, F. (2026). _Environmental Modelling & Software_ , 204, 107102. `https: //github.com/franciscoparrao/surtgis` 

9 

