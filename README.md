🚦 BA SafeRoute: Análisis Estadístico de Siniestralidad Vial y Ruteo Inteligente
Este proyecto desarrolla un sistema de optimización de rutas para la Ciudad Autónoma de Buenos Aires (CABA) que, a diferencia de los GPS convencionales, prioriza la seguridad del usuario basándose en datos históricos de siniestralidad vial.

📊 El Problema
Los algoritmos de ruteo estándar (como Google Maps o Waze) suelen optimizar únicamente por tiempo o distancia. Sin embargo, en ciudades de alta densidad como Buenos Aires, ciertas intersecciones presentan una recurrencia estadística de accidentes graves que entorpecen el tránsito y ponen en riesgo la seguridad.

🛠️ Tecnologías Utilizadas
Python (Google Colab como entorno de desarrollo).

Pandas: Manipulación y limpieza de datasets de seguridad vial.

OSMnx: Descarga y modelado de redes viales a partir de OpenStreetMap.

Folium: Visualización interactiva de mapas y rutas.

Geopy: Geocodificación de direcciones de texto a coordenadas geográficas.

NetworkX: Algoritmos de grafos (Dijkstra ponderado).

🗂️ Origen de los Datos
Se utilizó el dataset oficial de Homicidios en Siniestros Viales de la Ciudad de Buenos Aires (BA Data). El archivo incluye:

Geolocalización precisa de los hechos.

Cantidad de víctimas por siniestro.

Tipo de vehículos involucrados.

🧠 Lógica del Algoritmo
El sistema no solo procesa puntos en un mapa, sino que realiza un re-pesaje de la red vial:

Se descarga el grafo vial de CABA.

Se asigna a cada segmento de calle un costo inicial basado en su longitud real.

Análisis de Riesgo: Se cruzan los siniestros del dataset con los nodos del mapa. Cada vez que una calle está cerca de un siniestro histórico, se le aplica una penalización estadística (aumentando su "costo" en el algoritmo de Dijkstra).

Optimización: El usuario ingresa origen y destino, y el modelo calcula:

Ruta Roja (Corta): Minimiza la distancia física.

Ruta Verde (Segura): Minimiza la probabilidad estadística de encontrar un punto crítico de accidentes.

🚀 Cómo usarlo
Clona el repositorio.

Sube el archivo hechos.csv a tu entorno de Google Colab o Google Drive.

Ejecuta las celdas para procesar la red vial y generar el modelo de riesgo.

Ingresa dos direcciones (Ej: "Av. Corrientes 1200" y "Av. Santa Fe 2500") para obtener el mapa comparativo.

Próximos Pasos (Roadmap)
[ ] Integrar datos de Siniestros con Lesiones para aumentar la densidad del mapa de calor.

[ ] Implementar pesos dinámicos según el tipo de vehículo (ej: rutas más seguras para motos).

[ ] Incorporar datos de cortes de tránsito en tiempo real.
