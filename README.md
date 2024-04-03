# credit-risk-classification

In this repository you'll find a folder called **credit-risk-classification** in it you'll find: the **credit_risk_classification.ipynb** file responsable for our analysis, the **report.md** file and the folder called **Resources** holding the file **lending_data.csv** where data for our analysis is stored.

## Overview of the Analysis

The goal of this analysis is to determine if a specific loan is an healthy one or an high risk one, starting from a dataframe holding informations about: loan size, interest rate, borrower income, total debt, loan status and others, this last one being the target of our analysis, 77535 instances long and being described by zeros and ones, zeros describing the healthy loans and the ones being the high risk ones.
For this analysis we started by defining the target variable or dependent variable, y, as `loan_status` and extracted it from the rest of the dataset that will represent our independent variables, X. We then proceeded to split the variables in two groups each: testing Xs and ys and training Xs and ys, after that we defined our model as `LogicRegression`, this algorithm is a binary classifier that means that everyone of our records will be assigned to one of two different groups: `healthy loans` or `high risk loans`. After that we proceed with fitting the model with the training values we extracted before and make our predictions, after that we generated the confusion matrix and the classification report for our predictions in order to analyse how effective our model is in predicting the status of the loan.

## Results

* Machine Learning Logic Regression Model:
    * **Model Accuracy** = 0.99 : this means that our model is able to predict if a loan is healthy or not 99% of the time. That is a good value because we are not looking to reach the 100% but just get as close as possible to it, that is because having a model with a perfect score would mean that we have overfit the model therefore it would struggle in predicting new values not included in the original dataset.
    * **Model Precision** (`0`) = 1.00 , **Model Precision** (`1`) = 0.85 : our model was able to perfectly predict the healy loans but has a lower score when it comes to the high risk ones, that is due to the amount of *false positive* (102) and *true positives* (563) predictions generated by the model, where accuracy is equal to the total amount of *true positives* divided by the sum of *true positives* and *false positives*.
    * **Model Recall** (`0`) = 0.99 , **Model Recall** (`1`) = 0.91 : the recall our model was able to score is high for both groups that is due to the amount of false negative predictions compared to the total amount of true positive predictions of each group that our model was able to score, recall being equal to the amount of *true positives* divided by the sum of *true positives* and *false negatives* those being respectively (18663 , 102) for group `0` and (563 , 56) for group `1`
    
    

## Summary

Overall the model is solid and able to determine if a loan is healthy or at high risk. That said it might be relevant to talk about the repercussions of a misclassification of one of the former as one of the first, in fact predicting a high risk loan as a healthy one might end up in a significant loss.
Even though this might be a risk for our customer the amount of false positives predicted by our model for healthy loans is 102 against 18663 total true positives for the same class and when it comes to the high risk ones the amount of false positives predicted is 56 compared to the 563 true ones. This data let us assume as previously stated that the model overall is solid and can be used in a real world environment.
In order to reduce the errors and augment the prediction efficiency of the model we might suggest for the future entries to gather more information about the applayers, in order to further expand our model making it more accurate and effective, also we might suggest to cross validate our model by using other models like a Gradient Boosting Regressor model, method that we tested ourselves and showed good results even though less effective by itself than the Logarithmic Regression, in order to reduce overfitting and increase the generalizability of the model.



All the code for the analysis was made by me with the help of the class materials.
