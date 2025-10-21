# Análisis de Desinformación en Redes Sociales en las Elecciones Presidenciales

Autor: Francisco Castillo Hernández

Fecha: 19/10/2025

## Descripción del Problema

Este proyecto realiza un análisis de datos a gran escala sobre las secciones de comentarios de YouTube de los principales medios de noticias chilenos, con el objetivo de estudiar la propagación de desinformación durante el período de elecciones presidenciales.

El análisis busca identificar los patrones ocultos detrás de la diseminación de narrativas falsas mediante el uso combinado de análisis de redes, análisis temporal y procesamiento de texto. El proyecto se divide en dos partes principales:

- **Parte 1: Propagación y Actores Clave:** Se enfoca en la reconstrucción de cascadas de difusión, la dinámica temporal de la conversación y la identificación de actores influyentes (Amplificadores, Generadores de Debate) y cuentas con patrones de actividad anómala (bots).

- **Parte 2: Comunidades y Narrativas:** Se enfoca en la asociación, identificando "burbujas ideológicas" de usuarios que hablan de temas similares, analizando sus narrativas dominantes a través de nubes de palabras y midiendo el impacto de las cuentas anómalas en cada comunidad.

## Dependencias Técnicas

Este proyecto se desarrolla en Python 3 dentro de un Jupyter Notebook (main.py). Todas las librerías necesarias se pueden instalar ejecutando:

```
pip install pandas numpy google-api-python-client tqdm networkx matplotlib python-louvain wordcloud nltk

```

### Librerías Principales

- `pandas` y `numpy`

- `google-api-python-client` (para la API de YouTube)

- `tqdm` (para barras de progreso)

- `networkx` (para análisis de grafos)

- `matplotlib` (para visualizaciones)

- `python-louvain` (para detección de comunidades)

- `wordcloud` (para nubes de palabras)

- `nltk` (para procesamiento de lenguaje natural)

## Instrucciones de Ejecución

El análisis completo está contenido en el notebook main.py. Se recomienda ejecutarlo secuencialmente.

### Paso 1: Configuración de la API

Para facilitar la reproducibilidad, ya se ha incluido una clave de API funcional en la celda: `Parte 1` -> `Recolección de Datos` -> `Conexión a Youtube`.

Si esta clave excede su cuota diaria o se desea utilizar una propia, se puede obtener una nueva desde la [Google Cloud Console](https://console.cloud.google.com/apis/dashboard), asegurándose de habilitar la **YouTube Data API v3** para el proyecto.

### Paso 2: Instalación de Dependencias

```
pip install pandas numpy google-api-python-client tqdm networkx matplotlib python-louvain wordcloud nltk
```

### Paso 3: Ejecución del Notebook

Abra el notebook `P1_TEL351_Francisco-Castillo.ipynb` y ejecute todas las celdas en orden, desde la primera hasta la última (`Cell > Run All`).

**¡ADVERTENCIA!** La celda de _"Detección de Comunidades"_ es extremadamente intensiva y puede tardar más de 40 minutos en completarse, ya que debe proyectar y filtrar un grafo de 87.7 millones de aristas. Se recomienda paciencia.

- **Nota:** Los scripts de _"Recolección de Datos"_ son reanudables. Si la cuota de la API se agota, simplemente espere a que se reinicie y vuelva a ejecutar la celda para continuar donde se quedó. Los datos se guardan progresivamente en `canales.csv`, `videos_para_analizar.csv` y `comentarios_finales.csv`.

## Reproducibilidad

El notebook ha sido configurado con semillas (`random_state=42` y `seed=42`) en todas las celdas que utilizan procesos aleatorios (Detección de Comunidades, Nubes de Palabras, Muestreo de Nodos y Generación de Layouts de Grafos). Esto asegura que los resultados y visualizaciones generados sean 100% reproducibles en cada ejecución.

