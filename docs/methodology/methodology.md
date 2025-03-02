# 📜 Justificación de la Metodología

## Descripción
Este documento describe la metodología seleccionada para el proyecto de predicción de precios de ganado, cuyo objetivo principal es mejorar la precisión del modelo actual reduciendo el **RMSE (Root Mean Squared Error)** y aumentando el **R² (Coeficiente de Determinación)**. Se comparan metodologías aplicables y se justifica la elección de **CRISP-DM** como marco de trabajo, dada su flexibilidad, enfoque iterativo y adaptabilidad a entornos de nube como **AWS SageMaker**.

---

## Comparación de Metodologías Aplicables
A continuación, se comparan tres metodologías comúnmente utilizadas en proyectos de ciencia de datos:

| **Metodología** | **¿De qué trata?**                                                                 | **Pros**                                                                 | **Contras**                                                                 |
|-----------------|------------------------------------------------------------------------------------|--------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| **CRISP-DM**    | Un enfoque estándar para proyectos de minería de datos que divide el proceso en seis fases bien definidas. | ✅ Se puede aplicar en cualquier industria.<br>✅ Iterativo, lo que permite mejoras continuas.<br>✅ Tiene un flujo estructurado fácil de seguir. | ❌ No detalla la implementación en la nube.<br>❌ Puede requerir pasos adicionales para llevar modelos a producción. |
| **KDD**         | Se enfoca en la extracción de conocimiento útil desde grandes volúmenes de datos.   | ✅ Muy útil en la exploración y limpieza de datos.<br>✅ Ayuda a encontrar patrones ocultos en los datos. | ❌ No explica cómo poner modelos en producción.<br>❌ Menos enfocado en mejorar modelos de machine learning. |
| **TDSP**        | Un enfoque más moderno creado por Microsoft, diseñado para proyectos colaborativos y la implementación en la nube. | ✅ Optimizado para entornos de nube como AWS y Azure.<br>✅ Fomenta el trabajo en equipo y la automatización.<br>✅ Pensado para modelos en producción. | ❌ Puede ser más técnico y requerir más conocimiento.<br>❌ Está más alineado con Azure, aunque se puede adaptar a AWS. |

---

## Justificación de la Elección de la Metodología CRISP-DM
Para el desarrollo del proyecto de predicción de precios de ganado, se ha seleccionado la metodología **CRISP-DM (Cross Industry Standard Process for Data Mining)** como el enfoque principal. Esta decisión se basa en las siguientes razones clave, que se alinean con los objetivos y el alcance del proyecto:

### 1. **Alineación con los Objetivos del Proyecto**
El objetivo principal es mejorar la precisión del modelo de predicción, reduciendo el **RMSE** y aumentando el **R²**. CRISP-DM es ideal para este propósito debido a su enfoque iterativo y sus fases bien definidas, que permiten mejorar continuamente el modelo a través de ciclos de enriquecimiento de datos, análisis y reentrenamiento.

- **Enfoque iterativo**: Permite realizar múltiples ciclos de mejora, esencial para alcanzar la precisión deseada.
- **Fases bien definidas**: Las seis fases de CRISP-DM (comprensión del negocio, comprensión de los datos, preparación de los datos, modelado, evaluación y despliegue) aseguran que no se omitan pasos críticos.

### 2. **Flexibilidad y Adaptabilidad a AWS**
Aunque CRISP-DM no está ligado a una plataforma específica, se adapta fácilmente a entornos de nube como **AWS**. Las herramientas de AWS (SageMaker, Glue, S3) pueden integrarse sin problemas en las fases de CRISP-DM, lo que permite aprovechar al máximo las capacidades de la nube.

- **Integración con AWS**: Por ejemplo, la preparación de datos puede realizarse con **AWS Glue**, el modelado con **SageMaker**, y el despliegue del endpoint también con SageMaker.

### 3. **Enfoque en la Calidad de los Datos**
Uno de los desafíos clave es mejorar la calidad de los datos para aumentar la precisión del modelo. CRISP-DM pone un fuerte énfasis en la comprensión y preparación de los datos, lo que es crucial para identificar y corregir problemas como valores atípicos, datos faltantes o inconsistentes.

- **Enriquecimiento de datos**: En el script **Analisis Final fossa.ipynb**, se realizó la limpieza de datos, imputando valores nulos en columnas como **Raza** y **Marca**, y eliminando outliers en **Precio_Kilo** utilizando el rango intercuartílico (IQR). Además, se integraron datos externos como el tipo de cambio del dólar (**dolar.csv**) y datos climáticos (**clima.csv**), lo que permitió mejorar la calidad del dataset.

### 4. **Evaluación Continua y Mejora del Modelo**
CRISP-DM incluye una fase de evaluación que permite medir el rendimiento del modelo en cada iteración. Esto es clave para monitorear métricas como el **RMSE** y asegurar que el modelo esté mejorando progresivamente.

- **Métricas clave**: En el script **Analisis Final fossa.ipynb**, se evaluó el modelo final utilizando **RMSE** y **R²**. El modelo inicial tenía un **RMSE** de [Inserte valor aquí], y después de la optimización, se logró reducir a **159.97**, lo que representa una mejora significativa. Además, el **R²** aumentó a **0.84**, lo que indica una mayor capacidad predictiva del modelo.

### 5. **Escalabilidad y Mantenimiento**
CRISP-DM no solo facilita la implementación del modelo, sino también su escalabilidad y mantenimiento a largo plazo.

- **Escalabilidad**: En el script **Analisis Final fossa.ipynb**, se utilizó **AWS SageMaker** para entrenar y desplegar el modelo, lo que permite incorporar nuevos datos y reentrenar el modelo de manera continua.
- **Mantenimiento**: La fase de despliegue incluye la implementación del modelo en producción y considera la necesidad de monitoreo y actualización continua.

### 6. **Comparación con Otras Metodologías**
Aunque **TDSP** y **KDD** son metodologías válidas, CRISP-DM ofrece ventajas específicas para este proyecto:

- **TDSP**: Aunque está optimizado para la nube, está más alineado con **Azure**, y este proyecto se desarrolla en **AWS**. Además, puede ser más técnico y requerir un mayor conocimiento.
- **KDD**: Se enfoca en la extracción de conocimiento, pero no proporciona una guía clara para la implementación en producción, lo que es un requisito clave en este proyecto.

