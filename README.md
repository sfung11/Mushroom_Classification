Susan Fung
Mushroom Classification
August 2, 2017

Objective:
Predict whether a mushroom is poisonous or edible using a minimal number of features that a layperson can recognize.

Data:
8024 rows, 22 columns (including "class", which is the target variable). The data set is located at [this site](https://archive.ics.uci.edu/ml/datasets/Mushroom). The remaining 21 columns represent categorical features pertaining to mushroom classification. 

Feature Selection:
With all 21 features, it is possible to acheive a TPR (aka recall, sensitivity) of 1.0 and a TNR (aka specificity)
of 1.0. However, if considering the objective, the features were initially reduced to 4 features that are likely to be easily understood by a lay person (eg not a mycologist). These features were cap_color, cap_shape, cap_surface, and habitat. Within cap_color and cap_surface, minor changes were made to condense the number of categories within those features.  

Cleaning Missing Data:
This dataset is only missing data in one column, stalk_root. Any rows missing data in this field were replaced with np.nan.

Algorithm:
A variety of classification methods were used: logistic regression, decision tree models, KNN, SVMs were performed on normalized training data.

Evaluation:
The model was evaluated by cross validation using accuracy as well as AUC as metrics for success. A threshold probability was set in order to ensure that the number of false positives was zero.  

Further Improvement:
Since the priority metric was to minimize false negatives, the next step would be to take the mushrooms misclassified as false positives and run those through a second round of classification. This will ensure that the mushrooms that are safe to eat are labeled appropriately. 
