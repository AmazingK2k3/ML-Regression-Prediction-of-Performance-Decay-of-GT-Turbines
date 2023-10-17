# Maintanence of Naval Propulsion-Regression
During the process of ship design, the optimization of propulsion systems is a crucial task.  It is important to account for the performance decay over time of the GT components such as GT turbines.  The main intention of this project is to predict the performance decay of GT turbines predicting its state coefficient with the data of key propulsion parameters such as ship speed, torque, compressor outlet pressure etc using regression analysis. Efficient and accurate prediction of degradation will help in preemptive measures to strengthen the performance of turbines and maintenance periods.

Data Used: The model is trained using the UCI Maintenance of Naval Propulsion Plan dataset. The raw dataset consisted of 18 columns such as level position, air pressures, temperatures, speed etc. to predict the variable G Turbine decay state coefficient. The total number of samples available in the dataset is 11934 with no null values.


Steps Involved:
* Data Observation and Preparation
* EDA: Data visualisation and understanding
* Model building: Linear Regression
* Model Evaluation: ANOVA
* Cross Validation
* Hyper Parameter Tuning

Various Regression Methods were used in this project:
* Baseline Linear Regression
*  Polynomial Regression with Lasso and Ridge Regularization
*  Support Vector Machines
   *  Linear SVM
   *  Polynomial SVM
   *  RBF SVM
*  Decision Trees
*  Random Forest
*  Adaboost
*  Gradient Boost

Hyperparameter Tuning was done using GridSearchCV and Randomized Search CV

## Results
Decision trees and Random forest regressor turned out to yield the highest  R2 value being 0.972 and 0.993 respectively. 
The R2 score for AdaBoost and GradientBoost models are 0.394 and 0.1253 respectively, which shows that the models are performing poorly, this might be due to the parameters chosen while making these models.
We also performed Cross Validation first in our training set with 10 k-folds and the validation score turned out to be  0.91 +/-  0.0078 for linear regression.
And with our entire dataset with 10 k-folds yielding the validation score of  0.90 +/- 0.024 for linear regression. 

### Cross Validation:
Like the R2  values, Ridge Regression yields a sensible cross validation score of 0.90 +/- 0.008 for the training set and a score of 0.90 +/- 0.02 for the entire dataset. 
Polynomial Regression yields a cross validation score of 0.68 +/- 0.059 for the training set and a score of 0.99 +/- 4.45 for the entire dataset, presumably an error. 
LinearSVM like in the previous results yields a negative value of cross validation score.
Decision trees yields one of the highest scores with the cross validation scores for training set is  0.956 +/- 0.0067  and for the entire dataset being  0.88 +/- 0.120
The best cross validation score is given by Random Forest Regressor which is 0.98 +/- 0.003 for the training dataset and 0.93 +/- 0.085 for the entire dataset.
The cross validation scores for gradient boosting regressor are 0.34 +/- 0.051 for the training dataset and for the entire dataset is 0.33 +/- 0.084.
For the AdaBoost Regressor the same scores for the training dataset are 0.17 +/- 0.022 and for the whole dataset are 0.15 +/- 0.043 which shows that the model is worst

### Conclusion
As stated in the introduction, the main intention of this project, which is to  predict the performance decay of the GT turbines by predicting its state coefficient using regression analysis, has been achieved. The regression analysis included predicting the coefficient using various models- Linear Regression,Polynomial Regression, Lasso, Ridge, Elastic-Net, Linear SVM, Polynomial SVM, Rbf SVM, Decision Trees, Random Forest , Adaboost and Gradient Boost. The performance of the models were evaluated using ANOVA method. The results were gathered pre scaling and post-scaling the models.
Cross validation was then carried out for the models on the training set then the entire set whose results have been gathered. Finally hyperparameter tuning was performed for models that were able to process and execute to yield results. 
Out of the analysis carried out, we can conclude that the Random Forest Regressor model proved to be the most accurate in predicting the state coefficient of the gas turbine using the propulsion parameters. With a  high R2 score and continued high scores in cross validation and hyperparameter tuning, we can deploy this model to strengthen the performance of the turbines and increase the quality of maintenance of the turbines.

