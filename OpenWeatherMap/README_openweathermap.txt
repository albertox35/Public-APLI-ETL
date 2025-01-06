=======================================
        README - Análisis Meteorológico
=======================================

Este proyecto tiene como objetivo cargar datos meteorológicos desde una API, procesar y almacenar la información en un DataFrame de pandas con un MultiIndex. Los datos incluyen variables como temperatura, humedad, presión atmosférica, nubosidad, velocidad del viento, entre otros. Además, el proyecto genera visualizaciones gráficas que muestran la evolución de estas variables a lo largo del tiempo, con la fecha de predicción en el eje X. Los gráficos generados se guardan localmente en un directorio específico y también se visualizan en pantalla.


======================================= 
	Estructura del Proyecto
======================================= 

La estructura del proyecto es la siguiente:
/OpenWeatherMap 		# Carpeta que contiene los scripts de Python
├── OpenWeatherMap.db		# Base de datos
├── OpenWeatherMap.ipynb	# Script que ejecuta el análisis y genera las visualizaciones
├── /Visualizaciones/		# Carpeta donde se guardarán las imágenes generadas
└── README_OpenWeatherMap.txt	# Este archivo

=======================================
        Uso de la API Key
=======================================

Este proyecto hace uso de la API de OpenWeatherMap para obtener las predicciones meteorológicas. Para interactuar con la API, necesitas una **API Key** (clave de acceso). Puedes obtenerla de la siguiente manera:

