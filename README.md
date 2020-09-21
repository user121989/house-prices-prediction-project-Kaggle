# house-prices-prediction-project-Kaggle-
Hey everyone! 

This project was made for the Kaggle competition “House prices” (link - https://www.kaggle.com/c/house-prices-advanced-regression-techniques)

The main goal of the competition is to predict the selling price of a house based on its descriptive parameters. The train data set includes about 80 features and 1460 samples. The most challenging task in this project is to find a way how to reduce amount of variables. My project was made to find an answer for the feature reducing question.

It’s my second iteration for the competition and it’s obvious not the last one. 

A few words about the first attempt:
The first attempt included computation  of the variance inflation factor (VIF). VIF was implemented to detect multicollinearity among the features and thanks for this algorithm I was able to drop a number of the features and focus on the rest of them. Unfortunately, the data set that was created with VIF algorithm was not stable in the training model stage. For instance, accuracy of the Linear Regression on the training set with cross validation equal to 5 was 0.776, Random Forest algorithm (parameters: 'max_depth': 6, 'max_features': 'auto', 'min_samples_leaf': 1, 'n_estimators': 366) showed 0.720 - which is not bad, but AdaBoost had accuracy on the training set only 0.409, DecisionTree only 0.470. Upon receiving these  results, I decided to change my feature selection algorithm.

The second attempt included another feature selection algorithm - SelectKBest with Chi2. With this algorithm I selected 19 features among 466 (a lot of dummies features) and finally stability among trained model was achieved. The most successful models were RandomForest ('max_depth': 6, 'max_features': 'auto', 'min_samples_leaf': 4, 'n_estimators': 500), and Xgboost ('colsample_bytree': 0.7, 'learning_rate': 0.03, 'max_depth': 7, 'min_child_weight': 4, 'n_estimators': 500, 'nthread': 4, 'objective': 'reg:linear', 'silent': 1, 'subsample': 0.7).

The final result for Xgboost model on the test data was 0.16004 Root Mean Squared Logarithmic error.

It’s obvious that is not the ideal solution for the problem, for instance I mainly ignored feature engeniring tricks but it can be helpful on the way to improve the final result.  I will further update this page.
