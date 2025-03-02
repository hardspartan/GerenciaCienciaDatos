# 📊 Resumen Ejecutivo

## Descripción
Este documento resume los hallazgos clave, métricas principales y conclusiones del proyecto de predicción de precios de ganado. Está diseñado para tomadores de decisiones, con un enfoque en el impacto y las recomendaciones estratégicas.

---

## Hallazgos Clave

### 1. **Mejora del Modelo Predictivo**
- **Objetivo inicial**: Reducir el **RMSE (Root Mean Squared Error)** y aumentar el **R² (Coeficiente de Determinación)** del modelo existente.
- **Resultado final**: 
  - **RMSE**: Se redujo de **187.59** (modelo inicial) a **159.97** (modelo optimizado), una mejora del **14.7%**.
  - **R²**: Aumentó de **0.78** (modelo inicial) a **0.84** (modelo optimizado), un incremento del **7.7%**.
- **Impacto**: El modelo mejorado permite predecir el precio del ganado con mayor precisión, lo que ayudará a los ganaderos y compradores a tomar decisiones más informadas.

### 2. **Importancia de las Variables**
- **Variables clave**: Las variables más influyentes en la predicción del precio fueron:
  - **Dolar**: El tipo de cambio del dólar mostró una correlación significativa con el precio del ganado, con un coeficiente de correlación de **0.3685**.
  - **Temperatura_Minima**: Las condiciones climáticas, especialmente la temperatura mínima, influyeron en los precios, con un coeficiente de correlación de **-0.1681**.
  - **Precipitacion**: Los niveles de precipitación también tuvieron un impacto notable en los precios, con un coeficiente de correlación de **0.1192**.
- **Impacto**: Estos hallazgos sugieren que factores externos, como el clima y la economía, son cruciales para la predicción de precios.

### 3. **Calidad de los Datos**
- **Limpieza y enriquecimiento**: 
  - Se imputaron valores nulos en columnas clave: **6.62%** en `Raza`, **2.37%** en `Marca`, y **0.03%** en `Peso`.
  - Se eliminaron **15,555 registros** (aproximadamente **1.6%** del dataset) debido a outliers en `Precio_Kilo`.
  - Se integraron datos externos: **2,162 registros** de datos climáticos y **1,239 registros** de tipo de cambio del dólar.
- **Impacto**: La mejora en la calidad de los datos permitió obtener un modelo más preciso y confiable.

---

## Métricas Principales

| **Métrica**         | **Modelo Inicial** | **Modelo Optimizado** | **Mejora**       |
|----------------------|--------------------|------------------------|------------------|
| **RMSE**            | 187.59             | 159.97                 | Reducción del 14.7% |
| **R²**              | 0.78               | 0.84                   | Aumento del 7.7%   |

---

## Conclusiones y Recomendaciones Estratégicas

### 1. **Conclusiones**
- **Modelo robusto**: El modelo optimizado de **XGBoost** demostró ser altamente efectivo para predecir el precio del ganado, con un **RMSE de 159.97** y un **R² de 0.84**.
- **Factores externos clave**: El tipo de cambio del dólar y las condiciones climáticas son variables críticas que deben ser monitoreadas para mejorar la precisión del modelo.
- **Calidad de datos**: La limpieza y enriquecimiento de los datos fueron fundamentales para alcanzar los objetivos del proyecto.

### 2. **Recomendaciones Estratégicas**
- **Monitoreo continuo**: Implementar un sistema de monitoreo en tiempo real para actualizar el modelo con datos recientes de clima y tipo de cambio.
- **Expansión del dataset**: Incorporar más variables externas, como precios de insumos agrícolas y datos de mercado internacional, para mejorar aún más la precisión del modelo.
- **Capacitación y adopción**: Capacitar a los usuarios finales (ganaderos y compradores) en el uso del modelo para maximizar su impacto en la toma de decisiones.

---

# 📊 Hallazgos Clave

## Descripción
Este documento resume los descubrimientos más relevantes obtenidos durante el análisis de datos, el impacto de estos hallazgos en la toma de decisiones y una comparación con los objetivos iniciales del proyecto.

---

## Principales Insights Identificados

### 1. **Variables más Influyentes**
- **Dolar**: El tipo de cambio del dólar mostró una correlación significativa con el precio del ganado, con un coeficiente de correlación de **0.3685**.
- **Temperatura_Minima**: Las condiciones climáticas, especialmente la temperatura mínima, influyeron en los precios, con un coeficiente de correlación de **-0.1681**.
- **Precipitacion**: Los niveles de precipitación también tuvieron un impacto notable en los precios, con un coeficiente de correlación de **0.1192**.

### 2. **Calidad de los Datos**
- **Limpieza de datos**: 
  - Se imputaron valores nulos en **6.62%** de los registros en `Raza` y **2.37%** en `Marca`.
  - Se eliminaron **15,555 registros** (aproximadamente **1.6%** del dataset) debido a outliers en `Precio_Kilo`.
- **Integración de datos externos**: Se incorporaron **2,162 registros** de datos climáticos y **1,239 registros** de tipo de cambio del dólar.

---

## Impacto de los Hallazgos en la Toma de Decisiones

### 1. **Mejora en la Precisión del Modelo**
- **Impacto**: El modelo mejorado permite a los ganaderos y compradores predecir los precios del ganado con mayor precisión, lo que facilita la planificación financiera y la toma de decisiones estratégicas.

### 2. **Factores Externos Clave**
- **Impacto**: La identificación de variables clave como el tipo de cambio del dólar y las condiciones climáticas permite a los usuarios finales monitorear estos factores y ajustar sus estrategias de compra y venta en consecuencia.

---