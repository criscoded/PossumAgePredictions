# Possum Age Prediction: A Comparative Regression Analysis
A comprehensive Machine Learning project focused on ecological predictive modeling. This repository evaluates multiple regression techniques to accurately predict the age of mountain brushtail possums based on various morphological measurements.

# Project Goals

The primary objective was to determine which regression architecture provides the highest predictive accuracy for ecological datasets, where data can often be noisy or limited in scale.

# Data Engineering & Features

The dataset includes several morphological descriptors used as features for the models:

* Target Variable: Age (Years)

* Predictor Variables: Head length, skull width, total length, tail length, and other physiological metrics

* Preprocessing:

  - Data Cleaning: Handling missing values and ensuring feature consistency

  - Feature Scaling: Standardizing numerical features to optimize model convergence

  - Categorical Encoding: Converting non-numeric ecological data for model compatibility

# Evaluated Models

To find the optimal predictor, this project implements and compares several regression strategies:

* Linear Regression: Establishing a baseline for relationship linearity

* Decision Tree Regressors: Exploring non-linear decision boundaries

* Random Forest / Ensemble Methods: Reducing variance and improving generalization through bagging and boosting techniques

* Regularization: Mitigating overfitting and identifying critical features through coefficient shrinkage

# Technical Stack

* Language: Python

* Environment: Jupyter Notebook

* Key Libraries:
  - Scikit-learn: Core library for model training, splitting, and evaluation

  - Pandas & NumPy: For robust data manipulation and mathematical operations

  - Seaborn & Matplotlib: For Exploratory Data Analysis (EDA) and model performance visualization

# Performance Metrics

Models were evaluated using industry-standard regression metrics to ensure statistical significance:

* Mean Absolute Error (MAE): Measuring average magnitude of errors

* Root Mean Squared Error (RMSE): Penalizing larger prediction gaps

* $R^2$: Quantifying the proportion of variance captured by the models

# Why this matters

Ecological modeling often relies on non-invasive methods to determine the age of wildlife. By developing an accurate regression pipeline, this project demonstrates how Machine Learning can assist field biologists in gathering vital demographic data without the need for invasive testing.

# Results & Model Comparison

After rigorous training and cross-validation, the models were compared to identify the most reliable predictor for ecological data

| Scaler          | Model                     | MSE      | MAE      | R2        |
|-----------------|--------------------------|----------|----------|-----------|
| StandardScaler | LinearRegression         | 3.176860 | 1.401766 | 0.194123  |
| StandardScaler | RandomForestRegressor    | 0.085574 | 0.140238 | 0.978292  |
| StandardScaler | GradientBoostingRegressor| 0.131205 | 0.267968 | 0.966717  |
| StandardScaler | SVR                      | 1.297671 | 0.687953 | 0.670818  |
| StandardScaler | XGBRegressor             | 0.218590 | 0.331351 | 0.944550  |
| RobustScaler   | LinearRegression         | 3.176860 | 1.401766 | 0.194123  |
| RobustScaler   | RandomForestRegressor    | 0.086988 | 0.141032 | 0.977934  |
| RobustScaler   | GradientBoostingRegressor| 0.132701 | 0.268707 | 0.966338  |
| RobustScaler   | SVR                      | 1.255305 | 0.684498 | 0.681565  |
| RobustScaler   | XGBRegressor             | 0.218590 | 0.331351 | 0.944550  |
| None            | LinearRegression         | 3.176860 | 1.401766 | 0.194123  |
| None            | RandomForestRegressor    | 0.086426 | 0.140397 | 0.978076  |
| None            | GradientBoostingRegressor| 0.131205 | 0.267968 | 0.966717  |
| None            | SVR                      | 3.955394 | 1.558679 | -0.003369 |
| None            | XGBRegressor             | 0.218590 | 0.331351 | 0.944550  |

# Key Findings:

* Feature Importance: Analysis revealed that specific morphological traits, such as skull width and total length, had a higher correlation with age than other variables

* Model Generalization: Ensemble methods (Random Forest) provided a significant reduction in RMSE compared to the baseline Linear Regression, suggesting complex, non-linear relationships within the biological data

# Conclusion

## The Small Dataset Challenge

Initial modeling on the original dataset demonstrated the significant impact of data volume on predictive accuracy. Through rigorous testing of both simple and ensemble models, several key behaviors were identified:

* Model Resilience: Random Forest consistently outperformed the competition across all scaling methods, proving its robustness in handling high-variance biological data

* Sensitivity to Variance: Linear Regression exhibited a tendency to overfit toward mean values, while SVR struggled to maintain a flexible decision boundary, leading to the project's baseline for minimum performance

* Algorithm Constraints: In the presence of limited data, advanced boosting models were unable to find significant advantages over simpler ensemble methods, establishing a "performance ceiling" for the initial dataset

## Impact of Data Augmentation

To explore the potential of these models, a synthetic data expansion was implemented to simulate a larger ecological study.

* Model Scalability: With increased data volume, advanced models (Random Forest and Gradient Boosting) "stretched their legs," showing a dramatic increase in predictive accuracy ($R^2$ scores)

* Linear Limitations: The experiment confirmed that Linear Regression's inherent structure is fundamentally ill-suited for the non-linear nature of age progression in this species

* Predictive Success: While initial results were limited, the scaled environment successfully yielded models capable of accurate age prediction, validating the use of Ensemble Learning for this ecological application

## Future Considerations

While crude synthetic generation provided a proof-of-concept, future iterations could leverage more sophisticated generative techniques such as Gaussian Mixture Models (GMMs) or TensorFlow-based GANs to create high-fidelity, biologically accurate synthetic populations.
