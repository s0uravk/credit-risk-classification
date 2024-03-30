# Credit Risk Classification

## Overview of the Analysis

Following is a basic overview of the analysis performed for credit risk classification:

* The purpose of the analysis is to train and evaluate a model based on loan risk. We used a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.
* The target financial information in the data is the loan status. The features in the financial data that are used to predict the loan status are loan size, interest rate, borrower income, debt-to-income ratio, number of accounts, derogatory marks, and total debt.
* For the target variable loan_status, I tried to predict the classification of borrowers into 0 or 1, where 0 corresponds to a healthy loan and 1 to a high-risk loan.  
* At first, identified and separated features and the target from the input dataset, then divided them for training and testing the model using train_test_split. Then, created a LogisticRegression model and trained it using X_train and y_train data. Then the trained model to predict the target using X_test data. Finally, evaluate the model's performance by calculating accuracy_score, confusion_matrix, and classification_report.
* Utilized the LogisticRegression model, which is a technique that uses mathematics to find the relationships between two data factors. It then uses this relationship to predict the value of one of those factors based on the other. The prediction usually has a finite number of outcomes, like yes or no (0 or 1 in this case).
[Click for more information on LogisticRegression](https://aws.amazon.com/what-is/logistic-regression/#:~:text=Logistic%20regression%20is%20a%20data,outcomes%2C%20like%20yes%20or%20no.)

## Results

This section describes the accuracy scores, as well as the precision and recall scores of the Logistic regression model used for the activity:

* Model 1: Logistic regression with original data:
    * This model does a good job of predicting both the healthy and the high-risk loans as inferred from the accuracy score of 99%.
    * This model has a precision score of 100% for healthy loans and 85% for high-risk loans. Meaning that healthy loans were classified correctly 100% of the time while mere 85% in the case of high-risk loans.
    * This model has a recall score of 99% for healthy loans and 91% for high-risk loans. The scores imply that for all the instances where the loans were healthy, 99% of the time they were classified correctly. However, for all the instances where the loans were high-risk, they were classified correctly 91% of the time.
      
     ![Model1_matrix](https://github.com/s0uravk/credit-risk-classification/assets/144293972/d295e989-8dbe-4336-ab22-fbeebc4a4b42)

     ![Model1_report](https://github.com/s0uravk/credit-risk-classification/assets/144293972/a9a99a65-499f-4579-b802-3a622162418b)
  
But as we see the y.value_counts() data is imbalanced towards healthy loans(0) with 75036 values as 0 and 2500 values as 1, which could have impacted the training and hence the predictions.

For imbalanced data, either I can use oversampling or undersampling. In the former case, duplicate data points will be created for the minority class which is 1 which will overfit the data. In the latter case, the majority class(0) will be compacted to the same size as the minority class, which might discard potentially valuable information from the majority class.

Oversampling seems to be more appropriate to use to balance the data as I don't want to lose valuable information from the majority class. It would affect the model's training time and memory requirement but it's the trade-off for better predictions.

* Model 2: Logistic regression with resampled data:
    * This model does a good job of predicting both the healthy and the high-risk loans as inferred from the accuracy score of 99%.
    * This model has a precision score of 100% for healthy loans and 84% for high-risk loans. Meaning that healthy loans were classified correctly 100% of the time while a mere 84% in the case of high-risk loans.
    * This model has a recall score of 99% for the healthy loans and 99% for the high-risk loans. The scores imply that for all the instances where the loans were healthy, 99% of the time they were classified correctly. However, for all the instances where the loans were high-risk, they were classified correctly 99% of the time.
      [Random Over Sampling Documentation](https://imbalanced-learn.org/stable/over_sampling.html)

     ![Model2_matrix](https://github.com/s0uravk/credit-risk-classification/assets/144293972/a0ac897a-a3de-4657-9e97-0eb2f21472ec)

     ![Model2_report](https://github.com/s0uravk/credit-risk-classification/assets/144293972/eeb893ff-6c2e-442e-a4a7-20525efbba90)


## Summary
Here's the summary of the analysis and recommendation of the best model to use.

* Both of the models have a high accuracy score. Whereas, for the second model precision score is slightly less compared to the first model. The second model performs the best as it has a higher recall score for predicting high-risk loans compared to model 1.
* Yes, the performance depends on the problem we are trying to solve as model 2 decreases the number of False negatives meaning that the loans that were predicted as healthy but in actuality, were high-risk. And we would like to avoid those circumstances as much as possible. Predicting high-risk loans (1) correctly is more important.
