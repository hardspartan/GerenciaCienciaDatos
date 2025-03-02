# ⚠️ Evaluación de Riesgos

## **Riesgos Identificados y Estrategias de Mitigación**

### **1. Problemas con la Calidad de los Datos**
- **Impacto**: Datos incompletos o inconsistentes podrían afectar la precisión del modelo.
- **Estrategias de Mitigación**:
  - **Preventivas**:
    - Implementar validaciones automáticas durante la ingesta de datos para detectar valores nulos o inconsistentes.
    - Establecer un protocolo de limpieza de datos que incluya la imputación de valores nulos y la eliminación de outliers.
  - **Reactivas**:
    - Realizar un análisis exploratorio de datos (EDA) para identificar y corregir problemas antes del modelado.
    - Utilizar técnicas de imputación avanzadas (como el promedio móvil o la interpolación) para datos faltantes.

---

### **2. Fallos en la Infraestructura de AWS**
- **Impacto**: Interrupciones en el acceso a los datos o en el entrenamiento del modelo.
- **Estrategias de Mitigación**:
  - **Preventivas**:
    - Configurar redundancia en la infraestructura de AWS, utilizando múltiples regiones o zonas de disponibilidad.
    - Realizar copias de seguridad periódicas de los datos y modelos en un bucket de S3 alternativo.
  - **Reactivas**:
    - Tener un plan de contingencia para migrar a servidores locales o alternativos en caso de fallos en AWS.
    - Monitorear el estado de la infraestructura en tiempo real usando **AWS CloudWatch** para detectar y resolver problemas rápidamente.

---

### **3. Bajo Rendimiento del Modelo**
- **Impacto**: El modelo no alcanza el rendimiento esperado (por ejemplo, no se reduce el RMSE o no se aumenta el R²).
- **Estrategias de Mitigación**:
  - **Preventivas**:
    - Realizar pruebas exhaustivas durante el desarrollo del modelo, ajustando hiperparámetros mediante técnicas como **Grid Search** o **Random Search**.
    - Utilizar validación cruzada para asegurar que el modelo generalice bien a nuevos datos.
  - **Reactivas**:
    - Explorar otros algoritmos de machine learning (por ejemplo, cambiar de **Random Forest** a **XGBoost** o **Gradient Boosting**).
    - Incorporar más datos o características relevantes para mejorar el rendimiento del modelo.

---