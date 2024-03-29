# credit-risk-classification

## Overview of the Analysis

Following is a basic overview of the analysis performed for credit risk classification:

* The purpose of the analysis is to to train and evaluate a model based on loan risk. You’ll use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.
* The target financial information in the data is the loan status. The features in the financial data that are used to predict the loan status are loan size, interest rate, borrower income, debt to income ratio, number of accounts, derogatory marks and total debt.
* For target variable loan status i tried to predict is classification of borrowers into 0 or 1, Where 0 corresponds to a healthy loan and 1 to a high risk loan.  
* At first, identified and seprarted features and target from the input dataset, then divided them for training and testing the model using train_test_split. Then, created a LogisticRegression model and trained it using X_train and y_train data. Then used the trained model to predict target using X_test data. Finally, evaluated the model's performance by calculating accuracy_score, confusion_matrix and classification_report.
* Utilized LogisticRegression model, which is a technique that uses mathematics to find the relationships between two data factors. It then uses this relationship to predict the value of one of those factors based on the other. The prediction usually has a finite number of outcomes, like yes or no(0 or 1 in this case).
[Click for more information on LogisticRegression](https://aws.amazon.com/what-is/logistic-regression/#:~:text=Logistic%20regression%20is%20a%20data,outcomes%2C%20like%20yes%20or%20no.)

## Results

This section describes the accuracy and balanced accuracy scores, and the precision and recall scores of the Logistic regression model used for the acitivity:

* Logistic regression:
    * This model does a good job in predicting both the healthy and the high-risk loans as inferred from accuracy score of 99%.
    * This model has a precision score of 100% for the healthy loans and 85% for the high-risk loans. Meaning that healthy loans were classified correctly 100 % of the times while mere 85% in case of high-risk loans.
    * This model has a recall score of 99% for the healthy loans and 91% for the high-risk loans. The scores imply that for all the instances where the loans were actually healthy, 99% of the times they were classified correctly. However, for all the instances where the loans were actually high-risk, they were classified correctly 91% of the times.
      
     ![Model1_matrix](https://github.com/s0uravk/credit-risk-classification/assets/144293972/d295e989-8dbe-4336-ab22-fbeebc4a4b42)

     ![Model1_report](https://github.com/s0uravk/credit-risk-classification/assets/144293972/a9a99a65-499f-4579-b802-3a622162418b)


     ![Model2_matrix](https://github.com/s0uravk/credit-risk-classification/assets/144293972/a0ac897a-a3de-4657-9e97-0eb2f21472ec)

     ![Model2_report](https://github.com/s0uravk/credit-risk-classification/assets/144293972/eeb893ff-6c2e-442e-a4a7-20525efbba90)


## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:

* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.
