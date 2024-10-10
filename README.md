# GE-Stock-Price-Movement-Prediction

## Introduction
This report presents a quantitative analysis of stock price movement predictions for General Electric (GE) using various machine learning models. The objective is to assess model performance in predicting short-term price movements and to identify the model most suitable for forecasting stock trends. Given the volatility and complexity of stock prices, this analysis uses a systematic approach to compare model accuracy, F1 scores, precision, and recall. By leveraging historical stock data, this study aims to provide a reliable predictive framework to inform trading strategies.

## Data Overview
The dataset comprises 55,559 records with features capturing transaction details, such as trading time, trading price, waiting times between trades, and stock movement indicators. The target variable, Stock Movement, categorizes price trends into three classes:

Flat: No significant movement
Gain: Upward movement
Loss: Downward movement
Data preprocessing steps included addressing imbalances, feature scaling, and encoding categorical data.

## Data Preprocessing
To prepare the data for model training:

Class Imbalance: Since the “Flat” class dominates, the Synthetic Minority Over-sampling Technique (SMOTE) was applied to balance the classes.
Feature Scaling: Features were standardized using StandardScaler to improve model interpretability and convergence.
Label Encoding: Stock movement classes were numerically encoded for compatibility with machine learning models.
Model Comparison and Performance Analysis
Three machine learning models—Logistic Regression, Support Vector Classifier (SVC), and Decision Tree Classifier—were evaluated. Each model underwent hyperparameter tuning and was assessed on accuracy, F1 scores, and micro-averaged precision and recall metrics.

## 1. Logistic Regression
Parameters: Tuned with GridSearchCV, optimizing for C=1e-05, penalty=l2, and solver=saga.
Performance:
Accuracy: 36.9%
F1 Score: 0.333
Precision and Recall: Both scored 0.37.
Challenges: The model exhibited limited performance due to its inability to capture non-linear relationships in stock data, resulting in lower F1 scores, especially for the “Loss” class.
## 2. Support Vector Classifier (SVC)
Parameters: Default parameters were applied, given SVC’s efficacy with basic configurations.
Performance:
Accuracy: 39.0%
F1 Score: 0.394
Precision and Recall: Both metrics achieved 0.39.
Observation: SVC outperformed Logistic Regression but required significant computational time, impacting scalability. The model showed modest improvement in capturing stock movement trends but still lagged in handling complex price patterns.
## 3. Decision Tree Classifier
Parameters: Optimized using GridSearchCV with best parameters as criterion=gini, max_features=log2, min_samples_split=2, and splitter=random.
Performance:
Accuracy: 50.0%
F1 Score: 0.487
Precision and Recall: Both metrics achieved 0.50.
Key Insights: The Decision Tree Classifier demonstrated the highest performance, successfully capturing complex patterns in the stock data and achieving the best F1 score and accuracy among all models.

<img width="563" alt="image" src="https://github.com/user-attachments/assets/45b276d9-14e6-4fdf-a099-5c99fa85f7e7">

## Conclusion:
The Decision Tree Classifier outperformed both Logistic Regression and SVC, achieving the highest F1 score and accuracy. Due to its capability to model non-linear relationships in stock data, the Decision Tree model is selected as the best-performing algorithm for predicting GE stock price movements.

## Recommendations
Model Enhancement with Ensemble Techniques: The Decision Tree model could be further improved by implementing ensemble methods such as Random Forest or Gradient Boosting, which may enhance prediction accuracy and reduce overfitting.

Expanded Feature Engineering: Additional features, such as market indicators, trading volume, and historical trends, could improve model robustness by providing more context around stock price movements.

Real-Time Model Monitoring: Given the dynamic nature of stock prices, regularly retraining and updating the model with new data is essential to maintain prediction accuracy and adjust to market changes.

Resource Optimization: While Decision Trees performed best, they can be computationally expensive as they grow in complexity. Optimizing the tree depth and node splits will help manage computational costs, especially in a live trading environment.
