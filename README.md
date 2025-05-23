# **🚀NASA Turbofan Jet Engine**
# Predicción de Vida Útil Restante (RUL) en Motores Turbofan

## Descripción del Proyecto

Este repositorio contiene un proyecto de Machine Learning centrado en la predicción de la **Vida Útil Restante (Remaining Useful Life - RUL)** de motores turbofan. El objetivo es estimar cuántos ciclos operativos le quedan a un motor antes de una falla funcional, utilizando datos de sensores operativos. Este tipo de predicción es crucial para el mantenimiento predictivo, permitiendo optimizar los tiempos de servicio y reducir costos operativos.

El análisis se realiza sobre el dataset **FD001** de la serie CMAPSS (Commercial Modular Aero-Propulsion System Simulation) de la NASA, un benchmark estándar en el campo del pronóstico de salud de sistemas.

## Contenido del Repositorio

-   `NASA 0001.ipynb` : Contiene el notebook de Jupyter con el análisis exploratorio de datos (EDA), preprocesamiento, entrenamiento de modelos, evaluación y visualización. 
-   `train_FD001.txt`, `test_FD001.txt` y `RUL_FD001` : Son los datasets del proyecto. 
-   `Damage Propagation Modeling.pdf`: El paper original de la NASA que describe el dataset CMAPSS y sus aplicaciones.
      
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

# _Remaining Useful Life (RUL) Prediction for Turbofan Engines_

## _Project Description_

_This repository contains a Machine Learning project focused on predicting the **Remaining Useful Life (RUL)** of turbofan engines. The objective is to estimate how many operational cycles an engine has left before a functional failure, using operational sensor data. This type of prediction is crucial for predictive maintenance, enabling optimization of service times and reduction of operational costs._

_The analysis is performed on the **FD001** dataset from NASA's CMAPSS (Commercial Modular Aero-Propulsion System Simulation) series, a standard benchmark in the field of system health prognostics._

## _Repository Contents_

- _`NASA 0001.ipynb`_: _Contains the Jupyter notebook with exploratory data analysis (EDA), preprocessing, model training, evaluation, and visualization._
- _`train_FD001.txt`, `test_FD001.txt`, and `RUL_FD001`_: _These are the project datasets._
- _`Damage Propagation Modeling.pdf`_: _The original NASA paper describing the CMAPSS dataset and its applications._

## _Models Evaluated_

_A diverse set of Machine Learning models were evaluated, including:_

- _Linear Regression_
- _K-Nearest Neighbors (KNN)_
- _Random Forest_
- _Gradient Boosting_
- _XGBoost_
- _LightGBM_

## _Key Conclusions_

_The analysis revealed important insights into the models' performance in RUL prediction:_

- _**Predominant Overfitting:** Models such as **Random Forest and LightGBM** showed significant overfitting. Despite their high training performance, they exhibited a sharp drop in accuracy on the test set (R² ≈ 0.32-0.34)._
- _**Potential of Boosting Models:** **Gradient Boosting and XGBoost** demonstrated the best initial performance on the test set (R² ≈ 0.37-0.38), with visually closer predictions to actual values. This positions them as the most promising candidates for optimization._
- _**Challenge with High RULs:** A consistent observation is the increased difficulty in accurately predicting high RULs (engines in early/healthy phases of their lifespan), a common challenge in this type of problem._
- _**Distribution Disparity:** The actual RUL distribution differs between the training set (more concentrated at low RULs) and the test set (a higher proportion of high RULs), which influences model behavior._

## _Next Steps_

_To improve model accuracy and generalization capability, the following steps are crucial:_

1. _Hyperparameter Tuning: Optimize boosting models (Gradient Boosting, XGBoost)._
2. _Advanced Feature Engineering: Develop new features from sensor data to enhance the degradation signal._
3. _Neural Network Analysis: Apply LSTM models to leverage their capability with sequential data._
