# ℹ️ Power BI | Web scraping con Python
[![Python Version](https://img.shields.io/badge/python-3.8-blue)](https://www.python.org/downloads/release/python-380/)
[![Pandas](https://img.shields.io/badge/pandas-1.2.0+-yellow)](https://pandas.pydata.org/)
![Power BI](https://img.shields.io/badge/Power%20BI-Transforming%20Data%20into%20Insights-orange?style=flat&logo=power-bi)
![Requests](https://img.shields.io/badge/Requests-v2.26.0-blue)


<div id="header" align="center">
  <img src="https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExcm1tN3Zsdm81cjVjZTJscmExdmV2eTM3YmlkN2hzZHFhbDA2YXRmdCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/Zebztgv7jmkoLe1DoY/giphy.gif" width="100"/>
</div>

## Introducción

Este proyecto implica la implementación de web scraping mediante un sencillo script de Python en Power BI para extraer datos de una página web específica. En este caso, el objetivo es importar un archivo .csv que ha sido cargado en una web directamente a Power BI y que se vaya actualizando automáticamente sin necesidad de cambiar el origen de datos cada vez que se actualizen los datos en la web.

La automatización de este proceso resulta altamente beneficioso, ya que hay ocasiones en las que los datos del archivo subido en la página web se actualizan con frecuencia. Realizar esta tarea de manera manual implicaría ajustar continuamente la ruta de origen y descargar el archivo .csv cada vez que se desee actualizar. Al aplicar esta solución, Power BI se conectará directamente al origen de datos, eliminando la necesidad de llevar a cabo estos pasos manuales.

A continuación, explicaré como abordé esta casúistica mediante un breve script en Python, aprovechando las bibliotecas Pandas y requests.
<div id="header" align="center">
  <img src="https://miro.medium.com/v2/resize:fit:720/format:webp/1*DKnPHPUBOuSV50E6Rq0vyQ.png" width="800"/>
</div>

---
### Requisitos

- Instalar Python.
- Instalar las librerías “requests” y“pandas”.
- Instalar Power BI.
- Generar Script de Python en Power BI para obtener el enlace correcto y ejecutarlo.


### 📦Librerías utilizadas
- Pandas: Es una poderosa biblioteca de Python diseñada para el análisis y manipulación de datos estructurados. Su estructura principal, el DataFrame, facilita la carga, limpieza y análisis de datos tabulares, ofreciendo herramientas eficientes para transformaciones complejas y visualización de información
- Requests: Es una biblioteca Python sencilla y eficaz para realizar solicitudes HTTP. Permite a los desarrolladores enviar y recibir datos a través de la web de manera fácil y rápida, gestionando aspectos como autenticación, cookies y sesiones de manera intuitiva, ideal para interactuar con APIs y servicios web externos.
  
---

### *CONSEJO*:

Antes de realizar el script directamente en Power BI, aconsejo realizarlo en el editor de código que utilices, VSCode, Pycharm, Jupyter Notebook, etc.

De esta forma, te puedes asegurar que funcione correctamente viendo el resultado final, además de ver posibles errores en el código. Posteriormente, solo basta con pegar el código en Power BI.
<p align="center">
  <img src="https://github.com/adriansg1991/WebScrapingPowerBI/blob/main/WS1.png" alt="Script">
</p>

Como podéis ver, primero uso mi editor de código para importar el .csv de la web e importar únicamente las columnas que necesito para el análisis. Una vez veo el resultado final con el método .head (para poder ver los primeros registros).
De esta forma, me aseguro que el output final contenga la información que quiero. Por tanto, unicamente queda pegar el script en Power BI.
<p align="center">
  <img src="https://github.com/adriansg1991/WebScrapingPowerBI/blob/main/WS2.png" alt="ScriptPowerBI">
</p>

Además, aconsejo instalar la librería requests, para verificar si es posible importar datos de la web haciendo la petición al servidor.
<p align="center">
  <img src="https://github.com/adriansg1991/WebScrapingPowerBI/blob/main/WS3.png" alt="Request">
</p>


```python
import requests

response = requests.get('https://opendata-ajuntament.barcelona.cat/data/dataset/29d1b774-a83e-4c1e-91f7-1b9ad042ea83/resource/87a8aeda-d3eb-4ba5-bcad-b9ab0c296df5/download/2022_accidents_causa_conductor_gu_bcn_.csv')

print(response.status_code)
200 # OK
``` 

Usamos la librería request con el método get para preguntarle al servidor si podemos solicitar información o recursos concretos de la web.
Si el código de respuesta es 200, significa que puedes importar la información.

En algunas webs no es posible importar información. Existen diferentes respuestas que te puede devolver requests.get:

- **1xx**: Informativo — Solicitud recibida, proceso continuo.
- **2xx: Success — La acción fue recibida, entendida y aceptada con éxito.**
- **3xx**: Redirección — Se deben tomar medidas adicionales para completar la solicitud.
- **4xx**: Error de cliente: la solicitud contiene una sintaxis incorrecta o no se puede cumplir.
- **5xx**: Error de servidor — El servidor no pudo cumplir con una solicitud aparentemente válida.

---
## Web Scrapping
Se trata de un procedimiento utilizado para extraer datos de sitios web mediante el uso del lenguaje de programación Python, con el objetivo de conectar la extracción directamente a Power BI.

Para llevar a cabo este proceso, es esencial contar con Python instalado en nuestros equipos y especificar la ruta de instalación en la aplicación Power BI. Esto permitirá establecer la conexión necesaria entre la extracción de datos mediante Python y la integración fluida con Power BI. La instalación adecuada de Python y la configuración precisa de la ruta son pasos cruciales para garantizar el funcionamiento eficiente de esta conexión.

## Desarrollo
En ocasiones, surge la necesidad de descargar archivos periódicamente desde una página web y posteriormente reemplazar los archivos existentes con la versión más reciente.
El siguiente ejercicio busca simular la interacción humana al descargar un archivo CSV desde un sitio web específico. Se logra mediante un pequeño script en Power BI, que automatiza este proceso.
Para este propósito, he empleado un conjunto de datos de la página Open Data del Ajuntament de Barcelona. Este conjunto de datos proporciona información sobre los accidentes gestionados por la Guàrdia Urbana en Barcelona, clasificados por causa.
A continuación, presento un script básico en Power BI para llevar a cabo esta tarea:
import pandas as pd

```python
url = 'https://opendata-ajuntament.barcelona.cat/data/dataset/29d1b774-a83e-4c1e-91f7-1b9ad042ea83/resource/87a8aeda-d3eb-4ba5-bcad-b9ab0c296df5/download/2022_accidents_causa_conductor_gu_bcn_.csv'

AccidentsBCN2022 = pd.read_csv(url)

columns_ok = ['Nom_districte','Nom_barri','Nom_carrer','Descripcio_dia_setmana','NK_Any','Mes_any','Nom_mes','Dia_mes','Hora_dia','Descripcio_causa_mediata','Descripcio_torn']
AccidentsBCN2022 = AccidentsBCN2022[columns_ok]
```


Podemos usar Pandas para Data cleaning & Data Wrangling. Por ejemplo, eliminar nulos e importar únicamente las columnas que nos importan. De esta manera, la importación será más eficiente y ocupará menos espacio.

## Datasets
Lo podéis consultar en el siguiente link:
*https://opendata-ajuntament.barcelona.cat/data/es/dataset/accidents_causa_conductor_gu_bcn*

## Resultado final
<div id="header" align="center">
  <img src="https://miro.medium.com/v2/resize:fit:720/format:webp/1*juD-r5hPdEMEK5R_DP1KQA.gif" width="850"/>
</div>

Ya hemos establecido la conexión entre Power BI y la fuente de datos, lo que significa que cualquier cambio en el archivo cargado en la web se reflejará automáticamente en el dashboard.
Simplemente actualizando la información en Power BI, podemos mantener el dashboard actualizado sin la necesidad de modificar el origen de datos.


---

En lugar de utilizar un programa de visualización de datos como Power BI, también podemos aprovechar librerías de Python como Matplotlib o Seaborn para crear gráficos. Aunque esta opción puede ser más compleja, si lo comparamos con Power BI, proporciona un mayor control sobre la personalización de las visualizaciones.

---

## 📬 Contacto

Si tienes alguna pregunta o sugerencia, no dudes en contactarme a través de [mi correo electrónico](mailto:adriansg1991@gmail.com) o en [Linkedin](https://linkedin.com/in/adriansanchez-garcia/).

¡Gracias por visitar el repositorio! 🚀
