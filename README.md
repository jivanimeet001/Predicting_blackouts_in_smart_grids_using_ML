# Predicting Cascading Failures in Smart Grids

## Abstract
While significant advancements have been made in modeling cascading failures in smart grids, a notable observation is the limited integration of machine learning algorithms in many of these projects. This study addresses this gap by applying machine learning techniques to classify cascading faults in smart grids leading to substantial blackouts. Due to the unavailability of real-world cascading failure data, we have devised a synthetic cascading failure simulator framework. This framework generates cascading failure data under various smart grid operating conditions, incorporating critical variables such as the quantity of failed lines, their maximum and minimum capacity, loading level, Load shedding capabilities, and communication uncertainty (capacity estimation error). The dataset encompasses topological parameters for diverse combinations of transmission line failures, including average degree and average distance. Moreover, our approach factors in the probability of human error, which amplifies the risk of cascades during propagation. Subsequently, diverse machine learning techniques are employed to categorize the cascade impact based on the quantity of Load shedding and the number of faulty transmission lines, and the precision of these models is thoroughly evaluated. Furthermore, regression models are employed to forecast the cascade effect. This data-driven methodology offers smart grid design engineers a valuable tool for enhancing grid robustness by promptly classifying cascade failures based on the input smart grid conditions.

## Introduction
Smart grids are complicated systems that require constant maintenance of the demand-supply link between power generation and customer demand. They have a risk of cascade failures even with safeguards in place. When demand and supply suddenly become unbalanced, a minor disruption in the smart grid may have a cascading effect. This study aims to predict cascading failures using machine learning techniques.

## Summary of the Project Objective
- Conduct exploratory data analysis to identify patterns in the data.
- Use regression analysis to determine the impact of cascading failures caused by different initial disturbance circumstances on cascading termination.
- Determine critical and non-critical initial feature values using categorization approaches.
- Compare different machine learning methods and adjust hyperparameters as needed.

## Dataset
Our Cascade Failure Simulation (CFS) framework, created in MATLAB, was utilized to create the simulated dataset of cascading failures. Over seventy thousand cascading failure simulations are included. 17 characteristics and 2 target variables are present in the dataset.

## Model Features
- Level of grid loading power (r)
- Limit of load shedding (θ)
- Estimated capacity error (e)
- Failing lines, installed capacity, Cmax, and Cmin
- Mean distance and mean degree
- Probability of human operator error
- Number of cascade-related failure lines
- Load shed amount

## Data Cleaning
- The dataset has no null values, missing values, or outliers.
- One redundant column was eliminated.
- Columns were renamed for improved comprehension.

## Statistical Analysis
- Histogram analysis
- Correlation analysis
- Collinearity analysis

## Outcomes and Comprehensive Machine Learning Analysis
For regression, algorithms used:
- Linear regression/Ridge/Lasso regression
- Random Forest regression
- Support vector regressor

For classification, algorithms used:
- Logistic regression
- KNN (k nearest neighbour)
- Random forest
- Decision tree
- Support vector machine
- Adaboost

The performance of regression and classification models was evaluated using various metrics.

## Discussion
This study demonstrates that machine learning can be used to forecast cascading failures with a high degree of accuracy. The data-driven methodology presented here offers valuable insights for smart grid design engineers to enhance grid robustness.

## Model Hyperparameters
| Model           | Hyperparameters                                                |
|-----------------|----------------------------------------------------------------|
| Decision tree   | 'criterion': 'entropy', 'min_samples_leaf': 10, 'min_samples_split': 5 |
| KNN             | 'algorithm': 'auto', 'leaf size': 1, 'n_neighbors': 10, 'weights': 'distance' |
| Adaboost        | 'algorithm': 'SAMME.R', 'learning rate': 0.5, 'n_estimators': 200 |
| Random forest   | 'criterion': 'gini', 'min_samples_leaf': 5, 'min_samples_split': 5, 'n_estimators': 50 |
| Logistic regression | C= 10 (penalty = 'l2')                                         |
| SVM             | 'C': 5, 'kernel': ['rbf']                                      |
