# Module 12 Report Template

## Overview of the Analysis

The purpose of this analysis is to build a model that can identify the creditworthiness of borrowers leveraging data from a peer-to-peer lending services company. The company data consists of eight categories:

 * the size of the loan
 * interest rate
 * the income of the borrower
 * borrower debt to income ratio
 * number of borrower accounts
 * number of borrower derogatory marks
 * total borrower debt
 * loan status in terms of healthy (0) vs. high-risk (1)
 
I created my labels set from the “loan_status” column, and then I created the features DataFrame from the remaining columns. The results left a labels set that only contained 2,500 high-risk loans compared to 75,036 healthy loans.

I then created test and training data sets and developed two different Logistic Regression models. Using RandomOverSampler, I fit one of the models with oversampled data resulting in equally high number of high-risk and healthy loans at 56,271. The other model just used the normal sample from the source data.


## Results

### Machine Learning Model 1:

  * Balanced Accuracy Score: 95.2% (Very good)
  
  * Precision: 
      * Healthy - 100% (Perfect) 
      * High-Risk - 85% (Good)
      
  * Recall:
      * Healthy - 99% (Perfect)
      * High-Risk - 91% (Very good)
      
  
### Machine Learning Model 2 (fit with oversampled data):

  * Balanced Accuracy Score: 99.4% (Perfect)
  
  * Precision: 
      * Healthy - 100% (Perfect) 
      * High-Risk - 84% (Good)
      
  * Recall:
      * Healthy - 99% (Perfect)
      * High-Risk - 99% (Perfect)

## Summary

When we look at Model 1, we see fairly accurate predictive results, highlighted by a balanced accuracy score of 95.2%. Model 1 was able to demonstrate  nearly perfect results for healthy loans (perfect 100% precision score & just a hair off perfect 99% recall score) and some very good results for high-risk loans (good 85% precision score and very good 91% recall score), despite the great difference in data volume. 

But, as predictive as Model 1 was, Model 2 using oversampled data was even more predictive. Fitting to an oversampled dataset in this case got us an improved balanced accuracy score of 99.4%. Healthy loans were just as predictive in Model 2 than Model 1 but with the added sample for high-risk loans, Model 2 saw a nearly perfect recall score of 99% for high-risk loans. 

While both models do a great job, I recommend using Model 2 with the oversampled data, especially if the goal is to accurately identify high-risk loans.
