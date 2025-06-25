# Reto Bankaya – Modelado de Riesgo Crediticio

Este proyecto fue desarrollado como parte de un desafío de ciencia de datos enfocado en la construcción de un modelo de riesgo crediticio para la empresa Bankaya. El objetivo fue clasificar a los clientes según su probabilidad de incumplimiento en el pago de un préstamo, y asignar tasas de interés individualizadas con base en dicha probabilidad.

## Objetivo

Desarrollar un modelo predictivo de riesgo crediticio que permita distinguir entre clientes con buen y mal comportamiento financiero. A partir de datos internos de solicitudes de crédito y datos externos de historial crediticio, se busca generar un score de riesgo que optimice la toma de decisiones en la aprobación y pricing de préstamos.

## Metodología

El proceso general consistió en las siguientes etapas:

1. **Análisis y limpieza de datos**  
   Tratamiento de valores faltantes, codificación de variables y transformación de campos numéricos y de fecha.

2. **Análisis exploratorio de datos**  
   Visualización de distribuciones, detección de desbalanceo en la variable objetivo, identificación de variables relevantes y creación de categorías interpretativas de riesgo.

3. **Integración de datos externos**  
   Agregación del historial crediticio por cliente y generación de nuevas variables basadas en comportamiento externo: uso de crédito, retrasos, frecuencia de pagos, etc.

4. **Entrenamiento de modelos**  
   Se compararon múltiples algoritmos: regresión logística, árbol de decisión, random forest, red neuronal y XGBoost. Se aplicó balanceo de clases con ROSE.

5. **Evaluación y selección de modelo**  
   La selección se basó en métricas de clasificación como recall, F1-score, accuracy y Kappa, priorizando el recall debido a la naturaleza del problema.

6. **Asignación de tasas de interés dinámicas**  
   Utilizando el score de riesgo generado por el modelo final, se implementó un sistema de tasas que varía del 10% al 50%, proporcional a la probabilidad estimada de incumplimiento.

## Resultados

- El modelo XGBoost fue seleccionado como el mejor, alcanzando un recall del 100% para la clase positiva (clientes con mal comportamiento).
- La variable `max_days_late` resultó ser el predictor más significativo.
- La integración de información externa contribuyó significativamente a mejorar la precisión del modelo.
- Se generó un sistema de tasas de interés personalizadas, alineadas con el riesgo crediticio estimado de cada cliente.

## Estructura del Repositorio

├── index.html # Página HTML para GitHub Pages
├── Reto Bankaya.pdf # Reporte completo del análisis y modelado
├── README.md # Este archivo
├── /src Reto_ML.rmd Código fuente en R
└── /final_bankaya_risk_scores_and_rates.csv # Base de datos con las tasas y scores asignados según el id

## Visualización del Proyecto

La presentación interactiva del proyecto puede consultarse en el siguiente enlace:

[https://cwallss.github.io/Reto-Bankaya/](https://cwallss.github.io/Reto-Bankaya/)

## Requisitos (opcional para reproducir el análisis)

- R ≥ 4.2
- Paquetes: `tidyverse`, `randomForest`, `xgboost`, `caret`, `ROSE`, `nnet`, `ggplot2`, entre otros.

## Consideraciones

Los archivos de datos (`main_dataset.parquet` y `credit_reports.parquet`) no están incluidos por razones de confidencialidad. Este repositorio muestra el proceso técnico, el análisis y los resultados del modelo de riesgo crediticio propuesto.


