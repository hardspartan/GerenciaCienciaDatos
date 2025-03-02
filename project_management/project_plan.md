# 📌 Plan del Proyecto

## Descripción
Este documento define el alcance, objetivos y cronograma general del proyecto de predicción de precios de ganado. El objetivo principal es mejorar el rendimiento de un modelo de machine learning para predecir el precio del ganado, reduciendo el **RMSE (Root Mean Squared Error)** y aumentando el **R² (Coeficiente de Determinación)**. A continuación, se detallan las fases del proyecto, los entregables esperados y los responsables de cada actividad.

---

## Alcance del Proyecto
El proyecto se enfoca en mejorar un modelo de predicción de precios de ganado mediante la aplicación de técnicas de ciencia de datos. El alcance incluye:

- **Limpieza y preparación de datos**: Imputación de valores nulos, eliminación de outliers, y enriquecimiento del dataset con datos externos (tipo de cambio del dólar y datos climáticos).
- **Modelado y optimización**: Implementación y optimización de un modelo de machine learning (**XGBoost**) utilizando **AWS SageMaker**.
- **Evaluación y despliegue**: Evaluación del modelo final con métricas clave (**RMSE** y **R²**) y despliegue del modelo en producción.

---

## Objetivos del Proyecto
Los objetivos del proyecto se definieron siguiendo la metodología **SMART**:

- **Específico**: Mejorar la precisión del modelo de predicción de precios de ganado.
- **Medible**: Reducir el **RMSE** y aumentar el **R²** respecto al modelo inicial.
- **Alcanzable**: Utilizar técnicas de limpieza de datos, selección de características y optimización de hiperparámetros.
- **Relevante**: El modelo mejorado permitirá a los ganaderos y compradores tomar decisiones más informadas sobre el precio del ganado.
- **Temporal**: El proyecto se completará en un plazo de **4 semanas**, con entrega final el **2 de marzo**.

---

## Cronograma General de Trabajo
El proyecto se divide en **4 semanas**, siguiendo las fases de la metodología **CRISP-DM**. A continuación, se detalla el cronograma, las actividades, los entregables y los responsables de cada fase.

| **Semana** | **Fase CRISP-DM**       | **Actividades**                                                                 | **Entregables**                                                                 | **Responsable**       |
|------------|-------------------------|--------------------------------------------------------------------------------|--------------------------------------------------------------------------------|-----------------------|
| Semana 1   | Comprensión del Negocio | - Definición del problema y objetivos.<br>- Revisión del modelo inicial.       | - Documento de objetivos y métricas.<br>- Análisis del modelo inicial.         | John, Edwin, Jhoan    |
| Semana 2   | Comprensión de los Datos| - Análisis exploratorio de datos (EDA).<br>- Identificación de valores nulos y outliers. | - Dataset limpio y enriquecido.<br>- Reporte EDA con visualizaciones clave.    | Edwin                 |
| Semana 3   | Preparación de los Datos| - Limpieza de datos (imputación de valores nulos, eliminación de outliers).<br>- Integración de datos externos (`dolar.csv` y `clima.csv`). | - Dataset listo para el modelado.<br>- Pipeline de datos en AWS Glue.          | Jhoan                 |
| Semana 4   | Modelado y Evaluación   | - Implementación y optimización del modelo.<br>- Evaluación del modelo final.  | - Modelo optimizado.<br>- Reporte de evaluación con métricas clave.            | John                  |
| Semana 4   | Despliegue              | - Despliegue del modelo en producción utilizando AWS SageMaker.                | - Modelo en producción.<br>- Documentación técnica del despliegue.             | John                  |

---

## Entregables Esperados
A continuación, se listan los entregables clave del proyecto:

1. **Documento de objetivos y métricas**: Definición clara del problema, objetivos SMART y métricas de éxito.
2. **Reporte EDA**: Análisis exploratorio de datos con visualizaciones clave (distribución de `Precio_Kilo`, matriz de correlación).
3. **Dataset limpio y enriquecido**: Dataset listo para el modelado, con valores nulos imputados y outliers eliminados.
4. **Modelo optimizado**: Modelo de machine learning (**XGBoost**) con hiperparámetros ajustados.
5. **Reporte de evaluación**: Evaluación del modelo final con métricas clave (**RMSE** y **R²**).
6. **Modelo en producción**: Despliegue del modelo en **AWS SageMaker** para su uso en producción.

---

## Responsables por Actividad
- **John**: Responsable de la comprensión del negocio, modelado y optimización, y despliegue del modelo.
- **Edwin**: Responsable del análisis exploratorio de datos (EDA) y la preparación de los datos.
- **Jhoan**: Responsable de la infraestructura de datos y la integración de datos externos.

---

## Resultados Finales
El proyecto logró superar los objetivos iniciales, alcanzando un **RMSE de 159.97** y un **R² de 0.84** con el modelo optimizado de **XGBoost**. Los entregables clave, como el dataset limpio y enriquecido, el modelo optimizado y el despliegue en producción, fueron completados dentro del plazo establecido.

---

## Lecciones Aprendidas
- **Colaboración efectiva**: La coordinación entre los roles de Data Scientist, Data Analyst y Data Engineer fue clave para el éxito del proyecto.
- **Importancia de la calidad de los datos**: La limpieza y enriquecimiento de los datos fueron fundamentales para mejorar el rendimiento del modelo.
- **Optimización de modelos**: La búsqueda manual de hiperparámetros en **XGBoost** permitió alcanzar un rendimiento superior al esperado.

---

Este documento refleja el plan de trabajo que permitió alcanzar los objetivos del proyecto de manera exitosa.
