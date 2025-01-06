=======================================
        README.txt
=======================================

Descripción del Proyecto
=======================================
Este proyecto utiliza la API de NewsAPI para obtener las últimas noticias y almacenarlas en una base de datos SQLite. Los datos obtenidos se procesan para ser utilizados en análisis y visualizaciones. 

=======================================
        Requisitos previos
=======================================
Antes de ejecutar este código, asegúrate de tener instaladas las siguientes bibliotecas de Python:

1. **requests**: Para realizar consultas HTTP a la API de NewsAPI.
2. **pandas**: Para la manipulación y análisis de los datos obtenidos.
3. **sqlite3**: Para interactuar con la base de datos SQLite y almacenar los datos.
4. **json**: Para trabajar con el formato JSON que se obtiene de la API.

Puedes instalar las bibliotecas necesarias ejecutando el siguiente comando:
pip install requests pandas sqlite3


======================================= 
	Estructura del Proyecto
======================================= 

La estructura del proyecto es la siguiente:
/NewsAPI			# Carpeta que contiene los scripts de Python
├── NewsAPI.db			# Base de datos
├── NewsAPI.ipynb		# Script que ejecuta el análisis y genera las visualizaciones
├── /Visualizaciones/		# Carpeta donde se guardarán las imágenes generadas
└── README_NewsAPI.txt		# Este archivo

=======================================
        Instrucciones para el uso
=======================================
Para usar este proyecto, sigue estos pasos:

1. **Obtener tu API Key**:
   - Regístrate en (https://newsapi.org/register) para obtener tu API Key.
   - Reemplaza el valor de 'apiKey' en el código con tu propia clave API.

2. **Configuración de la API Key**:
   - En el archivo de código, encontrarás una línea de parámetros donde se configura la API:
   
     ```python
     params = {
         'country': 'us',  # Cambiar el país según sea necesario
         'apiKey': 'TU_API_KEY_AQUI'  # Reemplaza con tu API Key
     }
     ```

   - Sustituye `'TU_API_KEY_AQUI'` por la clave que obtuviste de NewsAPI.

3. **Ejecución del código**:
   - Una vez configurado tu API Key, ejecuta el código para obtener los artículos de noticias.
   - Los datos se almacenarán en un archivo JSON y luego serán insertados en una base de datos SQLite local.

=======================================
        Recomendaciones de Seguridad
=======================================
**1. No compartas tu API Key.**  
   La **API Key** es personal y única. Si compartes tu API Key con otros, pueden hacer uso de tu cuota diaria, lo que podría resultar en que se te agote el límite o incluso que se bloquee tu acceso.

**2. Mantén tu API Key privada.**  
   Evita subir tu API Key a repositorios públicos como GitHub. Si trabajas en un entorno colaborativo, utiliza variables de entorno para gestionar tu clave de forma segura.

**3. No ejecutes el código repetidamente.**  
   Ejecutar el código múltiples veces puede consumir tu cuota diaria de solicitudes. El plan gratuito de NewsAPI permite 500 solicitudes por día. Asegúrate de que no sobrepasas este límite.

**4. Regenera tu API Key si sospechas que ha sido comprometida.**  
   Si por alguna razón tu API Key es compartida sin intención o sospechas de un uso indebido, regístrala nuevamente en el portal de NewsAPI para evitar que otros la utilicen.

**5. Plan de uso.**  
   Si necesitas realizar más solicitudes de las que el plan gratuito permite, considera cambiar a un plan de pago o implementar soluciones como la caché para reducir la cantidad de solicitudes.

=======================================
        Consideraciones Técnicas
=======================================
El código descarga los datos de noticias de NewsAPI y los guarda en un archivo JSON. Luego, los artículos se procesan y almacenan en una base de datos SQLite para facilitar su posterior consulta y análisis.

Recuerda que ejecutar el código de forma excesiva puede consumir rápidamente tu cuota diaria. Utiliza el código de manera controlada y realiza consultas solo cuando sea necesario.

=======================================
        Contacto
=======================================
Si tienes alguna duda o necesitas más detalles sobre el uso de la API o sobre cómo ejecutar el proyecto, no dudes en contactarme.

Correo electrónico: albertox35@yahoo.com.mx

