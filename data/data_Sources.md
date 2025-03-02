# 📂 Fuentes de Datos

## Descripción
Este documento detalla las fuentes de datos utilizadas en el proyecto de predicción de precios de ganado, incluyendo su origen, formato y propósito dentro del flujo de trabajo.

## 1. Fuentes de Datos Utilizadas
### 📌 Datos de Precios de Ganado
- **Origen:** Registros históricos de transacciones en mercados ganaderos.
- **Formato:** CSV, Excel.
- **Ubicación:** `data/raw/precios_ganado_original.csv`.
- **Uso:** Base principal para entrenar el modelo de predicción de precios.

### 📌 Datos Climáticos
- **Origen:** API de servicios meteorológicos o registros históricos.
- **Formato:** JSON, CSV.
- **Ubicación:** `data/raw/clima_historico_raw.json`.
- **Uso:** Evaluar el impacto del clima en la variabilidad de precios.

### 📌 Datos de Demanda de Mercado
- **Origen:** Reportes económicos del sector agropecuario.
- **Formato:** Excel, PDF (convertido a CSV).
- **Ubicación:** `data/raw/transacciones_mercado.xlsx`.
- **Uso:** Incorporación de tendencias de mercado en el modelo.

## 2. Procesamiento y Almacenamiento
### 📌 Datos Procesados
- Los datos crudos se limpian, normalizan y almacenan en `data/processed/`.
- Se eliminan valores atípicos y se imputan valores nulos.

### 📌 Datos de Validación
- Se separa un conjunto de datos en `data/validation/` para evaluar el modelo.
- No se usan en el entrenamiento para evitar sesgo.


