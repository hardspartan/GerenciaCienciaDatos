# 🔎 Evaluación de Modelos

## Descripción
Esta sección incluye las métricas de desempeño de los modelos utilizados, un análisis comparativo y las pruebas y validaciones realizadas. Además, se justifica la elección del modelo final.

## Pruebas y Validaciones

### 1. **División de Datos**
- Se dividió el dataset en conjuntos de entrenamiento (80%) y validación (20%).
- Se utilizó **train_test_split** con un `random_state=42` para garantizar reproducibilidad.

### 2. **Escalado de Variables**
- Se aplicó **StandardScaler** para normalizar las variables numéricas, mejorando la convergencia del modelo.

### 3. **Validación Cruzada**
- Se realizó una validación cruzada con **5 folds** para evaluar la estabilidad del modelo.
- El modelo mostró un **RMSE promedio de 162.3** y un **R² promedio de 0.83** en los folds.

---

## Comparación entre Modelos

| **Modelo**         | **RMSE** | **R²**  | **Tiempo de Entrenamiento** | **Observaciones**                     |
|---------------------|----------|---------|-----------------------------|---------------------------------------|
| **Baseline**        | 187.59   | 0.78    | 2.5 minutos                 | Modelo inicial con hiperparámetros por defecto. |
| **XGBoost Optimizado** | 159.97   | 0.84    | 5 minutos                   | Mejor rendimiento, mayor precisión y estabilidad. |

---

## Justificación de Elección

El modelo **XGBoost Optimizado** fue seleccionado debido a:
1. **Mejor precisión**: Redujo el RMSE en un 14.7% y aumentó el R² en un 7.7% en comparación con el modelo inicial.
2. **Estabilidad**: Mostró un rendimiento consistente en la validación cruzada, con un RMSE promedio de 162.3.