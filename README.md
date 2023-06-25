# Proyecto de Data & Analytics en Azure y Spark

Este proyecto ofrece una solución **end-to-end** de **Data & Analytics** en el ámbito financiero y de redes sociales, aprovechando las tecnologías de **Azure**. Demostramos cómo Azure proporciona una plataforma completa y escalable para la **ingesta, procesamiento y análisis de datos**.

*Datos obtenidos de: https://www.kaggle.com/datasets/omermetinn/tweets-about-the-top-companies-from-2015-to-2020?resource=download*


## Objetivos del proyecto
Objetivo principal: 
Mostrar la influencia de las redes sociales en el mercado de acciones, a lo largo del tiempo.

Objetivos particulares:
1. Mostrar la relación que se encuentra entre el precio de las acciones y el volumen de ventas.
2. Relacionar el precio y el volumen de venta de las acciones con las interacciones de Twitter.
3. Comparar el desempeño de las empresas en Twitter, en contraste con su valor de bolsa.


*Documentacion del proceso: https://drive.google.com/file/d/1JKLcAkMY0Bd_0D1Lc07I99I-Xd9fPubQ/view?usp=sharing*






## Proceso de manipulación y transformación de datos
- **Extracción de datos:** Los datos se originan en una base de datos SQL Server (**Azure SQL**) y se extraen utilizando **Azure Data Factory**, guardando en formato CSV en la carpeta "Raw data" del Datalake. Se ha creado un pipeline que incluye un **LookUp** para buscar y leer los datos, y un **ForEach** para iterar sobre ellos y realizar acciones específicas.

- **Transformación con Azure Databricks:** La primera notebook de **Azure Databricks** llamada "Raw to Trusted", lee los datos de "Raw data" para su manipulación y transformación utilizando **PySpark**. Se aplican las transformaciones necesarias para preparar los datos para el análisis posterior. Finalmente, la primera notebook guarda los resultados de las transformaciones en formato **Parquet** en la ruta "Trusted". La segunda notebook, llamada "Trusted to Refined" utiliza **SparkSQL** para realizar los JOIN necesarios y combinar las tablas relevantes para el análisis. Finalmente, esta ultima notebook carga la informacion refinada en una base de datos SQL.  

- **Almacenamiento de datos:** Los dataframes transformados se guardan en formato Parquet en un Data Lake de Azure (Azure Data Lake Gen2). Esto permite un almacenamiento eficiente y escalable de los datos preparados. Tambien se utiliza Azure SQL para el analisis final de los datos desde Power BI

- **Análisis con Power BI:** Se aprovecha la integracion entre Power BI y Azure SQL para construir un tablero interactivo que muestre informacion relevante para la toma de decisiones.

## Arquitectura del proyecto
![Arquitectura_financiero-Page-2 drawio](https://github.com/MJuanM/Financiero-Spark/assets/108939684/5f3f2112-c319-4c36-b606-d113161a7706)

## Beneficios
- Escalabilidad y eficiencia: La combinación de Azure Data Factory, Azure Databricks y Power BI proporciona una solución escalable y eficiente para la ingesta, procesamiento y análisis de datos.

- Facilidad de uso: Las herramientas de Azure utilizadas en este proyecto ofrecen una interfaz intuitiva y una integración fluida, lo que permite a los usuarios aprovechar al máximo la plataforma.

- Toma de decisiones basadas en datos: Con la visualización interactiva y los informes generados, los interesados pueden tomar decisiones informadas y estratégicas en el ámbito financiero y de redes sociales.

## Requisitos
Se requiere una suscripción a Azure para utilizar las tecnologías mencionadas en este proyecto.
Se debe configurar adecuadamente Azure Data Factory, Azure Databricks y Power BI para aprovechar al máximo sus funcionalidades.
