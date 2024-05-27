![header](header.png)

## **1. Business Problem Understanding**

### **Context:**
A subscription business model is a recurring revenue model in which customers pay a weekly, monthly, or yearly fee in exchange for products or services. Customers can renew their subscription after a certain period of time. This business model really depend on recurring revenue, monthly recurring revenue (MRR) is the lifeblood of the subscription business. Without predictable sources of revenue, it’s impossible to sustain business over the long-term. On the flip side, it’s critical to track churned MRR to assess how customer attrition affects the revenue. If business losing customers too quickly, it can seriously hurt business ability to grow.


### **Problem Statement:**
Customer churn (or customer attrition) refers to the loss of customers or subscribers for any reason at all, businesses measure and track churn as a percentage of lost customers compared to total number of customers over a given time period. Based on the historical data, Telco has a relatively high rate of customer churn, almost 30%. If this continues, the company will keep losing recurring revenue and it will also affect the company's ability to grow. Additionally, the company will spend more funds to acquire new customers, because according to Harvard Business Review, converting a first-time customer is 5 to 25 times more expensive than keeping an existing one. A significant reduction in churn rate makes your business more profitable because you’re able to keep most subscribers within your customer base.

Problem: There haven't been any effective preventive strategies taken yet to prevent customers from leaving the company.

**Stakeholders** : Marketing Manager

### **Goals**
As data scientist we try to help the company in identifying warning signs of customer churn in order to `reduce the risk of losing recurring revenue by 80%`. With answering some questions:
   
    - What are the characteristics of customers who left the service?
    - How can the company predict the chances of customers churning?
    - What factors influence the chances of customers leaving the company?

This enables company to proactively implement targeted retention strategies, significantly lowering the chances of customers leaving and thus, effectively reducing future churn rates.



### **Analytical Approach:**

Here are the steps of analysis we will undertake:

* __Step-1:__ Perform Exploratory Data Analysis (EDA) to discover the behavior of customers who leave the company.
* __Step-2:__ Build a classification model based on behavioral analysis to predict the chances of customers leaving the company.
* __Step-3:__ Identify the factors that contribute to customers' chances of leaving the company.
* __Step-4:__ Develop a scheme/strategy simulated to reduce the chances of customers leaving the company (churn rate). 

The analysis results will be accessible to stakeholders through a dedicated platform (Web/Mobile) whenever targeted retention strategies are to be implemented. The workflow is as follows:

1. Stakeholders input customer data.
2. The system provides a list of customers with high potential to leave the company.
3. Stakeholders use the analysis results to implement targeted retention strategies.


### **Metric Evaluation:**

This analysis will focus on customers who have left the company. The targets are defined as follows:

- **0:** Indicates customers who did not leave the company.
- **1:** Indicates customers who left the company.

Ensuring the accuracy of the model is crucial to avoid the financial impact of classification errors (false positives or false negatives).

| **Error Type**     |**Explanation** | **Consequences** | 
|-----------------|------------|----------------|
| **False Positive / Type 1 Error**  | The model incorrectly predicts that the customer will leave the company, when in fact they will not | The company will incur unnecessary marketing expenses by targeting loyal customers |
| **False Negative / Type 2 Error**  | This happens when the model incorrectly predicts that the customer will not leave the company when, in fact, they will | The company will lose recurring revenue and spends more funds to acquire new customers| 

