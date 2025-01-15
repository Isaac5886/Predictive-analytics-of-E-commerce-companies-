## showing if a customer will purchase or not

1. Loading Data
2. Extraordinary Data Analysis 
3.   Future Engineering 
4.   predictive model
5.  Evaluate model

 ##    FEATURE SELECTION

   In the Random Forest Classifier model, the most influential feature is Page Values, with an importance score of 39%. This suggests that the monetary value attributed to each page plays a key role in driving revenue. Next, Product Related_Duration and Exit Rates share an equal importance score of 
9%.
    In the Logistic Regression model, the Akaike Information Criterion (AIC) was calculated at 7361.8, and the Bayesian Information Criterion (BIC) was 7487.9, suggesting a good fit while reducing the number of features included. Page Values was the strongest predictor, with a p-value of less than 5.090279e-254, indicating a statistically significant relationship. Other significant predictors included ProductRelated_Duration (p_value= 3.721492e-02) and Exit Rates (p-value = 1.100523e-10).
    The Decision Trees model also identified Page Values as the most important variable, selecting that feature for the first split. Bounce Rates, Month, and ProductRelated_Duration became important variables affecting the revenue, showing how seasonality and user engagement metrics influence purchase decisions.
  The Gradient Boosting Classifier identified Page Values as the most influential feature, with the highest importance score of 7.46%, Bounce Rates of 4.27% and Month of 4.69%. These features contribute significantly to the model's predictions, with Page Values being the most important factor.