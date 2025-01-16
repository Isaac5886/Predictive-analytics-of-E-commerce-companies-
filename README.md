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

## TRAINING AND TESTING SET 

 The Random Forest model achieved the highest training accuracy of 100%, suggesting it learned the underlying patterns in the training data. Its testing accuracy of 89.5% demonstrates a strong ability to generalise to unseen data.
  In contrast,the Support Vector Machine displayed the lowest performance, with training and testing acuracy of 85.3% and 83.4% respectively. Both Random Forest Classifier and Decision tree models exhibited perfect training accuracy, suggesting they can fit the training data exceedingly well. However, Decision trees have lower testing accuracy with Random forest classifiers raising concerns 
about overfitting. 

   
1. Random Forest Classifier have a training set of 1.0 and testing set of 0.8956

2. Decision Tree have a training set of 1.0 and testing set of 0.8627

3. Support Vector Machine have a training set of 0.8525 and testing set of 0.8340

4. Logistic Regression have a training set of 0.8883 and testing set of 0.8719

5. Gradient Boosting Classifier have a training set of 0.9239 and testing set of 0.8927

 ##    FEATURE SELECTION

   In the Random Forest Classifier model, the most influential feature is Page Values, with an importance score of 39%. This suggests that the monetary value attributed to each page plays a key role in driving revenue. Next, Product Related_Duration and Exit Rates share an equal importance score of 
9%.
    In the Logistic Regression model, the Akaike Information Criterion (AIC) was calculated at 7361.8, and the Bayesian Information Criterion (BIC) was 7487.9, suggesting a good fit while reducing the number of features included. Page Values was the strongest predictor, with a p-value of less than 5.090279e-254, indicating a statistically significant relationship. Other significant predictors included ProductRelated_Duration (p_value= 3.721492e-02) and Exit Rates (p-value = 1.100523e-10).
    The Decision Trees model also identified Page Values as the most important variable, selecting that feature for the first split. Bounce Rates, Month, and ProductRelated_Duration became important variables affecting the revenue, showing how seasonality and user engagement metrics influence purchase decisions.
  The Gradient Boosting Classifier identified Page Values as the most influential feature, with the highest importance score of 7.46%, Bounce Rates of 4.27% and Month of 4.69%. These features contribute significantly to the model's predictions, with Page Values being the most important factor.

## CLASSIFICATION AND CONFUSION MATRIX

# 1. Random Forest Classifier:
 
 The Random Forest Classifier model scored the highest accuracy at 90%, demonstrating 
excellent performance in correctly classifying non-purchasing customers, with a precision of 0.92 and a recall of 0.96. For the purchasing class, it showed improved precision values of 0.75 and had a recall of 0.57.
  The F1 score of 0.65 indicates that the Random Forest Classifier model balances precision and recall for the purchasing class, making it a strong candidate for deployment. This model enhances overall performance by capturing complex relationships among features by combining models.

# 2. Decision Tree: 
  The Decision Tree model shows an accuracy of 86%, which is slightly lower than Logistic 
Regression. It reaches the high precision of 0.91 for the non-purchasing class, showing excellent performance in identifying customers who do not purchase. However, the recall for non-purchasing customers is slightly lower at 0.92, still reflecting good reliability.
For the purchasing class, precision is 0.60 and recall is 0.56, indicating a more balanced yet inadequate performance. The F1 score of 0.58 indicates that the model demonstrates slightly greater robustness in predicting purchases, yet it remains unsatisfactory compared to Logistic Regression. A common issue with Decision Trees is overfitting. While they can identify certain patterns in purchasing behaviour, they may also pick up noise, causing significant errors within the purchasing class. Adopting a randomised approach may help mitigate the risk of overfitting and enhance generalisation. Overall, their performance in classifying purchasing customers is relatively weak.

# 3. Logistic Regression:
 Logistic Regression yields an overall accuracy of 87%, indicating a robust ability to classify nonpurchase customers correctly, with a recall of 98%. This high recall means that the model correctly identifies 98% of the non-purchasing cases, reinforcing the model’s reliability.
 However, performance in the purchasing class raises an alarm. Given a precision of 0.75 with recall as low as 0.36, the model poorly identifies purchasers resulting in a high count of false negatives, 400 cases where purchases were incorrectly predicted as non-purchases. This large discrepancy indicates that while the model is good for non-purchasers, it may fail to capture the complexity associated with 
purchasing behaviour, potentially leading to lost sales opportunities. 

# 4. Support Vector Machine:
  The Support Vector Machine model exhibits excellent accuracy in predicting non-purchases, with a recall rate of 100%, indicating that it correctly identifies every customer who does not make a purchase. There is a failure to correctly identify the purchasing customers, as evidenced by the very low recall of 0.01 and an F1 score of only 0.03 for the purchases class.
  The Purchasing class score of 1.00 is misleading, based on 8 correct predictions out of 622 actual purchases. The model's failure to accurately predict purchases highlights a significant imbalance, resulting inhigh-quality false negatives.

