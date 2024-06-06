# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

**Answers:**

* The purpose of this analysis was to build a machine learning model to predict the creditworthiness of borrowers using historical lending data from a peer-to-peer lending services company. This is crucial because it helps in identifying risky loans and reducing financial losses.
* The data included information about various loans, and we needed to predict whether a loan is healthy (0) or high-risk (1).
* The primary variable to predict was `loan_status`, with value counts showing a significant imbalance: many more healthy loans (0) compared to high-risk loans (1).
* The machine learning process involved: 
  1. Preparing the data by reading it into a Pandas DataFrame.
  2. Splitting the data into features (`X`) and labels (`y`).
  3. Splitting the data into training and testing sets using `train_test_split`.
  4. Training a logistic regression model on the original data.
  5. Resampling the data using `RandomOverSampler` to handle class imbalance.
  6. Training another logistic regression model on the resampled data.
  7. Evaluating both models using balanced accuracy, confusion matrix, and classification reports.
* We used `LogisticRegression` for training the models and `RandomOverSampler` from the imbalanced-learn library for resampling the data to address class imbalance.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1 (Original Data):
  * **Balanced Accuracy Score**: 0.94
  * **Precision**:
    * `0` (healthy loan): 1.00
    * `1` (high-risk loan): 0.84
  * **Recall**:
    * `0` (healthy loan): 0.99
    * `1` (high-risk loan): 0.94
  * **F1 Score**:
    * `0` (healthy loan): 1.00
    * `1` (high-risk loan): 0.89

* Machine Learning Model 2 (Resampled Data):
  * **Balanced Accuracy Score**: 0.99
  * **Precision**:
    * `0` (healthy loan): 1.00
    * `1` (high-risk loan): 0.84
  * **Recall**:
    * `0` (healthy loan): 0.99
    * `1` (high-risk loan): 0.99
  * **F1 Score**:
    * `0` (healthy loan): 1.00
    * `1` (high-risk loan): 0.91

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.

**Answers:**

* The model that seems to perform best is **Model 2 (Resampled Data)**. It has a higher balanced accuracy score of 0.99 compared to 0.94 for Model 1. Additionally, Model 2 has a better recall for high-risk loans (0.99) compared to Model 1 (0.94).
* The performance depends on the problem we are trying to solve. In this case, it is more important to predict the `1`'s (high-risk loans) accurately to minimize financial losses. Model 2's higher recall for high-risk loans makes it more suitable for this purpose.
* Given the higher balanced accuracy and recall for high-risk loans, **Model 2 (Resampled Data)** is recommended. This model ensures that almost all risky loans are identified, which is crucial for effective credit risk management.
