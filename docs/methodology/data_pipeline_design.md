# 🔄 Diseño del Pipeline de Datos

## **Arquitectura del Pipeline de Datos**

### **1. Ingesta y Transformación de Datos**
En esta fase, se recopilaron y procesaron los datos necesarios para el proyecto. El pipeline de ingesta y transformación incluyó los siguientes pasos:

- **Ingesta de datos**:
  - **Datos principales**: Se cargó el dataset principal (`Bd_Transacciones.csv`) desde **Amazon S3**, que contenía información sobre transacciones ganaderas, incluyendo variables como `Precio_Kilo`, `Peso`, `Raza`, `Tipo_Remate`, y `Fecha`.
  - **Datos externos**: Se integraron datos adicionales desde `dolar.csv` (tipo de cambio del dólar) y `clima.csv` (datos meteorológicos como temperatura y precipitación).

- **Transformación de datos**:
  - **Limpieza de datos**: Se imputaron valores nulos en columnas como `Raza` y `Marca` con "Desconocido" y "Sin Marca", respectivamente. Además, se eliminaron outliers en `Precio_Kilo` utilizando el rango intercuartílico (IQR).
  - **Integración de datos**: Se cruzaron los datos principales con `dolar.csv` y `clima.csv` utilizando la columna `Fecha`.
  - **Agrupación de categorías**: Se agruparon categorías poco frecuentes en `Raza`, `Marca` y `Categoria` bajo la etiqueta "Otras".
  - **Imputación de valores nulos en datos externos**: Para las columnas de clima (`Temperatura_Promedio`, `Temperatura_Minima`, `Temperatura_Maxima`, `Precipitacion`), se aplicaron técnicas de interpolación lineal y relleno hacia adelante y atrás (`ffill` y `bfill`).

**Herramientas utilizadas**:
- **AWS Glue**: Para la extracción y transformación de datos.
- **Pandas**: Para la limpieza y transformación de datos en el entorno de desarrollo local.

---

### **2. Almacenamiento y Disponibilidad**
Una vez transformados, los datos se almacenaron en un formato accesible para el modelado y análisis. El almacenamiento y disponibilidad se gestionaron de la siguiente manera:

- **Almacenamiento en S3**: Los datos limpios y transformados se almacenaron en **Amazon S3**, en un bucket específico para el proyecto (`sagemaker-fossa`). Esto permitió un acceso rápido y seguro a los datos desde **AWS SageMaker**.
- **Disponibilidad para el modelado**: Los datos se cargaron directamente en **SageMaker** para el entrenamiento y evaluación del modelo. Se utilizó el formato **CSV** para garantizar la compatibilidad con las herramientas de machine learning.

**Herramientas utilizadas**:
- **Amazon S3**: Para el almacenamiento seguro y escalable de los datos.
- **AWS SageMaker**: Para el acceso y procesamiento de los datos durante el modelado.

---

### **3. Plan de Monitoreo del Pipeline**
Para garantizar la calidad y consistencia de los datos a lo largo del tiempo, se implementó un plan de monitoreo del pipeline. Este plan incluyó las siguientes acciones:

- **Monitoreo de la ingesta de datos**:
  - Verificación de la integridad de los datos: Se implementaron checks para asegurar que los datos se cargaran correctamente desde las fuentes externas (`dolar.csv` y `clima.csv`) y que no hubiera pérdida de información.
  - Detección de valores nulos: Se monitorearon las columnas clave (`Raza`, `Marca`, `Peso`) para identificar y corregir valores nulos en tiempo real.

- **Monitoreo de la transformación de datos**:
  - Validación de transformaciones: Se verificó que las transformaciones aplicadas (imputación de valores nulos, eliminación de outliers, agrupación de categorías) se ejecutaran correctamente.
  - Auditoría de datos: Se realizaron revisiones periódicas para asegurar que los datos transformados cumplieran con los estándares de calidad requeridos.

- **Monitoreo del almacenamiento y disponibilidad**:
  - Disponibilidad de datos: Se implementaron alertas para detectar fallos en la carga de datos en **Amazon S3**.
  - Acceso a los datos: Se monitoreó el acceso a los datos desde **SageMaker** para asegurar que estuvieran disponibles durante el entrenamiento y evaluación del modelo.

**Herramientas utilizadas**:
- **AWS CloudWatch**: Para el monitoreo y alertas en tiempo real del pipeline de datos.
- **AWS Glue DataBrew**: Para la validación y auditoría de la calidad de los datos.

---

### **4. Resultados del Pipeline**
El pipeline de datos permitió obtener un dataset limpio y enriquecido, listo para el modelado. Los principales resultados incluyen:

- **Datos limpios**: Se eliminaron valores nulos y outliers, y se imputaron datos faltantes en variables clave como `Raza`, `Marca`, `Peso`, y `Precio_Kilo`.
- **Datos enriquecidos**: Se integraron datos externos como el tipo de cambio del dólar y variables climáticas, lo que mejoró la capacidad predictiva del modelo.
- **Dataset final**: El dataset final incluyó variables como `Fecha`, `Raza`, `Marca`, `Peso`, `Precio_Kilo`, `Dolar`, `Temperatura_Minima`, y `Precipitacion`, listas para ser utilizadas en el entrenamiento del modelo.

---

### **5. Lecciones Aprendidas**
- **Importancia de la calidad de los datos**: La limpieza y transformación de datos fueron fundamentales para mejorar el rendimiento del modelo.
- **Integración de datos externos**: La incorporación de datos como el tipo de cambio del dólar y las variables climáticas demostró ser clave para enriquecer el dataset y mejorar las predicciones.
- **Monitoreo continuo**: La implementación de un plan de monitoreo permitió garantizar la calidad y consistencia de los datos a lo largo del tiempo.

---

Este diseño de pipeline de datos fue esencial para alcanzar los objetivos del proyecto, logrando un **RMSE** de **159.97** y un **R²** de **0.84** en el modelo final.

