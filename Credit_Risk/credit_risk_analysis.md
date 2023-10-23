# Module 12 Report 

## Overview of the Analysis

In this challenge we were given a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers. The purpose of our analysis was to train and test different learning models in order to access it's accuracy in predicting the chances of a given loan being healthy (0) or it being at risk of defaulting (1)

- In order to predict the chances of a loan being healthy or being risky, our dataset gives us vital information around the loan amount, interest rate, income of the borrower, their debt to income ratio and the number of accounts the borrower has along with derogatory marks, (i.e. this could be due to a late payment or other delinquencies attached to the borrower). We're also given the current loan status of each loan that we will use to predict credit worthiness of a borrower.
- After splitting our data into our desired target and label variables, we can see that the amount of loans listed as healthy vs at risk indicates that most of our loans are healthy. With 75036 loans have a loan status of 0 (healthy) while 2500 loans are 1 (at risk)
- The following steps were taken in our analysis.
  1. I separated the given data  and initialized them into x (labels) and y (target) variables. After doing so, I implemented the train_test_split function from the sklearn.model_selection module. Utilizing that function, I was able to split our x and y data into training data, and testing data, with a random_state of 1.
  2. Once our training data and testing data were split, I utilized the Logistic Regression function from the sklearn.linear_model module to fit our learning model to the training data and eventually deriving predicitions from our testing data.
  3. I then used those predictions to evaluate the performance our learning model by finding the accuracy score, confusion matrix and classification report utilizing the same sklearn library with their metrics module.
  4. After understanding the performance of this model, I deployed another learning model, imblearn (or imbalanced learning) to resample our x and y data with the RandomOverSampler function. This is because we noticed with our value_counts that our given data is at an imbalance. Once the data was resampled, I used Logistic Regression again to evaluate the results of our resampled model.

## Results

* Machine Learning Model 1:
  * Accuracy: Our model has a high accuracy of 0.94, which means it correctly classifies approximately 94% of all the loans in our dataset. However, high accuracy can be misleading in imbalanced datasets, so it's essential to consider other metrics.
  * Precision: The precision of our model is approximately 0.87. This means that when our model predicts a loan as "at risk," it's correct about 87% of the time. In other words, the model has a relatively low false positive rate, making it reasonably reliable when it predicts a loan as risky.
  * Recall (Sensitivity): The recall of our model is approximately 0.89. This indicates that our model is capable of capturing 89% of the actual risky loans in the dataset. It has a relatively low false negative rate, meaning it doesn't miss many risky loans.

* Machine Learning Model 2:
  * Accuracy: Our secondary model has an extremely high accuracy of 0.994, which means it correctly classifies approximately 99.4% of all the loans in our dataset. This is a very high accuracy rate, indicating that the model's overall performance is excellent.
  * Precision: The precision of our secondary model is approximately 0.994. This means that when our model predicts a loan as "at risk," it's correct about 99.4% of the time. The model has a very low false positive rate, which suggests it is highly reliable when it predicts a loan as risky.
  * Recall (Sensitivity): The recall of our secondary model is approximately 0.994. This indicates that our model is capturing 99.4% of the actual risky loans in the dataset. It has an extremely low false negative rate, meaning it rarely misses risky loans.

## Summary

Objectively, the secondary model outperforms the primary model in terms of accuracy, precision, and recall. It achieves near-perfect scores for all three metrics, indicating exceptional performance in classifying loans as "healthy" and "at risk." While comparing our results to that of the primary model, we can see the improved performance in our testing, once we derive a balance in our data. 

While the first model did have considerable accuracy and may still be suitable in identifying risky loans, the secondary model with its near-perfect precision and recall values for class 1 is highly reliable make it an excellent choice for minimizing false negatives (missed risky loans).
