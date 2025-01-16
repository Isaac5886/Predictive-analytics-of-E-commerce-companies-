## showing if a customer will purchase or not

1. Loading Data
2. Extraordinary Data Analysis 
3.   Future Engineering 
4.   predictive model
5.  Evaluate model


##   DATASET 
 
  The researcher collected secondary data for this study from the Online Shopper Purchasing 
Intention dataset, available on the University of California, Irvine (UCI) Machine Learning Repository website (Agustyaningrum, et al., 2021). The data carries information connected to customer behaviouron online shopping platforms and comprises records from 12,330 user sessions. The study attributes each session to a specific user over one year to ensure that the data remains unbiased by special events or holidays over an extended period (Hu & Shi, 2024). The dataset having a total of 18 features, consists of 10 numerical and 8 categorical features. 
   Revenue is the target feature that indicates whether there is a purchase or non-purchase, represented as a Boolean variable. The false value signifies that the customer did not purchase, whereas a true value indicates that a purchase was made. Of the total samples, 10,422 (84.53%) are negative, showing that the customers did not purchase, represented as 0. The remaining 1,908 samples (15.47%) are positive,indicating that the customer made a purchase.
  The numerical features comprise Administrative, Administrative Duration, Informational, Informational Duration, Product Related, Product Product, Bounce Rate, Exit Rate, Page Value, and Special. These features describe the different types of pages the user visited during each session and the total time spent on those pages.
  The Bounce rate reflects the percentage of visitors who enter the site and then leave without continuing further. The Exit Rate defines the number of Users who exit from a given page after reviewing the page as the last one in their session. Page Value is the average value a page has to contribute to a successful transaction.
  Special Day indicates how close the visit date is to major promotional events, such as Christmas on December 25th and New Year's Day on January 1st. This feature helps identify when most customers purchase clothing, food, and other items from the e-commerce company. The categorical features consist of operating systems, browsers, regions, traffic types, visitor types (returning visitors, new visitors), weekends, months and Revenue. A Boolean Variable value indicates whether the visit occurred on the weekend and the month of the year.

## DATA PREPROCESSING AND CLEANING

  The preprocessing phase is crucial and begins with identifying outliers to prevent potential errors. This is followed by normalisation, which transforms categorical variables into numerical ones.
  Preprocessing is often the most time-intensive part of model development, yet it is essential in ensuring reliable outcomes. Unprocessed data can lead to misleading predictions. Within the dataset, certain columns, such as month, visitor type, and weekend, contain categorical data, while others are numerical. One-hot encoding converts categorical features into a numerical format.
  Additionally, to maintain data integrity, we addressed missing values by filling them with the most frequently occurring values, thereby avoiding data loss, especially for zero-labeled revenue rows (Agustyaningrum, et al., 2021)
  We have gathered a total of 12,330 entries, after eliminating the duplicates, the total number of records was reduced to 12205, resulting in the removal of 125 duplicate entries. The data preparation phase begins with selecting the relevant attributes whose data types will be adjusted. After this selection, 
we Perform data cleaning by checking for missing values, removing duplicate entries, identifying inconsistencies, and correcting errors.

##   EXPLORATORY DATA ANALYSIS (EDA)

   Exploratory Data Analysis (EDA) aims to uncover patterns and relationships in e-commerce datasets to provide better insights into customer behaviour and website usage. The analysis includes statistical measures and distributive statistics, including mean, median, mode, standard deviation, 
minimum, and maximum values.
  ProductRelated_Duration has the highest mean value of 1194.746220, while Bounce Rates have 
the lowest mean at 0.022191. The standard deviation for ProductRelated_Duration is the highest at 1913.669288 indicating significant variability in how long customers engage with product pages.

 ##    FEATURE SELECTION

   In the Random Forest Classifier model, the most influential feature is Page Values, with an importance score of 39%. This suggests that the monetary value attributed to each page plays a key role in driving revenue. Next, Product Related_Duration and Exit Rates share an equal importance score of 
9%.
    In the Logistic Regression model, the Akaike Information Criterion (AIC) was calculated at 7361.8, and the Bayesian Information Criterion (BIC) was 7487.9, suggesting a good fit while reducing the number of features included. Page Values was the strongest predictor, with a p-value of less than 5.090279e-254, indicating a statistically significant relationship. Other significant predictors included ProductRelated_Duration (p_value= 3.721492e-02) and Exit Rates (p-value = 1.100523e-10).
    The Decision Trees model also identified Page Values as the most important variable, selecting that feature for the first split. Bounce Rates, Month, and ProductRelated_Duration became important variables affecting the revenue, showing how seasonality and user engagement metrics influence purchase decisions.
  The Gradient Boosting Classifier identified Page Values as the most influential feature, with the highest importance score of 7.46%, Bounce Rates of 4.27% and Month of 4.69%. These features contribute significantly to the model's predictions, with Page Values being the most important factor.