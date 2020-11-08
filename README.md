# Cancer detection

## CancerSEEK -- Testing Pre-processing steps (1)

This is one out of several experiments made during this project. More specifically, current notebook will evaluate **Naive Bayes**, **Logistic regression**, **KNN**, **SVC**, **Decision Trees**, **Random Forest**, **Gradient Boosting** and **XGBoost** on **Normal**, **Winsorized**, **Log-**, **BoxCox-** and **Yeo-Johnson** transformed data. 

The objective is to see which of the five pre-processing steps work best for each of the algorithms on this dataset. Sensitivity and Specificity will be used as evaluation metrics. No Feature Engineering will be applied. Thus, only the 10 features in the dataset that comes with the publication will be evaluated.


As the dataset is fairly small and considerable unbalanced, stratified k-fold will be used to preserve the percentage of samples for each class in the train and test set split.



## Results

Transforming the data made as expected a huge difference for Naive Bayes, Logistic Regression, KNN and SVC while the tree based models cared little about this. Best results were nonetheless achieved on the Winsorized and the Winsorized combined with Yeo-Johnson transformation datasets using XGBoost with around 74% sensitivity and 100% specificity. Nevertheless, the difference wasn't that great compared with the non-transformed datasets. Gradient Boosting was a high performer as well and almost in par with XGBoost. 


## Future Work

From a pure algorithmic perspective it would be interesting to further tune the most performant XGBoost model. Evaluating other tree based algorithms such as LightGBM and CatBoost as well as combining several individual classifiers using stacking or voting techniques might further boost the performance. Furthermore, when blending several classifiers it is normally benefitial to combine classifiers of various strenghts so their weaknesess are "cancelled" out. 


