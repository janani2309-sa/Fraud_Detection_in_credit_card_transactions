# Fraud_Detection_in_credit_card_transactions

## These are predictive models that have been used
### RandomForrestClassifier
We will use as validation criterion GINI, which formula is GINI = 2 * (AUC) - 1, where AUC is the Receiver Operating Characteristic - Area Under Curve (ROC-AUC) [4]. Number of estimators is set to 100 and number of parallel jobs is set to 4.
The ROC-AUC score obtained with RandomForrestClassifier is 0.85.

### AdaBoostClassifier
AdaBoostClassifier stands for Adaptive Boosting Classifier
The ROC-AUC score obtained with AdaBoostClassifier is 0.83.

### CatBoostClassifier
CatBoostClassifier is a gradient boosting for decision trees algorithm with support for handling categorical data
The ROC-AUC score obtained with CatBoostClassifier is 0.86.

### XGBoost
XGBoost is a gradient boosting algorithm
The best validation score (ROC-AUC) was 0.984, for round 241.
The AUC score for the prediction of fresh data (test set) is 0.974.

### LightGBM
This is another gradient boosting algorithm, LightGBM
Best validation score was obtained for round 85, for which AUC ~= 0.974.

## Conclusion
We investigated the data, checking for data unbalancing, visualizing the features and understanding the relationship between different features. We then investigated two predictive models. The data was split in 3 parts, a train set, a validation set and a test set. For the first three models, we only used the train and test set.

We started with RandomForrestClassifier, for which we obtained an AUC scode of 0.85 when predicting the target for the test set.

We followed with an AdaBoostClassifier model, with lower AUC score (0.83) for prediction of the test set target values.

We then followed with an CatBoostClassifier, with the AUC score after training 500 iterations 0.86.

We then experimented with a XGBoost model. In this case, se used the validation set for validation of the training model. The best validation score obtained was 0.984. Then we used the model with the best training step, to predict target value from the test data; the AUC score obtained was 0.974.

We then presented the data to a LightGBM model. We used both train-validation split and cross-validation to evaluate the model effectiveness to predict 'Class' value, i.e. detecting if a transaction was fraudulent. With the first method we obtained values of AUC for the validation set around 0.974. For the test set, the score obtained was 0.946.
With the cross-validation, we obtained an AUC score for the test prediction of 0.93.
