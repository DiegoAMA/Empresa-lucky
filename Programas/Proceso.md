# Proceso

## Descripción:
<p>Este repositorio documenta el proceso completo de análisis y generación de informes utilizando los datos ficticios. A continuación, se describen solo los pasos clave:
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
Primeramente se reviso la tendencia por medio del método "X-11" para cada linea y la sumatoria en conjunto. Siendo esta última la imagen representada a continuación.<br>
Durante el proceso de reporteo para directores. Se genero un analisis de los datos con la finalidad de generar diferentes forecast, siendo para todas las lineas como en un solo conjunto (Forecast total llamado en el código) y por separado (Forecast por linea).
<br></p>

<p align="center">
  <img src="https://github.com/DiegoAMA/Imagenes/blob/aadb604455dce8739b22475a408c8348db85756f/Lucky/Tendencias.png"></p><br>

<p>Tanto para el forecast total como por linea, se revisaron los outliers, la correlación entre los valores de venta contra las existencias y la estacionalidad de las series de tiempo mediante los gráficos de ACF (Autocorrelation Function) y PACF (Partial Autocorrelation Function).<br>
Una vez analizadas las series de tiempo se realizaron los forecast con los métodos de auto.arima (de forma automática), arima (Provando diversas combinaciones en base a los resultados de analisis de estacionalidad), ETS y lineal. Se evaluan por medio del AICc, R^2 Ajustado, la normalidad de sus residuales, la autocorrelación de los modelos, el RMSE y MAE; con el mejor modelo se genera uno nuevo utilizando boostcrapping (remuestro mediante selección aleatoria con remplazo) y bagging (Combinación de multiples modelos independientes).:<br>
Para fines practicos solo se muestran los resultados obtenidos de los modelos del forecast total. Las evaluaciones de estos quedaron de la siguiente manera:<br></p>

  | Modelo    | AICc       | R^2 Ajustado | Test jarque bera a residuales | Test de autocorrelación| RMSE (Raíz del error cuadratico medio)| MAE (Error absoluto medio) |
| ----------- | ---------- | ---------    | ----------------------------- | -----------------------| ------------------------------------  |----------------------------|
| Autoarima   | 965.94     | -----        | No normal                     | No autocorrelacionados | 1500 | 1256 |
| Arima       | 965.03     | -----        | No normal                     | No autocorrelacionados | 548  | 469  |
| ETS         | 1039.21    | -----        | Normal                        | No autocorrelacionados | 1290 | 883  |
| Reg. Lineal | -----      | 0.85         | Normal                        | No autocorrelacionados | 1686 | 1234 |
<br>
El modelo final para el forecast total fue ARIMA (1,1,1) con boostcrapping y bagging. Quedando la predicción para los siguientes seis meses.

<p align="center">
  <img src="https://github.com/DiegoAMA/Imagenes/blob/aadb604455dce8739b22475a408c8348db85756f/Lucky/Forecast%20Total.PNG"></p><br>


Siendo el módelo de los forecast para las tres lineas por separado el ETS con bootscarpping y bagging.
<p align="center">
  <img src="https://github.com/DiegoAMA/Imagenes/blob/aadb604455dce8739b22475a408c8348db85756f/Lucky/Forecast%20Linea%20Cocina.PNG"></p><br>



<br>
¡Saludos y gracias por llegar hasta aquí! :wave: :blush:


