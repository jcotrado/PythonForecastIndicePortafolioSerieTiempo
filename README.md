# PythonForecastIndicePortafolioSerieTiempo
Proyecto para realizar un pronostico de indice de portafolio con series de tiempo, se usan modelos ARIMA y SARIXMA, indices de portafolio de igual ponderación y poderación por capital

OBJETIVOS

- Entender Las bases de las series de tiempo
- Conocer y preparar los datos de la serie de tiempo y normalizarlos (desde data en bruto, a limpia y procesada para analisis)
- Entender algunos conceptos de indices basicos y manejo de correlaciones
- Crear indices para realizar el analisis y pronostico del portafolio (Equal-Weighted Index)
- Realizar un proceso de entrenamiento basico de la serie de tiempo
- Aplicar metodologias de modelos ARIMA and SARIMAX para hacer el pronostico usando series de tiempo
- 
NOTA 1: Datos obtenidos desde series de tiempo del Banco Central de Chile https://si3.bcentral.cl/Bdemovil/BDE/IndicadoresDiarios
NOTA 2 : En este ejemplo se considera el pronostico del indice de un portafolio de acciones chilenas (FALABELLA y SONDA), con 2 unidades de cada una.
NOTA 3 : Las series de tiempo disponibles en las carpetas compartidas, tienen datos desde 2015-01-02 a 2023-08-16

RELEASE 2023-08-30 

Funcionalidades: 

- Funcionalidad operativa para el pronostico de serie de tiempo
- Para sumar mas acciones al portafolio, subir los datos en la carpeta "\PronosticoSerieTiempo-Stocks-Cryptos\Acciones", se necesitara actualizar la parte del calculo del indice de capitalización ponderada (incluir el numero de acciones y el nuevo nemonico en la lista)

          my_assets=accionesChile
          
          # En este ejemplo, se asume que el portafolio se constituye de 1 accion de SONDA y una de FALABELLA
          #

          #w = cw_index(<fecha de la inversion>, [<Numero de unidades x activo>], [<Nemonicos>])
          w = capitalizationWeighted("2023-08-14", [1,1], ["FALABELLA","SONDA"])

Errores:

- Se pude mejorar el proceso integrando nuevos indicadores o factores economicos que puedan presentar una mejor correlaciones con los indices.