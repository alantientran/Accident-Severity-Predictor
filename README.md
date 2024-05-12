# ML Project to Predict the Severity of Accidents
### Data Preprocessing
* Removed unnecessary features and condensed the number of feature unique values
* Handled missing data via imputation (based on similar case) and deletion
* Feature engineering times, collision direction, environment lighting condition, etc.
* One hot encoding categoricals like week day and numeralized injury severity labels to allow for scaling

## Learning Models Results with 5-fold Cross-Validation
Heavily unbalanced data lead to dropping all the "no-injury" datapoints in one half of the data (140k out of 180k datapoints were labeled no-injury. All models further use this balanced data and saw improvements in accuracy
* (78% accuracy) Decision Tree with one-hot encoded categoricals
* (50% accuracy) Decision Tree with PCA data reduced the curse of dimensionality
* (57% accuracy) SVM
  * Precision improved across the board compared to DT but recall for class 3 was poor, leading to lower f1 score 
* (57%) Tuned SVM
* (63%) Neural Network
* (78%) SMOTE used to improve recall and support count of classes 2 and 3
* (80%) Random Forest Tree
* Ensembling via Gradient Boosting and Bagging ran for over 48 hours and did not finish
