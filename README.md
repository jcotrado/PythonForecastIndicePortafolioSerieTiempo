# PythonForecastIndicePortafolioSerieTiempo
Proyecto para realizar un pronostico de indice de portafolio con series de tiempo, se usan modelos ARIMA y SARIXMA, indices de portafolio de igual ponderación y poderación por capital

OBJETIVOS

- Entender Las bases teoricas de las series de tiempo
- Conocer y preparar los datos de la serie de tiempo y normalizarlos (desde data en bruto, a limpia y procesada para analisis)
- Entender algunos conceptos de indices basicos y manejo de correlaciones
- Crear indices para realizar el analisis y pronostico del portafolio (Equal-Weighted y Capitalization-Weight)
- Realizar un proceso de entrenamiento basico de la serie de tiempo
- Aplicar metodologias de modelos ARIMA and SARIMAX para hacer el pronostico usando series de tiempo
- Realizar pronosticos utilizando una serie de tiempo desde 2020-01-02 a 2023-08-16


NOTA 1: Datos obtenidos desde series de tiempo del Banco Central de Chile https://si3.bcentral.cl/Bdemovil/BDE/IndicadoresDiarios
NOTA 2 : En este ejemplo se considera el pronostico del indice de un portafolio de acciones chilenas (FALABELLA y SONDA), con 2 unidades de cada una.
NOTA 3 : Las series de tiempo disponibles en las carpetas compartidas, tienen datos desde 2015-01-02 a 2023-08-16

RELEASE 2023-08-30 

Funcionalidades: 

- Funcionalidad operativa para el pronostico de serie de tiempo
- Para sumar mas acciones al portafolio, subir los archivos con datos en la carpeta "\PronosticoSerieTiempo-Stocks-Cryptos\Acciones", se necesitara actualizar la parte del calculo del indice de capitalización ponderada (incluir el numero de acciones y el nuevo nemonico en la lista)

          my_assets=accionesChile
          
          # En este ejemplo, se asume que el portafolio se constituye de 1 accion de SONDA y una de FALABELLA
          #

          #w = cw_index(<fecha de la inversion>, [<Numero de unidades x activo>], [<Nemonicos>])
          w = capitalizationWeighted("2023-08-14", [1,1], ["FALABELLA","SONDA"])

Analisis TPM - TIB
 ![image](https://github.com/jcotrado/PythonForecastIndicePortafolioSerieTiempo/assets/25447366/caff54de-60e5-499d-80d3-67ae5309783f)


TPM: Tasa de politica Monetaria
TIB: Tasa Interbancaria

Pronostico con modelo ARIMA e Indice de portafolio de igual ponderación
![image](https://github.com/jcotrado/PythonForecastIndicePortafolioSerieTiempo/assets/25447366/e1915ad2-725f-4817-acc2-74c83f78d882)

La tasa de errores del pronostico con ARIMA son: 
MSE = 0.149988 
RMSE = 0.022496

Pronostico con modelo  SARIXMA  e Indice de portafolio de igual ponderación
![image](https://github.com/jcotrado/PythonForecastIndicePortafolioSerieTiempo/assets/25447366/4a2c69c6-3294-40bc-91e0-b480223480bf)

La tasa de error de predicciones SARIMAX es: 
MSE = 0.149988 
RMSE = 0.022496


Pronostico con modelo  SARIXMA  e Indice de portafolio de ponderación por capital (a una fecha especifica):
![image](https://github.com/jcotrado/PythonForecastIndicePortafolioSerieTiempo/assets/25447366/260404de-fb7c-4903-98c2-c268b135f738)

La tasa de error de predicciones SARIMAX es: 
MSE = 0.067973 
RMSE = 0.022496



Mejoras:

- Se pude mejorar el proceso integrando nuevos indicadores o factores economicos que puedan presentar una mejor correlaciones con los indices.
- Se pueden probar la fiabilidad con periodos de pruebas mas cortos
