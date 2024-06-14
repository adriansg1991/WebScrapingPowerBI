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
## 📦Librerías utilizadas
- Pandas
- Requests
  
---

### *CONSEJO*:

Antes de realizar el script directamente en Power BI, aconsejo realizarlo en el editor de código que utilices, VSCode, Pycharm, Jupyter Notebook, etc.

De esta forma, te puedes asegurar que funcione correctamente viendo el resultado final, además de ver posibles errores en el código. Posteriormente, solo basta con pegar el código en Power BI


![Script](https://github.com/adriansg1991/WebScrapingPowerBI/blob/main/WS1.png)
Como podéis ver, primero uso mi editor de código para importar el .csv de la web e importar únicamente las columnas que necesito para el análisis. Una vez veo el resultado final con el método .head (para poder ver los primeros registros).
De esta forma, me aseguro que el output final contenga la información que quiero. Por tanto, unicamente queda pegar el script en Power BI.
![ScriptPowerBI](https://github.com/adriansg1991/WebScrapingPowerBI/blob/main/WS2.png)

Además, aconsejo instalar la librería requests, para verificar si es posible importar datos de la web haciendo la petición al servidor.
![Request](https://github.com/adriansg1991/WebScrapingPowerBI/blob/main/WS3.png)


