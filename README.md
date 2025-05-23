# **🚀NASA Turbofan Jet Engine**
# Predicción de Vida Útil Restante (RUL) en Motores Turbofan

## Descripción del Proyecto

Este repositorio contiene un proyecto de Machine Learning centrado en la predicción de la **Vida Útil Restante (Remaining Useful Life - RUL)** de motores turbofan. El objetivo es estimar cuántos ciclos operativos le quedan a un motor antes de una falla funcional, utilizando datos de sensores operativos. Este tipo de predicción es crucial para el mantenimiento predictivo, permitiendo optimizar los tiempos de servicio y reducir costos operativos.

El análisis se realiza sobre el dataset **FD001** de la serie CMAPSS (Commercial Modular Aero-Propulsion System Simulation) de la NASA, un benchmark estándar en el campo del pronóstico de salud de sistemas.

## Contenido del Repositorio

-   `notebooks/`: Contiene los notebooks de Jupyter con el análisis exploratorio de datos (EDA), preprocesamiento, entrenamiento de modelos, evaluación y visualización.
    -   `NASA 0001.ipynb` 
-   `data/`:  `train_FD001.txt`, `test_FD001.txt` y `RUL_FD001`

## Modelos Evaluados

Se evaluó un conjunto diverso de modelos de Machine Learning, incluyendo:

-   Regresión Lineal
-   K-Nearest Neighbors (KNN)
-   Random Forest
-   Gradient Boosting
-   XGBoost
-   LightGBM

## Conclusiones Clave

El análisis reveló insights importantes sobre el rendimiento de los modelos en la predicción del RUL:

-   **Sobreajuste (Overfitting) Predominante:** Modelos como **Random Forest y LightGBM** mostraron un sobreajuste significativo, rindiendo casi perfectamente en entrenamiento, pero cayendo drásticamente en precisión en el conjunto de prueba (R² ≈ 0.32-0.34).
-   **Potencial de los Modelos de Boosting:** **Gradient Boosting y XGBoost** demostraron el mejor rendimiento inicial en el conjunto de prueba (R² ≈ 0.37-0.38), con predicciones visualmente más cercanas a los valores reales. Esto los posiciona como los candidatos más prometedores para una optimización.
-   **Desafío en RULs Altos:** Una observación consistente es la mayor dificultad para predecir con precisión RULs altos (motores en fases iniciales/sanas de su vida útil), un desafío común en este tipo de problemas.
-   **Disparidad en Distribuciones:** La distribución del RUL real difiere entre los conjuntos de entrenamiento (más concentrado en RULs bajos) y prueba (mayor proporción de RULs altos), lo que influye en el comportamiento del modelo.

## Próximos Pasos

Para mejorar la precisión y la capacidad de generalización del modelo, los siguientes pasos son cruciales:

1.  **Ajuste de Hiperparámetros:** Optimizar los modelos de boosting (Gradient Boosting, XGBoost).
2.  **Ingeniería de Características Avanzada:** Desarrollar nuevas características a partir de los datos de los sensores para mejorar la señal de degradación.
3.  **Análisis mediante Redes Neuronales:** Aplicar modelos de LSTM para aprovechar su capacidad en datos secuenciales.

---

# Remaining Useful Life (RUL) Prediction for Turbofan Engines

## Project Description

This repository contains a Machine Learning project focused on predicting the **Remaining Useful Life (RUL)** of turbofan engines. The objective is to estimate how many operational cycles an engine has left before a functional failure, using operational sensor data. This type of prediction is crucial for predictive maintenance, enabling optimization of service times and reduction of operational costs.

The analysis is performed on the **FD001** dataset from NASA's CMAPSS (Commercial Modular Aero-Propulsion System Simulation) series, a standard benchmark in the field of system health prognostics.

## Repository Contents

-   `notebooks/`: Contains Jupyter notebooks with exploratory data analysis (EDA), preprocessing, model training, evaluation, and visualization.
    -   `NASA 0001.ipynb`
-   `data/`: Includes `train_FD001.txt`, `test_FD001.txt`, and `RUL_FD001.txt` (assuming `RUL_FD001` refers to a `.txt` file, please adjust if it's another format).

## Models Evaluated

A diverse set of Machine Learning models were evaluated, including:

-   Linear Regression
-   K-Nearest Neighbors (KNN)
-   Random Forest
-   Gradient Boosting
-   XGBoost
-   LightGBM

## Key Conclusions

The analysis revealed important insights into the models' performance in RUL prediction:

-   **Predominant Overfitting:** Models such as **Random Forest and LightGBM** showed significant overfitting. Despite their high training performance, they exhibited a sharp drop in accuracy on the test set (R² ≈ 0.32-0.34).
-   **Potential of Boosting Models:** **Gradient Boosting and XGBoost** demonstrated the best initial performance on the test set (R² ≈ 0.37-0.38), with visually closer predictions to actual values. This positions them as the most promising candidates for optimization.
-   **Challenge with High RULs:** A consistent observation is the increased difficulty in accurately predicting high RULs (engines in early/healthy phases of their lifespan), a common challenge in this type of problem.
-   **Distribution Disparity:** The actual RUL distribution differs between the training set (more concentrated at low RULs) and the test set (a higher proportion of high RULs), which influences model behavior.

## Next Steps

To improve model accuracy and generalization capability, the following steps are crucial:

1.  **Hyperparameter Tuning:** Optimize boosting models (Gradient Boosting, XGBoost).
2.  **Advanced Feature Engineering:** Develop new features from sensor data to enhance the degradation signal.
3.  **Neural Network Analysis:** Apply LSTM models to leverage their capability with sequential data.
