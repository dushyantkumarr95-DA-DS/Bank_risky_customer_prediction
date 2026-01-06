# Bank Risky Customer Prediction using Machine Learning.


# Project Overview: 

The objective of this project is to predict whether a banking customer poses a high financial risk based on historical data.
In a banking context, misclassifying a high-risk customer as low risk(false negative) can lead to significant financial loss.
And misclassifying a low risk customer as high-risk(false positive) can lead to bad customer experience and churn.

Therefore, this project prioritizes finding the right balance between Recall and Precision over Accuracy for better classification of customers.


# Dataset Description: 
The project uses a dataset of 12000 customers with the following numerical features: 

1)  Customers Demographics  :  Age, Annual income.

2)  Account Information  :  Credit score, Account tenure.

3)  Behavioral Data  :  Monthly transaction count, Average transaction value, Missed payments, Support calls, and Online usage hours.

4)  Target Variable  :  "HighRisk"(Binary output:0 for no, 1 for yes).


## Key Data Insights:

-  The dataset contains  no duplicate rows or missing values.

-  There is target variable class imbalance with a 35:65 ratio(HighRisk Vs Safe).


# Methodology:

1)  Preprocessing  :  Feature and target variable separated by stratified train-test-split(80/20) to preserve class distribution.

2)  Feature Scaling  :  Standardization was applied to ensure Logistic Regression and Neural Network model do not become feature biased.


# Models Implemented:

-  Logistic Regression with balanced class weights.

-  Random Forest Classifier.

-  Neural Network using Keras/Tensorflow.


# Final Model Selection  :  (Random Forest)

After comparing performance metrics,  I recommend "RANDOM FOREST" model for the deployment.

-  Random Forest model achieved recall:0.95 and precision:0.97 missing 41 high-risk customers(False Negative) and flagging 25 safe customers as risky(False Positive).

-  Although the Neural Network achieved the highest recall(0.99) and missed very few high-risk customers(12), it also resulted in a significantly higher number of safe customers being flagged as HighRisk(95), which could negatively impact the customer experience and may cause genuine customer churn.

-  In case of any Lawsuit by customer for being flagged as HighRisk, "Random Forest" can give you "Feature Importance" for arguing whereas in Neural Network it is very difficult to explain on which pattern the customer is flagged as HighRisk.

-  Hence Random Forest Model offers the most practical and interpretable solution for real-world banking risk assessment.

-  Note  ->  Use Neural Network Model only when the cost of false negative is extremely high.