1. Ve a [OpenWeatherMap](https://openweathermap.org/).
2. Regístrate o inicia sesión en tu cuenta.
3. Genera una nueva clave API desde tu panel de usuario.

Una vez que tengas tu API Key, deberás integrarla en el código del proyecto para realizar las consultas a la API de OpenWeatherMap. Asegúrate de no compartir tu clave API públicamente, ya que otras personas podrían usarla sin tu autorización, lo que podría generar costos adicionales o agotar el límite de uso.

Por motivos de seguridad, **nunca incluyas tu clave API directamente en el código fuente** que compartas públicamente. En su lugar, te recomendamos almacenar la clave en un archivo de configuración o como variable de entorno, y cargarla desde allí en tu código. Ejemplo de cómo almacenar la API Key en un archivo `.env`:

API_KEY=tu_clave_api_aqui

Y luego, en tu código, usa un paquete como `python-dotenv` para cargar la clave:

from dotenv import load_dotenv
import os

load_dotenv()  # Carga el archivo .env
api_key = os.getenv("API_KEY")

======================================= 
Precauciones
======================================= 

Límites de la API: La API de OpenWeatherMap tiene un límite de consultas gratuitas por minuto o por día, dependiendo de tu plan. Asegúrate de no exceder estos límites para evitar bloqueos o costos adicionales.

Manejo de errores: En caso de que la API esté fuera de servicio o no puedas obtener datos, el código debe manejar estos errores de forma adecuada. Esto evitará que el programa falle inesperadamente y permitirá que puedas diagnosticar el problema fácilmente.

Seguridad: Como mencionamos anteriormente, nunca compartas tu API Key públicamente y asegúrate de almacenarla de forma segura.

Uso responsable de datos: Ten en cuenta que las predicciones meteorológicas pueden tener un margen de error y no siempre serán 100% precisas. Asegúrate de utilizar estos datos con el conocimiento de sus limitaciones.


=======================================
        Requisitos previos
=======================================

Antes de ejecutar este código, asegúrate de tener instaladas las siguientes bibliotecas de Python:

1. **pandas**: Para la manipulación y análisis de los datos.
2. **requests**: Para realizar consultas HTTP a la API de OpenWeatherMap.
3. **matplotlib**: Para la creación de gráficos y visualizaciones.
4. **datetime**: Para la manipulación y formateo de fechas.
5. **os**: Para gestionar directorios y archivos locales.
6. **matplotlib.dates**: Para configurar el formato de fecha en los gráficos.

Puedes instalar estas dependencias ejecutando el siguiente comando en tu terminal:
pip install pandas requests matplotlib

=======================================
        Archivos del Proyecto
=======================================

- **city.list.json**: Archivo que contiene los IDs de las ciudades que se consultarán en la API de OpenWeatherMap.
- **OpenWeatherMap.json**: Archivo generado por la consulta a la API, que contiene las predicciones del clima para las ciudades seleccionadas.
- **Visualizaciones**: Directorio donde se guardarán las imágenes generadas por las gráficas.
- **ReadMe.txt**: Este archivo, que contiene la información básica sobre el proyecto y su ejecución.

=======================================
        Ejecución del Proyecto
=======================================

Para ejecutar el proyecto, sigue estos pasos:

1. Asegúrate de tener un archivo `city.list.json` con los IDs de las ciudades que deseas consultar.
2. Coloca tu clave de API de OpenWeatherMap en el script donde se realiza la consulta.
3. Ejecuta el código en tu entorno de Python. Los datos se cargarán desde el archivo JSON y se realizará una consulta a la API para obtener las predicciones meteorológicas.
4. Se generarán gráficos para las siguientes variables: temperatura, humedad, presión, nubosidad, viento y visibilidad. Las imágenes se guardarán en el directorio `Visualizaciones`.
5. Los gráficos también se mostrarán en pantalla para su análisis visual.

=======================================
        Estructura de los Datos
=======================================

Los datos obtenidos de la API y cargados en el DataFrame tienen un formato de **MultiIndex** con las siguientes columnas:

- **Fecha**:
  - `Fecha_de_prediccion`: Fecha de la predicción en formato `datetime64`.

- **Temperatura**:
  - `Temperatura_celcius`: Temperatura en grados Celsius.
  - `Temperatura_Real_celcius`: Temperatura real (sensación térmica).
  - `Temperatura_Minima_celcius`: Temperatura mínima predicha.
  - `Temperatura_Maxima_celcius`: Temperatura máxima predicha.

- **Humedad**:
  - `Humedad_percent`: Humedad relativa en porcentaje.

- **Presión**:
  - `Presion_hPa`: Presión atmosférica en hectopascales (hPa).

- **Nubosidad**:
  - `Nubosidad_percent`: Porcentaje de nubosidad.

- **Viento**:
  - `Velocidad_del_viento_m_s`: Velocidad del viento en metros por segundo (m/s).
  - `Rafagas_de_viento_m_s`: Rafagas de viento en metros por segundo (m/s).

- **Visibilidad**:
  - `Visibilidad_m`: Visibilidad en metros.

=======================================
        Visualización y Gráficos
=======================================

Los gráficos generados incluyen:

1. **Temperatura (en °C)**: Gráfica que muestra la evolución de la temperatura a lo largo del tiempo.
2. **Temperatura Real (en °C)**: Gráfica que muestra la evolución de la temperatura real o sensación térmica.
3. **Temperatura Mínima (en °C)**: Gráfica con la evolución de la temperatura mínima predicha.
4. **Temperatura Máxima (en °C)**: Gráfica con la evolución de la temperatura máxima predicha.
5. **Humedad**: Gráfica que muestra la evolución de la humedad relativa.
6. **Presión**: Gráfica que muestra la evolución de la presión atmosférica.
7. **Nubosidad**: Gráfica que muestra la evolución del porcentaje de nubosidad.
8. **Velocidad del Viento**: Gráfica que muestra la velocidad del viento a lo largo del tiempo.
9. **Ráfagas del Viento**: Gráfica que muestra la evolución de las ráfagas de viento.
10. **Visibilidad**: Gráfica que muestra la visibilidad en metros.

Todas las gráficas se guardarán en el directorio `Visualizaciones` y se visualizarán en pantalla.

=======================================
        Notas
=======================================

- Asegúrate de tener correctamente configurada la API de OpenWeatherMap con una clave válida.
- Los gráficos son generados con un intervalo de 3 horas (configurado con `mdates.HourLocator(interval=3)`), pero este valor puede ajustarse según sea necesario.
- El formato de fecha en el eje X de los gráficos se ha configurado para mostrar solo el día y el mes (formato `%d-%m`).


=======================================
        Contacto
=======================================
Si tienes alguna duda o necesitas más detalles sobre el uso de la API o sobre cómo ejecutar el proyecto, no dudes en contactarme.

Correo electrónico: albertox35@yahoo.com.mx
