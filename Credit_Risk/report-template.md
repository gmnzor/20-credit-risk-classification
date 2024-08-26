# Module 12 Report Template
Nestor Gomez

## Overview of the Analysis

For this analysis we used machine learning and a logistic regression model to analyze lending data to train a logistic regression model capable of predicting the creditworthiness of potential borrowers.

We utlized historical data from a peer-to-peer lending services which took into account various factors including loan size, interest rate, borrower income, open lines of credit, prior derogatory credit marks, and total outstanding debt, alongside a pre-existing classifier as to whether the loan ultimately defaulted or not.

Our intent was to see if the information in this dataset could predict the healthy/default classifier consistently, which would then allow us to utilize the model to predict potential defaults when new customers apply for credit.

To being we took in our data, and separated out the loan_status field which held our loan classifier, 0 being a healthy loan and 1 being a defaulted loan.

These two datasets were split further, with 75% of data points being carved out to train the data and 25% being kept back for testing our model.

We created a Logistic Regression model with the training dataset which looked to find trends between loan details and the customer's credit history and the eventual completion of the loan.

Once the model was fit, we then provided it the testing data to see if the model could predict healthy vs defaulted loans.

We then broke the results into four categories
* True Positives (TP) - Healthy loans marked as healthy
* False Positives (FP)- Defaulted loans marked as healthy
* True Negatives (TN)- Defaulted loans marked as risky
* False Negatives (FN)- Healthy loans marked as risky

By tallying up these four endcases, we can score the model's effectiveness.

## Results

Using bulleted lists, describe the accuracy scores and the precision and recall scores of all machine learning models.

* Logistic Regression Model:
    * Accuracy  
        * How many loans were predicted correctly
        * 99% of test cases (19,238/19,384) were correctly predicted
    * Precision  
        * Of loans predicted to be healthy, how many were healthy, and vice versa
        * True Positives / (True Postiives + False Positives)
        * 99% of loans predicted as healthy loans were identified as healthy
        * 94% of predicted defaulted loans were identified as risky
        * Macro average - 97% of all cases were correctly predicted  
    * Recall 
        * Of healthy loans, how many were predicted healthy, and vice-versa
        * True Positives / (True Postiives + False Negatives)
        * Near 100% of all healthy accounts were predicted to be healthy
        * 84% of defaulted accounts were predicted to be risky
    

## Summary

Our logistics regression model overall has high marks, correctly predicting loan outcome on 99% of test cases. 

In this use case, we are trying to determine likely default based on criteria at the time of application to avoid loss of intial investment. Of the one percent of cases that were misidentified, the largest cohort instance where we failed to identify a risky loan as risky, where we mislabeled 16% as healthy. 

While this can seem like a large margin of error, we must take into account that we had only 693 defaulted accoutns vs 18691 healthy. Our model had far more data on healthy accounts and was thus better able to identify those. 

With this limitation in mind, awe come back to our weight avg scores of 99% across precision, recall, and f1-score and can be confident in this prelimiary model's predictive ability.
