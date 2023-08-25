# Bank — Customer Churn Analysis

## Used tools: 
* `pandas`
* `matplotlib`
* `seaborn`
* `numpy`
* `scipy`
* `datetime`
* `math`
* `plotly`

## Project description

**Client** - regional bank "Metanprom," which is facing a crisis due to the critical mass of customer churn.

The client has access to a dataset with anonymized user data.

**Dataset Columns:**
* `userid` - user identifier,
* `score` - credit scoring points,
* `City` - city,
* `Gender` - gender,
* `Age` - age,
* `Objects` - number of owned objects,
* `Balance` - account balance,
* `Products` - number of products used by the client,
* `CreditCard` - presence of a credit card (yes/no),
* `Loyalty` - active client (yes/no),
* `estimated_salary` - estimated salary of the client,
* `Churn` - churn status (whether the client left or not).

## Task description

**Task:** Conduct an analysis of customers of the regional bank and **identify segments** (profiles of groups defined by 2-3 features) of customers who are prone to churn from the bank's services.

**Results:** Prepare a presentation and dashboard that can demonstrate the research findings effectively.

## Overall conclusion
**As a result of in-depth (exploratory) data analysis, the following observations have been made:**

1. An evident observation regarding customer churn is the age group above 38 years.
2. Clients using 1, 3, or 4 products have churn rates of 27.71%, 82.71%, and 100% respectively.
3. The number of properties owned does not affect churn.
4. Customers from Rostov Veliky are almost twice as likely to churn compared to those from Rybinsk or Yaroslavl (32.44% vs. 16.67% and 16.15% respectively).
5. Women are slightly more prone to churn, with a churn rate of 25% compared to 16.46% for men.
6. Inactive clients have a churn rate of 26.85%, while active clients have a rate of 14.27%.
7. The presence of a credit card does not affect churn.

**Based on the results of the exploratory data analysis, the following segments with the highest churn rates were identified:**

**First Segment:** Clients using 1, 3, or 4 products, aged 39 or older.

**Second Segment:** Women from the city of Rostov Veliky.

**Third Segment:** Inactive clients aged 37 and older.

Thus, by implementing specific actions (recommendations provided below) to retain customers in these identified churn-prone segments, **it is possible to retain up to 16.16% of the customers**, despite the overall average churn rate being 20.37%.

## Materials

* [Dashboard](https://public.tableau.com/views/Project_final_16857298399680/Dashboard1?:language=en-GB&publish=yes&:display_count=n&:origin=viz_share_link)
* [Presentation](https://drive.google.com/file/d/1wbxudKwBe4zeTKiBVdaJNGwZCV5TbwQB/view?usp=sharing)

