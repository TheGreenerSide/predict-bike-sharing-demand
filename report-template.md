# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Gehad Elaswad

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
kaggle requires no negative values in the submission, I had to make sure my results had no negative values and if there was any, I would have converted them to zero

### What was the top ranked model that performed?
The second model: where new features were added but no hyperparameters were changed

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
it highlighted the importance of the Quantitative variables such as temperature, wind speed and humidity. Meanwhile, intially it was not as important for categorical variables as it treated them like quantative variables (holiday, season...etc)

### How much better did your model preform after adding additional features and why do you think that is?
it performed much better (from score val of ~-54 to ~-33); because autogluon treated some variables as quantitive when they are categorical and because it focused on elements of the data which may be more influential instead of the whole feature (ex: the hour and day of the week instead of the date as a whole)

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
some hyperparameters made the model perform worse and some made it perform well, however it did not perform better as a whole than the previous model probably because autogluon changes hyperparameters in the best way possible for the model to be optimized for each specific problem

### If you were given more time with this dataset, where do you think you would spend more time?
I would try adding more features and analyse their relations with the demand

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|searcher|learning_rate|XGB reg|score|
|--|--|--|--|--|
|initial|default|default|default|1.84007|
|add_features|default|default|default|0.65209|
|hpo|local_random|0.04|squaredlogerroe|0.73958|
### Create a line plot showing the top model score for the three (or more) training runs during the project.


![model_train_score.png](model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.


![model_test_score.png](model_test_score.png)

## Summary
The feature adding and changing type of feature were impocatful on the score, however the hyperparameter tuning did not improve the model despite trying different changes probably because autogluon optimizes the models extremely well in the first place 