We will conduct simulations to get an overview of the consequences of each type of error using the following facts:
- Median of monthly charges (recuring revenue) around $70,35 per customer
- Median of tenure (customer lifespan) for all customers around 29 month and for the churned is 9 month
- Average customer acquisition cost (CAC) for telecomunication industry is $694 per-customer [source](https://userpilot.com/blog/average-customer-acquisition-cost/)
- Retention cost for SaaS company 4-5 times smaller than CAC [source](https://www.forbes.com/sites/forbesbusinesscouncil/2022/12/12/customer-retention-versus-customer-acquisition/?sh=2c41201c1c7d)

**Type 1 Error Simulation**

Retention Cost= ($694/4)= $173,5 per Customer

**Type 2 Error Simulation**

Losing Customer Lifetime Value = Recurring Revenue x Diff Customer Lifespan = $70,35x(29-9)= $1407

Losing Customer Lifetime Value + Customer Acquisition Cost= $1407 + $694= $2101 per Customer

Note: This costs are an estimated result based on the average of the same industry, this value can be smaller or larger depending on other factors that influenced each company.


## **2. Data Understanding**

### **About the Dataset**
The dataset represents customer profiles who have left the telco company. A churn in telco and other subscription-based services means a situation when the customer leaves the service provider.

### **Data Attribute: Target & Features**

The main goal of this machine learning development is to classify customers who will leave the company or not.

| Target | Data Type | Description |
| --- | --- | --- |
| Churn | String | Whether the customer churns or not |

In machine learning, a feature refers to an individual measurable property or characteristic of a phenomenon being observed. Features are essentially variables or attributes that are used as inputs to a machine learning model to make predictions or decisions.

| Feature | Data Type | Description |
| --- | --- | --- |
| Dependents| String | Whether the customer has dependents or not |
| Tenure | Integer | How long customer using the services (customer lifetime) |
| OnlineSecurity | String | Whether the customer has online security or not |
| OnlineBackup | String | Whether the customer has online backup or not |
| InternetService | String | Whether the client is subscribed to Internet service |
| DeviceProtection | String | Whether the client has device protection or not |
| TechSupport | String | Whether the client has tech support or not |
| Contract | String | Type of contract according to duration |
| PaperlessBilling | String | Bills issued in paperless form |
| MonthlyCharges| Float | How much customer pay for services each month|



## **Conclusion and Recomendation**

After completing data analysis, there are some conclusion and reccomendation:

#### **Conclusion**
1. Main metric, the main metric used in building machine learning models this time is the F4 score, because the impact of false negatives is far greater than false positives.

2. The best model used is using Quadratic Discriminant Analysis (QDA) with hyperparameter tuning on priors (0.3,0.7) and using a probability threshold of 0.4.

3. Model Evaluation, based on the results of model evaluation on train and validation data, the model has worked quite well as seen from no significant overfitting or underfitting tendencies. Calibration results show that the model is effective in predicting high probabilities for positive outcomes but struggles with consistency across the full range.

4. Model Intrepetation

    a. Model Limitation

     - `Dependents` : Type dependents No/Yes only
     - `Tenure`: Tenure between 0-72 months
     - `Internet Service`: Type of internet service used by customer only Fiber Optic, DSL, or none
     - `Contract`: There are only 3 contract types: Month-to-month, One Year, and Two Year.
     - `Paperless Billing`: Type of billing is only Yes and No
     - `Monthly Charge`: Monthly charge ranges from $18.8-$118.6

    b. Feature Importance

     The feature that most affects the performance of the model (seen from the decrease in F4) is `Contract` selected by the customer, followed by `Monthly Charges` and the type of `Internet Service`.

    c. Model Works Best
        - The model works well when the predicted probabilities range between 0.0426-0.4042 and 0.4646-0.6454.
        - The model works less well when the predicted probabilities range between 0.4046-0.4643.

5.Model Impact

 - Using machine learning, the total cost incurred by the company is $132,741.5
 - Without using machine learning, the total cost incurred by the company to retain all customers is $168,468.
 - The company is able to save costs around `$35,727` or about `20%` by using machine learning, in addition to using machine learning has successfully predicted correctly `93%` of customers who actually churn.

#### **Recomendation**

- Some recommendations for retention strategies to minimize customer churn:
1. Loyalty Programs
    Offering rewards and incentives for customers who choose One Year or Two Year Contract, so as to attract customers to choose a longer contract type and minimize the possibility of churn.
2. Cost Evaluation to Fiber Optic Internet service
    The high monthly charge for consumers who use fiber optic as an internet service is one of the factors that make customers churn, therefore another evaluation of the price for this service is needed.
3. In general, improve service quality, customer service, and periodically reach out to customers in order to measure customer satisfaction in using services from the company.


- Recommendations on improving machine learning models
1. Selection of methods that are robust to multicollinearity so that they can cover more features.
2. Collect more data to minimize the imbalance between classes
3. Collecting more personalized customer data such as age, gender, so that it can be more detailed in conducting churn analysis.
4. Conduct a periodic evaluation of the model that has been created.

## Instalastion

To get this project, you can clone it by running the following code:

    git clone git@github.com:zuhririzqi/Telco-Customer-Churn.git


##  Project Organization

The directory structure of this project looks like this:


        ├── readme.md                                   -- The top-level README for developers using this project.
        ├── data
        │   ├── Telco Customer Churn.docx               -- Dataset explaination
        │   ├── data_telco_customer_churn.csv           -- Original Dataset
        │   ├── df_seen.csv                             -- Data Train
        │   └── df_unseen.csv                           -- Data Test
        ├── model
        │   └── Deployment_27052024.pkl                 -- Model 
        ├── notebook
        │   └── Telco Customer Churn Analysis.ipynb     -- Notebook containing data analysis and experiment                           
        ├── requirements.txt                            -- The requirements file for reproducing the analysis environment


## Contribute

If you want to give some feedback please contact me on linkedIn [link](https://www.linkedin.com/in/rizqi-rahmadani-zuhri-saputri/)
