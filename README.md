# Telco Customer Churn
Churn prediction refers to the analytical process of identifying customers who are more likely to discontinue using a service or terminate their subscription. Anticipating customer churn is crucial as acquiring new customers entails higher costs than retaining existing ones. Upon identifying the customers with the highest propensity to churn, we can devise targeted marketing strategies aimed at increasing the likelihood of customer retention.

## Objective
Predict customer churn and examine the underlying factors that contribute to churn within the company. Our approach will involve applying different classification modeling techniques, such as logistic regression, random forest, and XGBoost, to achieve this goal

## Data Understanding
1. customerID: An identification number assigned to each customer.
2. gender: Indicates the gender of the customer.
3. SeniorCitizen: Identifies if the customer is a senior citizen or not (1, 0).
4. Partner: Indicates if the customer has a partner or not (Yes, No).
5. Dependents: Indicates if the customer has dependents or not (Yes, No).
6. tenure: The duration, in months, for which the customer has been a client of the company.
7. PhoneService: Indicates if the customer has availed phone service or not (Yes, No).
8. MultipleLines: Indicates if the customer has multiple lines or not (Yes, No, No phone service).
9. InternetService: Indicates the type of internet service the customer is availing (DSL, Fiber optic, No).
10. OnlineSecurity: Indicates if the customer has online security or not (Yes, No, No internet service).
11. OnlineBackup: Indicates if the customer has online backup or not (Yes, No, No internet service).
12. DeviceProtection: Indicates if the customer has device protection or not (Yes, No, No internet service).
13. TechSupport: Indicates if the customer has tech support or not (Yes, No, No internet service).
14. StreamingTV: Indicates if the customer has streaming TV service or not (Yes, No, No internet service).
15. StreamingMovies: Indicates if the customer has streaming movies service or not (Yes, No, No internet service).
16. Contract: Indicates the type of contract the customer has (Month-to-month, One year, Two year).
17. PaperlessBilling: Indicates if the customer uses paperless billing or not (Yes, No).
18. PaymentMethod: Indicates the type of payment method the customer uses (Electronic check, Mailed check, Bank transfer (automatic), and Credit card (automatic)).
19. MonthlyCharges: Indicates the monthly charges paid by the customer.
20. TotalCharges: Indicates the total charges paid by the customer.
21. Churn: Our target feature that indicates if the customer has churned or not (Yes, No).

## Methods
In order to create our classification model, we plan to employ several techniques, including the use of both random forest algorithms, both with and without the implementation of SMOTE (Synthetic Minority Oversampling Technique), as well as XGBoost. However, due to the uneven distribution of our feature targets, we cannot rely on accuracy as an appropriate evaluation metric. Instead, we will be utilizing recall (sensitivity) as our metric of choice, as we are primarily interested in identifying those customers who are most likely to churn

## Conclusion

1. The data appears to be relatively clean, with no major issues such as null values or duplicated rows.
2. The minimum and maximum values for each column seem reasonable overall.
3. Most columns with continuous numerical values display asymmetry.
4. No numerical columns contain outliers based on the boxplot analysis.
5. There is an imbalance in the distribution of the target variable, with "churn = No" being more frequent in the dataset.
6. Most customers use phone and internet services, but only a small percentage subscribe to additional services. 7. Online Security and Online Backup have a good number of subscribers.
8. Based on the bar charts, `gender` does not appear to be a significant factor in churn rate. However, several customer tendencies are associated with a higher likelihood of churn, including: no partner or dependents, using fiber optic internet and phone service, not subscribing to additional services, having a month-to-month contract, choosing paperless billing, and using electronic checks.
9. The correlation heatmap indicates that `tenure` is highly correlated with `TotalCharges`, while `MonthlyCharges` and "`TotalCharges` appear somewhat correlated with each other, but with a correlation coefficient less than 0.8.
10. Based on the pair plot, non-senior citizens are more likely to churn. Customers with shorter tenure are also more likely to churn. Customers with lower `MonthlyCharges` are more likely to stay, while those with higher `MonthlyCharges` are more likely to churn. Finally, customers with lower `TotalCharges` are more likely to churn.
11. Upon conducting the modeling analysis, it has become evident that **XGBoost proves to be the most suitable model for imbalanced data**. However, it is crucial to note that feature selection has not yet been implemented in this analysis. Feature selection is an essential process that involves the selection of relevant features that significantly impact the dataset. Incorporating feature selection in the analysis could potentially enhance the overall outcome.
