# Proceso

## Descripción:
<p>Este repositorio documenta el proceso completo de análisis y generación de informes utilizando los datos ficticios. A continuación, se detallan solo los pasos clave del proceso:
<br></p>

<p> 1.- Generación de Datos: <br>Se crea una base de datos ficticia que simula el entorno del negocio.
La información es almacenada en una base de datos SQL para su posterior análisis.<br></p>

<p> 2.- Importación y Preparación de Datos con R: <br>Utilizando el lenguaje de programación R, se realiza la importación de datos desde la base SQL.
Se lleva a cabo la preparación de la información necesaria para la generación de pronósticos.<br></p>

<p> 3.- Pronósticos con R: <br> Se aplican diversos métodos de pronóstico a los datos preparados en R.
Los resultados finales del pronóstico son cruciales para la toma de decisiones futuras.<br></p>

<p>4.- Conexión con Power BI: <br> Se establece una conexión efectiva entre Power BI y la base de datos SQL.
Se formula una consulta específica para obtener datos relevantes y alimentar el informe de Power BI. <br></p>

<p>5.- Generación de Reportes en Power BI: <br> Utilizando los resultados del pronóstico y la consulta SQL, se genera un informe completo en Power BI.
Este informe proporciona insights visuales y analíticos para facilitar la comprensión de los datos. <br></p>

<p>6.- Proceso de ETL Completo:<br> La manipulación de datos no se limita solo a R y Power BI. Se ejecutan pasos adicionales en SQL para dar forma a la información.
Posteriormente, se continúa con procesos en R para garantizar la coherencia de los reportes de Excel destinados a la fuerza de ventas.<br></p>

<p>Este repositorio sirve como un recurso integral para entender y replicar el flujo completo de trabajo desde la generación de datos hasta la presentación de informes visuales. Explora los archivos y carpetas para acceder a los scripts, consultas y visualizaciones utilizadas en cada etapa del proceso.<br></p>

# Forecast
<p>
Primeramente se reviso la tendencia por medio del método "X-11" para cada linea y su sumatoria en conjunto. Siendo esta última la imagen representada a continuación.<br>
Durante el proceso de reporteo para directores. Se genero un analisis de los datos con la finalidad de generar diferentes forecast, siendo para todas las lineas como un solo conjunto (Forecast total llamado en el código) y por separado (Forecast por linea).
<br></p>

inserte imagen aquí

<p>Tanto para el forecast total como por linea, se revisaron los outliers, la correlación entre los valores de venta contra los desplazamiento y la estacionalidad de las series de tiempo mediante los gráficos de ACF (Autocorrelation Function) y PACF (Partial Autocorrelation Function).<br>
Una vez analizadas las series de tiempo se realizaron los forecast con los métodos de auto.arima (de forma automática), arima (Provando diversas combinaciones en base a los resultados de analisis de estacionalidad), ETS y lineal.

  <br></p>


¡Saludos!