# 5. Gradient Boosting Classifier:
  The Gradient Boosting Classifier achieved 89% accuracy, with a high precision of 0.92 and a 
recall of 0.96 for the non-purchase customer class. The precision for the purchasing class is 0.73, and recall is 0.57, representing the best balance between precision and recall thus far among the models compared. The F1-Score of 0.57 for the purchasing class suggest that, although it is still not ideal, the Gradient Boosting classifier is much better at recognising purchasing behaviour than the models tested so far. This improvement indicates that it captures more complex patterns in the data that may relate to 
customer behaviour and intent to purchase.

## MODEL EVALUATION AND PERFORMANCE

   The results of each model were evaluated using metrics, including Accuracy, Precision, Recall, F1-Score, and ROC-AUC. These metrics provide a comprehensive view of model performance in predicting customer behaviour.

1. Logistic Regression has an accuracy of 87.2% but struggled with a recall of only 0.3569, indicating significant missed purchases, as reflected in its F1-score of 0.4837.

2.  The Random Forest Classifier model achieved an accuracy of 89.6%, a precision score of 0.7489, and a balanced F1-score of 0.6478, indicates effective identification of positive cases while minimising false positives.

3.  The Decision Trees model achieved an accuracy of 86.3% but faced difficulties with lower precision and recall, indicating problems with false positives and false negatives

4. The Support Vector Machine exhibited the highest precision of 100% but had a poor recall of 0.0129, indicating severe limitations in identifying actual purchases.

5. The Gradient Boosting Classifier showed strong performance, achieving an accuracy of 89.3% and recall of 0.5723, enabling it to identify more positive cases than Logistic Regression.

## RECEIVER OPERATING CHARACTERISTIC - AREA UNDER CURVE (ROC - AUC)

  The ROC-AUC (Receiver Operating Characteristic - Area Under Curve) is an analytical tool designed to evaluate the performance of a classification model by depicting the relationship between the True Positive Rate and the False Positive Rate. The AUC evaluates how well the model can accurately classify positive and negative instances.
  The AUC values of the models analysed indicate that the Gradient Boosting Classifier has an AUC of 0.92, represented in blue. Logistic Regression has an AUC of 0.88, shown in red. The Support Vector Machine has an AUC of 0.80, indicated in black. The Decision Tree Classifier has an AUC of 0.74, represented in green, while the Random Forest has an AUC of 0.92, also shown in pink.
  Gradient Boosting and Random Forest classifiers demonstrate exceptional results, achieving an AUC of 0.92. This indicates strong performance in accurately identifying purchasing customers while minimising false positives, which is crucial for effective marketing strategies.
  Logistic Regression follows with an AUC of 0.88, indicating solid performance but also room for improvement. It effectively predicts many purchases, though perhaps with minor enhancements needed for certain segments.
  The Support Vector Machine achieved a reasonable AUC of 0.80; however, this score suggests a higher likelihood of misclassifying purchases. Such misclassifications might lead to missed opportunities for interaction since potential customers may not be targeted effectively.
  The Decision Tree Classifier has the lowest AUC of 0.74 and struggles to distinguish between classes. Its performance can lead to a higher rate of false positives and false negatives, making marketing efforts ineffective.
  For the e-commerce company, an AUC value above 0.80 is considered good, while values 
exceeding 0.90 are excellent. In this context, it is evident that the Gradient Boosting Classifier performs well, whereas the Decision Tree Classifier needs improvement for better classification.

## CONCLUSION

  This research addressed critical operational issues of the e-commerce companies was discussed and decision-making was enhanced through predictive analysis. The models consistently highlighted the importance of Page Values in driving revenue. The Logistic Regression model provides insights into feature relationships, while the Decision Trees model demonstrates the impact of seasonality and 
user engagement metrics. The Gradient Boosting Classifier identified Page Values as the dominant factor.
  The possibility of customer purchasing was studied; it was found that Random Forest 
constitutes some of the effective machine learning techniques for yielding much better revenue predictions. The results indicate that not all segments of visitors contributed equally to revenues and rules of behaviour, and thus need a tailored approach to marketing strategies.
  This is further supported by the evaluation of unique activities and dates, in which such events have shown a marked impact on internet site visitors and revenue normal, underlining the significance of timing for e-commerce operations. The capability of forecasting revenue trends primarily based on 
historical data and user behaviour patterns serves as the bedrock for planning long-term period business operations.
  The insights gained from these studies deal with problems like system inefficiencies and 
provide a foundation for density enhancements in operational efficiency and customer satisfaction.Imposing the encouraged strategies, including record cleaning and developing a dynamic dashboard Real-time monitoring will facilitate a proactive technique for managing customer behaviour and revenue era.
