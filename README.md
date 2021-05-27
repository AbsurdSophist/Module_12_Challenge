# Module_12_Challenge

## Overview of the Analysis

    Credit risk poses a classification problem that’s inherently imbalanced. This is because healthy loans easily outnumber risky loans. By utlizing various techniques to train and evaluate models with imbalanced classes, we will use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers. We are seeking to predict the loan status (healthy or high-risk) by training a logistic regression model based on given historical data. This is done by importing the historical data and seperating our target (loan status) from our features data (all other given data). Once we have done so we use the value_counts function to confirm that number of each type of data in our set (in this case there are 75036 cases for health loans, and 2500 cases of high-risk loans, clearly demonstrating an imbalanced set). Using this split data set, we then initialize, fit, predict, and evaluate our logistic regression model using by calculating the accuracy score, and generating a confusion matrix and classificaiton report for the model. We then resampled our training data to take into account the imbalanced nature of our target set. By using the random oversample model from the imbalanced-learn library, we create a target data set that is balanced (in this case 56271 instances of each outcome). We then initialize, fit, and predict a logistic regression model using our resampled data set, and once again calculate the accuracy score and generate a confusion matrix and classification report. We can now evaluate the two models, and decide whether the logistic regressionmodel is appropriate for our purposes, as well as whether our model performs better by oversampling the training data set. 

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all six machine learning models.

* Machine Learning Model 1 (Logistic Regression Model: Original Data):

  * Accuracy: 95.2 %
  * Precision:
      * Healthy (0): 100% 
      * High-Risk (1): 85%
      * Overall: 99%
  * Recall:
      * Healthy (0): 99%
      * High-Risk (1): 91%
      * Overall: 99%
  * F1:
      * Healthy (0): 100%
      * High-Risk (1): 88%
      * Overall: 99%
      
      
* Machine Learning Model 2 (Logistic Regression Model: Oversampled Data):

  * Accuracy: 99.4%
  * Precision:
      * Healthy (0): 100%
      * High-Risk (1): 84%
      * Overall: 99%
  * Recall:
      * Healthy (0): 99%
      * High-Risk (1): 99%
      * Overall: 99%
  * F1:
      * Healthy (0): 100%
      * High-Risk (1): 91%
      * Overall: 99%

## Summary

    Overall, it would appear that, based on our results, the logistic regression model fitted to oversampled training data performs better than the model fit to the original data. 
    Based on our classification report, the logisitic regression model using the original data predicts the outcome of a a health loan or high-risk loan with approximately 95% accuracy (very high). While the model predicts a health loan better than a high-risk loan (as can be seen when looking at precision, recall, and the f1-score) it should noted that, based on previous value counts, the data is unbalanced, with nearly 30 times more data available with respect to healthy loans.
    While the accuracy of the previous logisitic regression model was already high (approximately 95%), we can see that when fit with oversampled data, the balanced accuracy score is an astoinding 99%. Looking at the classification report, one of the biggest differences is with respect to recall when predicting high-risk loans. In the previous model, this was around 91%, while with the oversampled model this reaches 99%; meaning, that the model is identifying true positives with a much higher level of accuracy. This of course has a substantial impact on our F1 score, and thus we find that the oversampled logistic regression model is superior to the original.
