# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Joy Hilda Mukami Kareko

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
TODO: Add your explanation

#### Since the number of bikes needed should be greater than 0, negative numbers were rejected.
#### I had to set any negatives to 0 count. 
### What was the top ranked model that performed?
TODO: Add your explanation
#### It was the WeightedEnsemble method at first, then after adding hyperparameter tuning, it was LightGBM.
#### This maintained for the last model when I did the hyperparameter tuning.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
TODO: Add your explanation
#### I noticed the data had various categorical variables.
#### I noticed also that more features meant better model performance.
#### I added an additional feature 'month','hour' and 'day' by separating the date using to_datetime function.
#### I also found out that the most important feature was the 'hour' feature, followed by 'workingday' and 'datetime'


### How much better did your model preform after adding additional features and why do you think that is?
TODO: Add your explanation

#### The model improvement was significant. The error score was lower to -35.
#### The 'hour' feature greatly improved my score.
#### The improvement was because the model had an additional feature to train on and learn on the data.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
TODO: Add your explanation

#### My model improved slightly after the hyperparameter tuning.
#### After trying different hyperparameters the performance score dropped and there was no improvement on the error score.
### If you were given more time with this dataset, where do you think you would spend more time?
TODO: Add your explanation
#### I would drop some features that seem insignificant.
#### I would also train the best models separately.
#### I would also try new features and see if they made any differences.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|default_feats	|default_feats	|default_feats	|1.39|
|add_features|default_feats	|default_feats	|default_feats	|0.47|
|hpo|num_trials:num_trials|scheduler:local|searcher:search_strategy|0.54|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](nd009t-c1-intro-to-ml-project-starter/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](nd009t-c1-intro-to-ml-project-starter/model_test_score.png)

## Summary
TODO: Add your explanation
#### First, I explored the data to understand the various features. I used histograms to understand the data distribution. I also changed the categorical data to a categorical data type. This was in the seasons, weather, working day and holiday data types. I also used describe() to understand the statistical distributions of the data. I then used autogluon to train on the data. The best model was Weighted Ensemble method with an error score of -114.
#### I then added additional features, hour, month and day by separating the date time columns. These features were significant and the Weighted Ensemble method was best still with an error rate of -35.
#### I then tuned my hyperparameters on the overall autogluon parameters and the error rate improved slightly to -34. The best model was however LightGBM.
#### I also tried changing the GBM hyperparameters and there was no improvement although the best model remained as the LightGBM.
#### Given more time, I would have tried different hyperparameters and also tried different models individually to achieve the lowest error rate possible.