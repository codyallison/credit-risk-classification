# Credit Risk Analysis

## Overview of the Analysis

The purpose of this analysis is to train and evaluate a model to determine loan risk. The information is comprised of peer-to-peer lending services data that can help determine how reliable a borrower might be.
</br>
Some of the information involved in these calculations include the borrower's income, the loan amount and interest rate, and how much debt the borrower has. 
</br>
We hope to show the accuracy and proficiency of the model to correctly predict which loans would be healthy loans vs high-risk loans. 
</br>
The process we used was to load in the available data and divide the target data from the features
- Target is loan being 0-"Healthy" vs 1-"High-Risk"
- Features include: loan size,	interest rate,	borrower income,	debt-to-income ratio,	number of accounts, 	derogatory marks,	 & total debt
</br>
Next, we split the data into training data and testing data.
</br>
Then we initiate and fit that data into a logistic regression model and calculate the Accuracy, confusion matric, and classification report
</br>
Next, we wanted to compare this to another method to see if we could improve upon the model. Using RandomOverSampler, we were able to resample the training data and fit a new logistic regression model to make a second set of predictions.
</br>
We then similarly produced Accuracy, confusion matric, and classification report as you can see compared below.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
</br>
Machine Model 1 is a logistical regression model fit against the original data provided in the CSV
</br>
Balanced Accuracy Score: 94.436%
</br>

|Confusion Matrix| |
|-------|------|
| 18679 | 80   |
| 67    | 558  |

</br>

| Target       | precision    | recall | f1-score | support |
|--------------|--------------|--------|----------|---------|
| 0            |  1.00        |   1.00 |     1.00 |    18759|
| 1            |  0.87        |   0.89 |     0.88 |      625|
|              |              |        |          |         |
| accuracy     |              |        |     0.99 |    19384|
| macro avg    |  0.94        |   0.94 |     0.94 |    19384|
| weighted avg |  0.99        |   0.99 |     0.99 |    19384|


* Machine Learning Model 2:
</br>
Machine Learning Model 2 is also a logistical regression model, however, the data were resampled using the randomoversampler module and tested against the original test data.
</br>
Balanced Accuracy Score: 99.597%
</br>

|Confusion Matrix| |
|-------|------|
| 18668 | 91   |
| 2    | 623  |

</br>

| Target       | precision    | recall | f1-score | support |
|--------------|--------------|--------|----------|---------|
| 0            |  1.00        |   1.00 |     1.00 |    18759|
| 1            |  0.87        |   1.00 |     0.93 |      625|
|              |              |        |          |         |
| accuracy     |              |        |     1.00 |    19384|
| macro avg    |  0.94        |   1.00 |     0.96 |    19384|
| weighted avg |  1.00        |   1.00 |     1.00 |    19384|

## Summary

In summary, both models seem to be healthy and suitable for credit risk assessment. Both models have a high accuracy (model 1: 94% and model 2: 99%) But as the numbers clearly show, model 2 is more accurate. 
They do have the same precision scores for both healthy (100%) and high-risk loans (87%)
But the second model can give more confidence with its higher score, but also higher recall value of accurately predicting true negative (%100)

I recommend model 2 
