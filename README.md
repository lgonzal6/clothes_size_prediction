# clothes_size_prediction

## About the project

Online clothing retailers can provide shoppers a little more confidence in their purchases by providing size suggestions. As this project, will demonstrate, predicted correct size can be tricky because size selection goes beyong someone's weight, height, and age. Fit preferences also come into play as well as body shape.

However, in this scenario, our dataset include 119,734 rows providing a shopper's weight (kg), age, height (cm), and size. There are 7 sizes: 'XXS', 'S', 'M', 'L', 'XL', 'XXL', 'XXXL'. Our questions here is which classification algorithm can best predict size, can we prodive shoppers with sound predictions?

## About the Data

The data was found on Kraggle and can be accessed [here](https://www.kaggle.com/datasets/tourist55/clothessizeprediction)

Columns include: weight (kg), age, height (cm), and size

## Process and Conclusion

In this project, we imputed the data using KNNImputer, we also scaled the data using StandardScaler. Furthermore, after the EDA revealed the importance of weight and height in size determination, we also added BMI.

We ran a few classification algorithms including: LogisticRegression, KNeighborsClassifier, DecisionTreeClassifier, BaggingClassifier and AdaBoost. Comparing results across these models, we obtained the best results from the logistic regression model, which we further fine-tuned using GridSearchCV.

The final model resulted in an accuracy score of 52%, which upon first impression may not seem impressive. However, exploring the predictions and errors, we see that most errors are within neighboring sizes. This is not surprising, given that a lot of the data on weight, heigh, and age had overlap in across the sizes. Meaning many individuals who weighted, 75kg for instance wore size S, some size M, etc. Another reason why this is not a surprising result is that the data set does not imclude important information, such as fit preference and body shape.

Nonetheless, this predictions can be useful in providing shoppers with suggestions. For instance, we can use this predictions to suggest size after a shopper had provided their preference for fit, if they would like a snug fit, we can provide a suggestions for a smaller size when the probability of the size and one size lower are withing a certain margin. Same for shoppers who want a loose fit, we can use these predictions to predict the correct size up.
