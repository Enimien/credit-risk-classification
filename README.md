## Overview of the Analysis

Building a model that can accurately identify the creditworthiness of borrowers is crucial for a peer-to=peer lending services. Such a model allows lenders to evaluate the risk associated with lending to a particular borrower, set appropriate interest rates, and make well-informed decisions about loan approvals. By leveraging historical borrower data and various financial indicators, lenders can assess the probability of default and make more reliable lending decisions. In this project, I used a dataset containing the historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

### Data Attributes (77,536 data entries)
* `loan size` : The amount of money borrowed.
* `interest_rate` : The percentage of the loan charged as interest to the borrower.
* `borrower_income` : The annual income of the borrower.
* `debt_to_income` : The ratio of a borrower's total debt payments to their gross income.
* `num_of_accounts` : The number of credit accounts the borrower has.
* `derogatory_marks` : Negative entries on the borrower's credit report, such as late payments or bankruptcies.
* `total_debt`: The total amount of debt the borrower owes.
* `loan_status`: The outcome of the loan, categorized as either "healthy" (low risk) or "high risk".

### ML Process
1. Data loading and exploration
2. Data split into training and testing sets
3. Train the model
4. Fit the model
5. Test the model
6. Evaluate the accuracy of the model

## Results

#### Description of Model Accuracy, Precision, and Recall scores.

- The confusion matrix shows the logistic model predicted 18,663 as healthy loans correctly and 102 as healthy loans incorrectly from a total loan status of 18,765 which were healthy (i.e., low-risk).
- The model predicted 563 as high-risk loans correctly and 56 high-risk loans incorrectly from a total loan status of 619 which were high-risk.

Confusion Matrix showing the Imbalance proportions of the actual and predicted classes
* Logistic Regression Machine Learning Model:
*                          precision    recall  f1-score   support
        Healthy Loan         1.00      0.99      1.00     18765
        High-risk Loan       0.85      0.91      0.88       619

        accuracy                               0.99     19384
        macro avg          0.92      0.95      0.94     19384
        weighted avg       0.99      0.99      0.99     19384

- The classification report which takes into account the model's accuracy revealed that the healthy loans had a precision score of 100%, and a recall of 99%. For the non-healthy loans, the precision and recall were 85% and 91%, respectively. Overall, the model attained an accuracy of 99%, indicating a high level of correctness in its predictions.


## Summary
- This logistic regression model is highly accurate in predicting healthy loan borrowers compare to high-risk loan borrowers. With an overall accuracy of 99%, there is only a 1% chance of misclassification for healthy loan borrowers. The model's precision, recall, and F1-score for healthy loan borrowers are all nearly perfect, but it shows a notable drop in these metrics for high-risk loan borrowers, where the accuracy dropped to 91%. This is associated to an imbalance dataset with larger records of Healthy Loan class then the high-risk loan records. The classifier focuses on getting the healthy loan class and not the smaller high-risky Loan class.
- Given these results, it is recommended to balance the dataset using oversampling technique which improves the accuracy score before using the logistic machine learning model to predict credit risk. While it is important to accurately predict the behavior of both healthy and high-risk borrowers, predicting high-risk loans (i.e., the 1's) is particularly crucial. By identifying high-risk borrowers, the bank can pay special attention to them when providing new loans or increasing their loan amounts, thus better managing credit risk.

