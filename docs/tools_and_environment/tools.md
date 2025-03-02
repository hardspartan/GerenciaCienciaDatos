# 🛠️ Herramientas y Entornos de Trabajo

## Descripción
Este documento describe el stack tecnológico y las herramientas utilizadas en el proyecto de predicción de precios de ganado, abarcando desde la gestión de datos hasta la implementación del modelo en producción.

## 1. Gestión y Procesamiento de Datos
- **AWS S3**: Almacenamiento de datos crudos, procesados y de validación.
- **AWS Glue**: Extracción, transformación y carga (ETL) automatizada de datos.
- **Pandas / PySpark**: Manipulación y procesamiento eficiente de grandes volúmenes de datos.
- **SQL (Amazon Redshift)**: Consulta y estructuración de datos históricos.

## 2. Análisis y Modelado
- **Jupyter Notebooks**: Exploración de datos, visualización y experimentación con modelos.
- **AWS SageMaker**: Entrenamiento y ajuste de modelos de machine learning a escala.
- **XGBoost / Random Forest**: Algoritmos utilizados para la predicción de precios.
- **Scikit-learn**: Evaluación de modelos y cálculo de métricas de desempeño.

## 3. Implementación y Despliegue
- **AWS SageMaker Endpoint**: Servicio para exponer el modelo como API en producción.
- **Flask / FastAPI**: Alternativa para construir una API local de inferencia.
- **AWS Lambda**: Ejecución sin servidores para consultas rápidas al modelo.
- **Docker**: Contenedores para reproducibilidad y despliegue escalable.

## 4. Monitoreo y Mantenimiento
- **AWS CloudWatch**: Monitoreo de logs y rendimiento del modelo en producción.
- **AWS CloudTrail**: Seguimiento de accesos y auditoría de cambios en los datos.
- **MLflow**: Seguimiento de experimentos y versiones de modelos.

## 5. Gestión del Proyecto
- **GitHub**: Control de versiones y colaboración en el desarrollo del proyecto.
- **JIRA / Trello**: Planificación y seguimiento de tareas.
- **Power BI / Tableau**: Visualización de resultados y generación de reportes.

Este stack tecnológico permite una gestión eficiente del ciclo de vida del proyecto, asegurando escalabilidad y rendimiento óptimo en cada etapa.

