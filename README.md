# Prepaid phone usage customer churn prediction

## Problem statement
A Wireless Company is concerned about customer retention rates and wants to know what is causing customers to switch/cancel the network provider. 
The aim of this project is to create a churn prediction model to identify the nature of customers that will churn out. Based on the analysis we provide recommendations and understand the variables that are most contributing to customer churn

## Summary of dataset
* Dataset BEFORE re-ordering: (182343,68)
* Dataset AFTER re-ordering months: (66469,187)
* Final Data (after outlier/missing values): (66469,59)
* 44 Continuous features (After removing correlations)
* 15 Categorical features
* Target Variable is Churn 
* 20.9% (Churn-1)
* 79.1% (Non-Churn-0)
### Predictor Categories across 3 months (June/July/Aug)
* User Category (user_intake,user_lifetime etc.)
* User Reload (user_does_reload count etc.)
* Call Outgoing Data (calls_outgoing_count, spendings etc.)
* SMS Outgoing Data (sms_outgoing_count, spendings etc.)
* SMS Incoming Data (sms_incoming_count, spendings etc.)
* GPRS Usage (gprs_session_count, usage, spendings)
* Last 100 Data (last_100_reloads_count,sum)
### Average Summary Statistics
* User lifetime 1100 days
* User spendings 7.58$ per month
* GPRS spendings 0.23$ per month
* SMS spendings 2.5$ per month

## Key business observations
One of the observations we identified is around 20% of the customers are churning out.
Specifically in that 20% around 10% are customers are with higher lifetime. Focusing on this set of loyal customers would be the first step.
August is the critical month where most higher lifetime customers are churning out. Higher activity is observed in June and July months than in August month. 
[Left figure] In June and July months the number of users who do not make outgoing calls, SMS, or reload are more in number than the users who make outgoing calls, SMS, or reload. 
[Right figure] In August month for outgoing calls, and reload we are seeing an inverse relationship where users who churn are showing a higher activity rate in terms of calls and recharge. 

![image](https://user-images.githubusercontent.com/82319213/218242760-3371b2f7-1f0e-4318-b813-777854641b06.png)

    
    
## Metric


For our Business, Recall is more critical than Precision. Because Recall is dependent on False Negatives. More False negatives would classify churned customers as continuing customers. Hence, we might miss the opportunity to address the problems related to them.

## Behaviours of churned customers
* Users having a high user lifetime in August month are churning out more.[A]
* For customers who are churning out, we see a decreasing trend in sms_out_going [B]
* Following are continuous variables that are contributing to higher  Churn characteristics: [C]
  * Higher 6/7_reloads_inactive_days, 8_reloads_inactive_days, 8_user_no_outgoing_activity_in_days
* Coming to the remaining variables Lower values are contributing to a higher churn rate. For example: sms_incoming_spendings, calls_outgoing_spendings [D]
* on GINI Impurity, and feature permutation technique, identified the following features in E figure are contributing more in differentiating between churned and non-churned customers [E]
![image](https://user-images.githubusercontent.com/82319213/218242897-86256238-18aa-4dfd-aec2-b7fd5c00edc1.png)

## Recommendations
![image](https://user-images.githubusercontent.com/82319213/218242904-088db40a-a883-4f6d-95e0-20fd45b77c47.png)






