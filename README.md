# AV_March_2022
Bank Customer Churn Prediction

# Problem Statement: 
Decreasing the customer churn is a key goal for any business. Predicting Customer Churn (also known as Customer Attrition) represents an additional potential revenue source for any business. Higher customer churn leads to loss in revenue and the additional marketing costs involved with replacing those customers with new ones.

In this challenge, as a Data Scientist of a bank you are asked to analyze the past data and predict wether the customer will churn or retain in the next 6 months. This would help the bank to have the right enagagement with customers at the right time.

# Objective:
Build a Machine Learning model to predict whether the customer will churn or not in the next six months.

# Data:
| Variable      | Description                     |
| :------------ |   ------------------:           | 
| `ID`          | Unique Identifier of a row      | 
| `Age`         | Age of the customer             |
| 'Gender'      | Gender of the customer (Male and Female)|
| 'Income'      | Yearly income of the customer            |
| 'Balance'     | Average quarterly balance of the customer|
| 'Vintage'     | No. of years the customer is associated with bank |
| 'Transaction Status' | Weather the customer has done any transaction in the past 3 months or not|
| 'Product Holdings' | No. of product holdings with the bank     |
|'Credit Card' | Weather the customer has a credit card or not  |
| 'Credit Category' | Category of the customer based on the credit score |
| 'Is Churn' | Wheather the customer will churn in the next six months or not|

# My Approach:
In order to solve the problem statement, following mehodolgy is taken.

1. Reading data
2. Exploratory Data Analysis
3. Data preprocessing
4. Feature Engineering
5. Upsampling to address class imbalance
6. Modelling
7. Prediction on the test set.

# Explanation
1. Reading Data - 
      Two csv files are preovided - train and test. The data has 10 features including the target variable. The size of data provided is small.
      
2. Exploratory Data Analysis - 
      On performing EDA, we come to know that, there is class imbalance (76.9% - 23.1%) (0-1). There are no missing values found. The features Age and Balance are the most correlated features in all the features present. There are outliers present in our dataset for three features (Age, Balance and Is_Churn). But these instances can happen in real world, so I decided to keep them as it is.

3. Data preprocessing - 
      Label Encoding is done for categorical features.
      
4. Feature Engineering - 
      Aggregated Features (sum, mean, max etc) and successive aggregates of features Product Holding and Balance (sum, mean, max etc) are taken. The Balance by Income ratio is also created as a new feature.
      
5. Upsampling to address class imbalance -
      Synthetic Minority Oversampling Technique (SMOTE) was applied to the data set to address the class imbalance.
    
6. Modelling -
      A bunch of models were tried on the genereated features. Loigistic Regression, Ridge Classifier, KNN, SVM, Random Forest, Gradient Boosting Classifier and Voting Classifier. Along all these models, Guassian Naive Bayes and Light GBM were also given to the voting classifer. 
      
7. Prediction on the test set - 
      The performance of voting classifer gave best macro F1 score so that was finalised to make predictions on the test data. 
