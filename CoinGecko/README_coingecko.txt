=========================
        README - Análisis de Criptomonedas
=======================================

Este proyecto permite obtener, procesar y analizar datos sobre el mercado global de criptomonedas utilizando la API de CoinGecko. A través de este proyecto, podrás obtener métricas como la capitalización de mercado total, el volumen de criptomonedas y el porcentaje de participación de cada criptomoneda, además de visualizar estos datos en gráficos.

=======================================
    Requisitos previos
=======================================

Antes de ejecutar este código, asegúrate de tener instaladas las siguientes bibliotecas de Python:

1. **requests**: Para hacer solicitudes HTTP a la API de CoinGecko.
2. **pandas**: Para manipular y analizar los datos.
3. **matplotlib**: Para crear gráficos y visualizaciones.
4. **json**: Para manejar archivos JSON con los datos obtenidos.
5. **os**: Para trabajar con directorios y archivos locales.
6. **sqlite3** (opcional): Si decides almacenar los datos en una base de datos SQLite.

Instala las dependencias necesarias con:
pip install requests pandas matplotlib

# =========================
#     Estructura del Proyecto
# =========================

La estructura del proyecto es la siguiente:

/Proyecto_Cripto_Análisis 	# Carpeta que contiene los scripts de Python
├── CoinGecko.json   		# Archivo JSON con los datos obtenidos de la API de CoinGecko
├── CoinGecko_dataframe.csv   	# Archivo CSV con los datos procesados y listos para análisis
├── CoinGecko.ipynb		# Script principal que realiza la extracción y análisis de los datos
├── /Graphs/			# Carpeta donde se guardarán las imágenes generadas de las visualizaciones
│   ├── distribucion_market_cap.png
│   ├── distribucion_volume.png
│   └── ...
└── README_coingecko.txt                  # Este archivo
|

=======================================
    Descripción del Proyecto
=======================================

Este proyecto se enfoca en la recolección y análisis de datos sobre el mercado de criptomonedas, haciendo uso de la API pública de CoinGecko. El objetivo es obtener datos actualizados sobre el mercado global de criptomonedas y visualizar estas métricas de manera clara.

Las métricas incluidas son:

- **Capitalización Total del Mercado** (`total_market_cap`).
- **Volumen Total del Mercado** (`total_volume`).
- **Porcentaje de Capitalización del Mercado por Moneda** (`market_cap_percentage`).
- **Datos Globales**: Cambio en la capitalización de mercado en las últimas 24 horas, número de criptomonedas activas, ICOs próximos y en curso, entre otros.

Este análisis incluye la generación de gráficos sobre la distribución de estas métricas y la exportación de los datos a archivos CSV y JSON.

=======================================
    Uso de la API de CoinGecko
=======================================
¿Qué es la API de CoinGecko?

La API de CoinGecko es una API pública que proporciona acceso gratuito a información sobre criptomonedas. No requiere una clave de API o autenticación para acceder a la mayoría de los endpoints.


Endpoint utilizado

En este proyecto, el endpoint utilizado es: https://api.coingecko.com/api/v3/global

Este endpoint devuelve información sobre las criptomonedas a nivel global, incluyendo:

- **Total Market Cap**: La capitalización total del mercado de criptomonedas.
- **Total Volume**: El volumen total de transacciones del mercado.
- **Market Cap Percentage**: El porcentaje de la capitalización de mercado por cada criptomoneda.
- **Market Cap Change Percentage (24h USD)**: El cambio en el porcentaje de capitalización en las últimas 24 horas.
- **Updated At**: Fecha y hora de la última actualización de los datos.
- **Active Cryptocurrencies**: Número de criptomonedas activas.
- **Upcoming ICOs**: ICOs próximos.
- **Ongoing ICOs**: ICOs en curso.
- **Ended ICOs**: ICOs finalizados.

¿Es necesario usar un token o clave de API?

