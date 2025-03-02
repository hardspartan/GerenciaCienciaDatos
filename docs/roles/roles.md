# 👨‍💻 Definición de Roles

## Descripción
Este documento define los roles y responsabilidades de cada miembro del equipo en el proyecto de predicción de precios de ganado. El objetivo principal del proyecto fue mejorar la precisión del modelo de predicción, reduciendo el **RMSE (Root Mean Squared Error)** y aumentando el **R² (Coeficiente de Determinación)**. Se logró superar las expectativas, alcanzando un **RMSE de 159.97** y un **R² de 0.84** con un modelo optimizado de **XGBoost**. A continuación, se describen los roles y las responsabilidades asignadas a cada integrante del equipo.

---

## Roles y Responsabilidades

### 1. **Data Scientist**
**Responsable**: Jhoan  
**Responsabilidades**:

- **Modelado**: Desarrollo y optimización del modelo de machine learning. En este proyecto, Jhoan se encargó de implementar y optimizar el modelo de **XGBoost**, utilizando técnicas como la búsqueda manual de hiperparámetros (`max_depth`, `learning_rate`, `min_child_weight`, `subsample`, `colsample_bytree`).
- **Análisis avanzado**: Extracción de insights a partir de los resultados del modelo, identificando las variables más importantes para la predicción del precio por kilo (`Dolar`, `Temperatura_Minima`, `Precipitacion`).
- **Evaluación del modelo**: Monitoreo de métricas clave como **RMSE** y **R²** para asegurar que el modelo cumpliera con los objetivos del proyecto.

**Tareas realizadas**:
- Implementación del modelo **XGBoost** y optimización de hiperparámetros.
- Evaluación del rendimiento del modelo final, logrando un **RMSE de 159.97** y un **R² de 0.84**.
- Análisis de la importancia de las variables en el modelo final.

---

### 2. **Data Analyst**
**Responsable**: Edwin  
**Responsabilidades**:

- **Análisis exploratorio de datos (EDA)**: Identificación de problemas en los datos, como valores nulos, outliers y baja correlación entre variables.
- **Visualización de datos**: Creación de gráficos y reportes para comunicar los hallazgos del análisis exploratorio.
- **Preparación de datos**: Limpieza y transformación de los datos para su uso en el modelado.

**Tareas realizadas**:
- Realización del **EDA** para identificar valores nulos en columnas como `Raza`, `Marca` y `Peso`, y outliers en `Precio_Kilo`.
- Integración de datos externos (`dolar.csv` y `clima.csv`) para enriquecer el dataset.
- Creación de visualizaciones clave, como la matriz de correlación y la distribución de `Precio_Kilo` antes y después de la limpieza de datos.

---

### 3. **Data Engineer**
**Responsable**: John  
**Responsabilidades**:

- **Infraestructura de datos**: Configuración y mantenimiento de la infraestructura en la nube (**AWS SageMaker**) para el entrenamiento y despliegue del modelo.
- **Pipelines ETL**: Desarrollo de pipelines para la extracción, transformación y carga de datos, asegurando que los datos estén disponibles y listos para su uso en el modelado.
- **Integración de datos**: Conexión de los datos principales con fuentes externas (tipo de cambio del dólar y datos climáticos).

**Tareas realizadas**:
- Configuración del entorno en **AWS SageMaker** para el entrenamiento y evaluación del modelo.
- Desarrollo de pipelines **ETL** para integrar los datos de `dolar.csv` y `clima.csv` con el dataset principal.
- Implementación del modelo final en producción utilizando **SageMaker**, asegurando su escalabilidad y mantenimiento.