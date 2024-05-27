![header](header.png)

## **About the Company**

---
SnM Corp is a fictitious SaaS company selling sales and marketing software to other companies (B2B) via AWS with revenue less than $1 million/year. SnM corp was founded in 2020 and has 99 customers from several different countries and industries.

<aside>

💡 **SaaS:** How does software as a service work?
SaaS works through the cloud delivery model. A software provider will either host the application and related data using its own servers, databases, networking and computing resources, or it may be an ISV that contracts a cloud provider to host the application in the provider's data center. The application will be accessible to any device with a network connection. SaaS applications are typically accessed via web browsers.

</aside>

## **Business Context and Task**

Analyzing sales performance is crucial for businesse regardless of their scale. By understanding revenue-driving metrics, companies can make measurable decisions, from pricing, product development, marketing stategies etc. A company growth rate measures specific variables associated with growth over a specific period and is expressed as a percentage. The variables are industry-specific, meaning they differ from one company to another. Company growth rate formula can be applied to any metrics such as revenue, profit, user aqcuisition, and compound annual growth rates (CAGR). Different industries have different growth rates and benchmarks, the average of CAGR in revenue for Software (System & Application) sector is 15,9% and for profit is 16,04% [link](https://pages.stern.nyu.edu/~adamodar/New_Home_Page/datafile/histgr.html). 

Another important metric for sales performance analysis is profit margins. Profit margins serves as essential indicator of a company's financial health and viability, it expressed as a percentage, represents the portion of a company’s sales revenue that it gets to keep as a profit, after subtracting all of its costs. Benchmark of profit margin for Software (System & Application) sector is 19,14% [link](https://pages.stern.nyu.edu/~adamodar/New_Home_Page/datafile/margin.html). 


The marketing manager ask data analyst team to provide analysis about company's growth and data supporting to enhance business growth.

To fulfill the goals we need to answer some question?
1. How is company sales performance and growth?
2. Stategies to improve sales?
3. Stategies to maximize profit margins?

## **Data**
---
This analisys uses dataset that contains transaction data from a fictitious SaaS company selling sales and marketing software to other companies (B2B), here is the original database from [source](https://www.kaggle.com/datasets/nnthanh101/aws-saas-sales), you can also access this data in [link](https://github.com/zuhririzqi/SnM-SaaS-Company/blob/main/data/SaaS-Sales.csv).

## **Conclusion and Recomendation**

After completing data analysis, there are some conclusion and reccomendation:

#### **Conclusion**

1. CAGR in sales and profit margins from 2020-2023 of SnM Company still below industry standart. Company should achive 1 million sales/year and increasing profit margin to 19% to achive the industry standart, total customer stagnant from 2020-2023.
2. Different region have their own top industry with highest CLV, but Contact Matcher and Support dominating as top product across the region and industry.
3. Value of applied discount in the transaction played important rule to profit margin value. Products with more than 30% High Discount Group apllied from all transaction, has profit margins 3% to -3%.


#### **Recomendation**

To achive 1 million dollar sales in 2024 and increasing profit margins by 6% per year, there are some actionable reccomendation based on the data:

1. **Sales**
    - Targeted and personalized promotion to customers with high CLV values based on industry. With the same marketing funds, instead of doing same marketing campaign to all of customer, targeted marketing expected to gain more sales, because higher CLV means higher expected sales.
    - Developing some new feature especially top product (Contact Matcher and Support). Developing some feature in top product will be more cost and time beneficial, instead of developing all product.
    - Try to expand market to gain new customer. There is no addition number of customer from 2020 to 2023, gaining new customer will help to improve sales.


2. **Profit Margins**
    - Limiting discount applied to transaction.
    - Evaluating strategies for pricing, valuing, and promoting products for Contact Matcher.
    - Eliminating low-performing products (Big Ol Database and Marketing Suite)


## Instalastion

To get this project, you can clone it by running the following code:

    git clone git@github.com:zuhririzqi/SnM-SaaS-Company.git


##  Project Organization

The directory structure of this project looks like this:


        ├── readme.md               -- The top-level README for developers using this project.
        ├── data
        │   ├── SaaS-Sales.csv      -- Original dataset
        │   └── data_clean.xlsx     -- Dataset that already cleaned
        ├── docs                    -- Detailed Presentation
        ├── notebook 
        │   └── SaaS Analysis.ipynb -- Notebook containing data analysis
        └── requirements.txt        -- The requirements file for reproducing the analysis environment

## Contribute

If you want to give some feedback please contact me on linkedIn [link](https://www.linkedin.com/in/rizqi-rahmadani-zuhri-saputri/)


## Tableau
You can also find the dashboard related to this analysis in this [link](https://public.tableau.com/app/profile/rizqi.rahmadani.zuhri.saputri/viz/SaaSAnalysis_17140247377000/DashGrow?publish=yes)

## NBViewer
Because github limitation the graph in notebook can't be view directly, you can view it directly in this [link](https://nbviewer.org/github/zuhririzqi/SnM-SaaS-Company/blob/main/notebook/SaaS%20Analysis.ipynb)