# Predicción de brotes de dengue en regiones del Perú utilizando modelos de aprendizaje automático y datos de vigilancia epidemiológica

**Autor:** Jhordy Edinson Burga Domínguez  
**Programa:** Maestría en Data Science  
**Institución:** Universidad Continental  
**Año:** 2026

---

## Resumen del Proyecto

Este repositorio contiene el código fuente y los archivos complementarios desarrollados para la tesis de maestría orientada a **predecir la incidencia de brotes de dengue en el Perú** mediante técnicas de machine learning y análisis de series temporales. El estudio utiliza los datos abiertos de vigilancia epidemiológica del Centro Nacional de Epidemiología, Prevención y Control de Enfermedades (CDC Perú) para el período comprendido entre los años 2000 y 2024.

El objetivo principal es comparar el desempeño de seis modelos predictivos (ARIMA, SARIMA, Prophet, Random Forest, XGBoost y LSTM) y proponer un sistema de alerta temprana que permita a las autoridades sanitarias anticipar la ocurrencia de brotes con al menos cuatro semanas de anticipación.

---

## Objetivos Específicos y Estructura del Análisis

El desarrollo de la investigación se articula en torno a tres objetivos específicos, los cuales se ejecutan de forma secuencial en el notebook principal:

| Objetivo | Descripción | Archivos Relevantes |
| :--- | :--- | :--- |
| **OE1** | Caracterizar los patrones temporales, geográficos y demográficos de la incidencia del dengue en las regiones del Perú durante el período 2000-2024. | `Trabajo_Dengue.ipynb` |
| **OE2** | Desarrollar y evaluar modelos predictivos basados en técnicas de series temporales y aprendizaje automático para anticipar la incidencia del dengue. | `Trabajo_Dengue.ipynb` |
| **OE3** | Establecer criterios de alerta temprana a partir de las predicciones del modelo seleccionado, para identificar regiones con alta probabilidad de brote. | `Trabajo_Dengue.ipynb` |

---

## Archivos Clave del Repositorio

| Archivo | Descripción | Uso Principal |
| :--- | :--- | :--- |
| **`Trabajo_Dengue.ipynb`** | **Código fuente principal.** Notebook de Python desarrollado en Google Colab que contiene el preprocesamiento de datos, el análisis exploratorio (EDA), el entrenamiento y optimización de los seis modelos predictivos, la evaluación de métricas y la generación de las gráficas presentadas en el Capítulo V de la tesis. | Reproducción total del análisis y los resultados. |

---

## Fuente de Datos

La base de datos original en formato `.csv` supera los 100 MB, por lo que no se encuentra alojada directamente en este repositorio. El dataset utilizado corresponde a la vigilancia epidemiológica de dengue publicada por el Ministerio de Salud a través de la Plataforma Nacional de Datos Abiertos del Perú.

*   **Enlace de la fuente oficial:** [https://www.datosabiertos.gob.pe/dataset/vigilancia-epidemiológica-de-dengue](https://www.datosabiertos.gob.pe/dataset/vigilancia-epidemiológica-de-dengue)
*   **Copia de respaldo (Google Drive):** [https://drive.google.com/file/d/1Blh_8lrxCa6R8k8tu_ygW0beEtyTXs6/view?usp=sharing](https://drive.google.com/file/d/1Blh_8lrxCa6R8k8tu_ygW0beEtyTXs6/view?usp=sharing)

**Nota para la ejecución:** Para que el notebook funcione correctamente, se debe descargar el archivo `.csv` y cargarlo manualmente en la sesión de Google Colab, o bien, colocarlo en la misma ruta de trabajo del proyecto.

---

## Requisitos de Ejecución

El análisis fue desarrollado en **Google Colab** utilizando **Python 3** y las siguientes librerías especializadas:

*   Manipulación de datos: `pandas`, `numpy`
*   Visualización: `matplotlib`, `seaborn`
*   Modelos estadísticos: `statsmodels` (ARIMA, SARIMA)
*   Modelos de machine learning: `scikit-learn` (Random Forest), `xgboost`
*   Modelos de series temporales: `prophet`
*   Modelos de deep learning: `tensorflow`, `keras` (LSTM)
*   Evaluación: `sklearn.metrics` (MAPE, RMSE, MAE)

---

## Metodología y Resultados Principales

El estudio siguió un enfoque cuantitativo con un diseño no experimental y longitudinal. La serie temporal fue dividida en un conjunto de entrenamiento (2000-2022) y un conjunto de prueba (2023-2024), este último seleccionado por corresponder al brote epidémico más severo registrado en el país, lo que permitió someter a los modelos a un escenario real de estrés.

Los resultados evidenciaron que los modelos estadísticos tradicionales presentaron dificultades para capturar la magnitud de los brotes, con errores porcentuales absolutos medios (MAPE) superiores al 60%. En contraste, el modelo de deep learning **LSTM** alcanzó el mejor desempeño, con un MAPE de 18.66%, posicionándose como la herramienta más precisa para anticipar la incidencia del dengue a cuatro semanas vista. A partir de este hallazgo, se propuso un sistema de alerta temprana con cuatro niveles (verde, amarillo, naranja y rojo) basado en percentiles históricos e intervalos de confianza, diseñado para apoyar la toma de decisiones en salud pública.
