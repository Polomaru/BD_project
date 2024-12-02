\# Proyecto Big Data \- CS3700

\#\# Introducción  
El uso de tarjetas de crédito en diversos comercios ha facilitado las compras diarias de las personas. Nos ahorra tener que llevar grandes cantidades de efectivo y también puede adelantar una compra completa que se puede pagar en el tiempo. No obstante, el análisis y la predicción de impagos en clientes de tarjetas de crédito es un área fundamental dentro del ámbito financiero, ya que permite a las instituciones bancarias y otras entidades crediticias gestionar y mitigar el riesgo asociado al crédito otorgado. En un contexto en el que el uso de tarjetas de crédito sigue siendo una herramienta común para el consumo, predecir si un cliente incurrirá en impagos en el futuro resulta crucial para la toma de decisiones en cuanto a la aprobación de créditos, establecimiento de límites y la gestión de carteras de clientes.

El objetivo de este trabajo es predecir el incumplimiento crediticio. 

\#\# Descripción del dataset

El dataset proviene de Kaggle, como parte de una competencia creada por American Express; el cual provee el dataset completo. Los datos de cada registro reflejan el estado de un cliente y su performance de pagador de crédito de los últimos 18 meses, y las columnas se encuentran agrupadas en las siguientes categorías. Existe un total de 50Gb de data provista.

- D\_\* \= Variables de delincuencia  
- S\_\* \= Variables de gastos  
- P\_\* \= Variables de pagos  
- B\_\* \= Variables de saldo  
- R\_\* \= Variables de riesgo

\#\# Dificultad técnica

* Cantidades masivas de datos: El dataset cuenta con más de 16Gb de entrenamiento y aproximadamente 34Gb de pruebas.  
* Datos desbalanceados: Existen más clientes que cumplen con sus pagos que aquellos que no lo hacen. Este desbalance puede hacer que el modelo tienda a predecir en su mayoría a los clientes como "no incumplidores", lo que puede afectar la precisión del modelo y las métricas de evaluación.  
* Naturaleza de los datos: El manejo de datos temporales y secuenciales puede ser complicado, dado que implica trabajar con líneas de tiempo de pagos y transacciones: Las variables como D\_, S\_, P\_, y B\_ reflejan comportamientos a lo largo del tiempo, por lo que es importante capturar correctamente las relaciones entre estas variables y el incumplimiento de pagos.

\#\# Herramientas empleadas

* Dask  
* Matplotlib  
* MongoDB  
* Wandb

\#\# Arquitectura del proyecto

\!\[Arquitectura\](https://i.imgur.com/Rmzh246.png)

\#\# Proceso ETL

Los datos son extraídos de Kaggle, el cual contiene la data de entrenamiento y prueba. Estos son procesados mediante Dask para poder aplicar transformaciones y guardarlas en MongoDB. Luego, los datos son extraídos de la base de datos y son cargados para entrenar el modelo de árboles de decisión. El entrenamiento es monitoreado por Weight and Biases. 

\#\# Resultados

\<Table\>

\#\# Dificultades

Buscar el mejor particionamiento para optimizar el uso de recursos computacionales.

\#\# Conclusiones