No, la API de CoinGecko es de acceso público y no requiere una clave de API. Sin embargo, si se requiere realizar un uso intensivo de la API, se recomienda verificar las limitaciones de solicitudes para evitar bloqueos o restricciones. 

Aunque no es necesario un token o clave, **es importante seguir las buenas prácticas al interactuar con APIs públicas**.

=======================================
    Buenas Prácticas y Consideraciones al Usar APIs Públicas
=======================================

Aunque la API de CoinGecko no requiere autenticación, es importante seguir algunas buenas prácticas:

1. **Limitaciones de Solicitudes**:
   - Aunque la API es gratuita, las solicitudes están limitadas a 50 por minuto. Si necesitas hacer más solicitudes, es recomendable implementar un sistema de caché para almacenar los datos localmente y evitar realizar solicitudes repetidas innecesarias.
   
2. **Autenticación y Tokens**:
   - Si decides usar un token de autenticación para superar límites o acceder a características premium, **nunca debes compartir tu clave API públicamente**. La clave podría ser utilizada por otras personas, lo que podría agotar tus límites de solicitud o incurrir en costos adicionales.
   
3. **Uso Responsable**:
   - Evita hacer solicitudes repetitivas sin necesidad. Si los datos no han cambiado, considera almacenar localmente los resultados para su posterior análisis.
   
4. **Manejo de Errores**:
   - Verifica siempre el código de estado HTTP de la respuesta. Si la solicitud no es exitosa (código 200), es importante manejar esos errores de manera adecuada y no continuar con el procesamiento de los datos.

5. **Exceso de Solicitudes**:
   - Si realizas solicitudes masivas, considera implementar una estrategia de retroceso exponencial para reducir la frecuencia de las solicitudes en caso de errores o alcanzar los límites.

=======================================
    Guardado y Visualización de Datos
=======================================

Este proyecto guarda los datos obtenidos de la API en archivos **JSON** y **CSV**. Además, se generan gráficos visualizando las distribuciones de las métricas clave como:

- **Distribución de la Capitalización del Mercado Total**.
- **Distribución del Volumen Total**.
=======================================
	Archivos generados:
=======================================
- **CoinGecko.json**: Los datos completos obtenidos de la API.
- **CoinGecko_dataframe.csv**: Los datos procesados en formato CSV.
- **distribucion_total_market_cap.png**: Gráfico sobre la distribución de la capitalización del mercado total.
- **distribucion_total_volume.png**: Gráfico sobre la distribución del volumen total.
- **sorted_by_volume.csv**: CSV con los datos ordenados por volumen.
- **sorted_by_market_cap.csv**: CSV con los datos ordenados por capitalización de mercado.

Los gráficos generados se guardan en una carpeta llamada `Graphs/` dentro del directorio de trabajo.

=======================================
    Ejecución del Proyecto
=======================================

1. Asegúrate de tener las dependencias necesarias instaladas.
2. Ejecuta el script principal. Este obtendrá los datos desde la API de CoinGecko.
3. Los resultados se procesarán y se generarán gráficos y archivos CSV.
4. Los archivos de salida serán almacenados en el directorio de trabajo actual.

=======================================
    Contribuciones
=======================================

Si deseas contribuir a este proyecto, sigue estos pasos:

1. Haz un fork del repositorio.
2. Crea una nueva rama para tus cambios (`git checkout -b feature/nueva-funcionalidad`).
3. Realiza los cambios y asegúrate de que todo funcione correctamente.
4. Haz un commit con tus cambios (`git commit -m 'Añadir nueva funcionalidad'`).
5. Sube tus cambios (`git push origin feature/nueva-funcionalidad`).
6. Abre un pull request.


=======================================
        Contacto
=======================================
Si tienes alguna duda o necesitas más detalles sobre el uso de la API o sobre cómo ejecutar el proyecto, no dudes en contactarme.

Correo electrónico: albertox35@yahoo.com.mx
