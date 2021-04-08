# Telecom Customer churn prediction

Medium blog: https://towardsdatascience.com/churn-prediction-using-neural-networks-and-ml-models-c817aadb7057

## Introduction
Customer attrition or customer churn occurs when customers or subscribers stop doing business with a company or service. Customer churn is a critical metric because it is much more cost effective to retain existing customers than it is to acquire new customers as it saves cost of sales and marketing. Customer retention is more cost-effective as you’ve already earned the trust and loyalty of existing customers.

There are various ways to calculate this metric as churn rate may represent the total number of customers lost, the percentage of customers lost compared to the company’s total customer count, the value of recurring business lost, or the percent of recurring value lost. However in this dataset, it is defined as a binary variable for each customer and calculating the rate is not the objective. The concept of the churn rate indicates there are factors which influence it and thus the objective here is to identify and quantify those factors.

I had come across this data analysis as part of an assignment for a online recruitment drive and it had to completed in 12 hours. Thus, it is a fairly easy and beginner level project with fewer variables. Since then I have decided to use a nueral network for prediction too.

## Results

Several Machine Learning models were applied and one neural network model using Keras was applied.
## Logistic Regression
ROC AUC 
![image](https://user-images.githubusercontent.com/66875776/113900669-b05fff00-9793-11eb-8cdf-d3248db9ccf1.png)
Predicted NO  Predicted YES
Actual NO      65.799204       7.622298
Actual YES     12.044937      14.533561

Feature importance according to Logistic Regression.
![image](https://user-images.githubusercontent.com/66875776/113955343-29d20e80-97e1-11eb-9683-c4b6fa50c9ec.png)
![image](https://user-images.githubusercontent.com/66875776/113955370-348ca380-97e1-11eb-9f5f-30bd1c09bfee.png)



## Neural Network model 
A 64-8-1 dense layered model with a decaying learning rate of batch size 32 is used.
![image](https://user-images.githubusercontent.com/66875776/113955096-b8925b80-97e0-11eb-9c11-bbb8c963be0c.png)
Neural Network:
               precision    recall  f1-score   support

         0.0       0.90      0.84      0.87      2362
         1.0       0.55      0.66      0.60       677

    accuracy                           0.80      3039
   macro avg       0.72      0.75      0.73      3039
weighted avg       0.82      0.80      0.81      3039


            Predicted NO  Predicted YES
Actual NO           1995            367
Actual YES           232            445

Neural Network Feature importance using eli5 library
![image](https://user-images.githubusercontent.com/66875776/113955593-ab29a100-97e1-11eb-8a1d-e8e974b35eab.png)

## Conclusion
Conclusion
It can be seen Total charges is the most important feature and rightfully so. The number one reason customers will 'churn' if they find the service to be expensive or unaffordable.
Tenure is also important, the customers who have been using the sevice for a long time or have long time contracts, which are cheaper in general, are less likely to churn. It is interesting to observe that Tenure is listed as more important for neural network model.
As observed in the EDA, most customers who are on month to month contracts are more likely to churn. Itcan be hypothesized that the reason is to be attributed to personal reasons of customers to have reservations about long term contracts or higher costs per unit time resulting from monthly contracts.
As seen in EDA, other important features are online security, electronic payment method, fiber optic internet service, tech support.
The features which are not important are gender, dependents, partner, streaming TV, backup and device protection.
Offers and improving churn rate:

Discounts: As the most important feature is total charges, followed by monthly charges, potential churners identified through the modelling should be offered huge discount on next month or months contract. This covers 80 % of the reasons identified for churning. For this modelling, the False Negative Rate should be minimised or Recall should be maximised so that the discounts are sent to maximum of the potential churners.
New contract: A six month or four month contract should be implemented. This will encourage the reserved customers who want shorter contracts and will increase their tenure on the service thus making them less likely to churn.
Online Security: This service should be promoted more and offered complimentary/free for trial periods depending on cost to company. The customers who do not have online security are more likely to churn and thus this offer could be combined with the first one mentioned and discount could only be offered on this.
Fiber optic: The fiber optic internet is costly and thus should either be promoted to appropriate target audience or better technology can be implemented to cut cost on this service. Ultimately the market research team has to decide the break even point for this service, whether it is profiting as much as the loss of customers it is causing.
Select services discounting: In addition to offering disounts on next month contract, discounts can be offered on important services to potential churners. These services include discount on online security, tech support, DSL internet, electronic checks and potentially streaming movies.
After these actions are implemented the modelling using newer data needs to performed and analyze the improvements. Another method to quantify the offers to be made is using manually generated features and their effect on the model.

References
Random Forest vs Neural Networks for Predicting Customer Churn, Abhinav Sagar, Medium,https://towardsdatascience.com/random-forest-vs-neural-networks-for-predicting-customer-churn-691666c7431e

Using basic neural networks to predict churn, Laurier Mantel, https://www.kaggle.com/lauriermantel/using-basic-neural-networks-to-predict-churn

How to Use ROC Curves and Precision-Recall Curves for Classification in Python, Jason Brownlee, https://machinelearningmastery.com/roc-curves-and-precision-recall-curves-for-classification-in-python/

Tensorflow, Keras,sklearn documentation

Feature importance of Neural Network,StackOverFlow, https://stackoverflow.com/questions/45361559/feature-importance-chart-in-neural-network-using-keras-in-python#:~:text=It%20most%20easily%20works%20with,using%20it%20is%20very%20straightforward.&text=At%20t
