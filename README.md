# house-prices-prediction-project-Kaggle-
Hey everyone! 

This project was made for the Kaggle competition “House prices” (link - https://www.kaggle.com/c/house-prices-advanced-regression-techniques)

It’s my the second iteration for the competition and it’s obvious not the last one. 

A few words about the first attempt:
The first attempt included computation  of the variance inflation factor (VIF). VIF was implemented to detect multicollinearity among the features and thanks for this algorithm I was able to drop a number of the features and focus on the rest of them. Unfortunately, the data set that was created with VIF algorithm was not stable in the training model stage. For instance, accuracy of the Linear Regression on the training set with cross validation equal to 5 was 0.776, Random Forest algorithm (parameters: 'max_depth': 6, 'max_features': 'auto', 'min_samples_leaf': 1, 'n_estimators': 366) showed 0.720 - which is not bad, but AdaBoost had accuracy on the training set only 0.409, DecisionTree only 0.470. Upon receiving these  results, I decided to change my feature selection algorithm.

The second attempt included another feature selection algorithm - SelectKBest with Chi2. With this algorithm I selected 15 features among 467 (a lot of dummies features) and finally stability among trained model was achieved. The most successful models were RandomForest (parameters: 'max_depth': 6, 'max_features': 'auto', 'min_samples_leaf': 4, 'n_estimators': 233), and Xgboost (parametrs: 'colsample_bytree': 0.7, 'learning_rate': 0.03, 'max_depth': 5, 'min_child_weight': 4, 'n_estimators': 500, 'nthread': 4, 'objective': 'reg:linear', 'silent': 1, 'subsample': 0.7).

It’s obvious that is not the ideal solution for the problem but I will further update this page.
