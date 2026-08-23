# Riesgo clínico para una red de clínicas

Proyecto de Primer Corte — Aprendizaje de Máquina No Supervisado
Universidad de La Sabana, 2026-II

## Problema de negocio

Actúo como analista de datos para una red de clínicas cardiológicas que quiere
entender qué variables clínicas están más asociadas con la presencia de
enfermedad cardíaca, y cómo debería "actualizar" su sospecha diagnóstica a
medida que llegan resultados de distintas pruebas.

## Dataset

**Heart Disease Dataset** (UCI Machine Learning Repository, base de Cleveland).
303 pacientes, 14 variables clínicas (edad, sexo, tipo de dolor de pecho,
colesterol, frecuencia cardíaca máxima, entre otras). Tras eliminar 6 registros
con valores faltantes, el análisis se hizo sobre 297 pacientes.

Fuente: https://archive.ics.uci.edu/dataset/45/heart+disease

## Contenido del notebook

El notebook (`notebooks/Proyecto_C1_Riesgo_clinico_ML.ipynb`) aplica 11 conceptos
probabilísticos y estadísticos al dataset:

1. Probabilidad condicional
2. Teorema de Bayes
3. Verosimilitud / Máxima Verosimilitud (MLE)
4. Distribuciones paramétricas
5. Esperanza y Varianza
6. Independencia y Correlación
7. Prior y Posterior (actualización bayesiana secuencial)
8. Entropía
9. Entropía cruzada
10. Divergencia KL

## Hallazgos principales

- La prevalencia de enfermedad en la muestra es 46.1%. El dolor de pecho
  asintomático y la angina inducida por ejercicio elevan bastante esa
  probabilidad (a 72.5% y 76.3%), mientras que el colesterol por sí solo casi
  no distingue entre pacientes sanos y enfermos.
- La actualización bayesiana secuencial con tres pruebas clínicas lleva el
  posterior de 46.1% a 97.4%, y el resultado final no depende del orden en
  que se evalúen las pruebas.
- La frecuencia cardíaca máxima sí diferencia bien a los dos grupos (139.1 lpm
  en enfermos frente a 158.6 lpm en sanos).
- Un clasificador de regresión logística alcanza 81.3% de exactitud en el
  conjunto de prueba, con una entropía cruzada de 0.384.

## Cómo ejecutar

1. Clonar el repositorio.
2. Instalar dependencias: `pip install numpy pandas scipy matplotlib seaborn scikit-learn`
3. Abrir `notebooks/Proyecto_C1_Riesgo_clinico_ML.ipynb` en Jupyter.
4. Kernel → Restart Kernel and Run All Cells.

## Autor

Sebastián — Universidad de La Sabana
