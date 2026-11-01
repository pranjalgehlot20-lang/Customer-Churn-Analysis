📊 Customer Churn Analysis | Python & SQLite

1. Project Overview

Customer churn is a major challenge for subscription-based businesses. Losing subscribers affects recurring revenue, customer lifetime value and long-term business growth.

This project analyses customer, subscription and customer-support data from an OTT-style subscription business to understand who is churning, why customers may be leaving, when churn occurs, and how businesses can improve retention.

Using Python, SQLite and data visualisation libraries, the project explores customer behaviour, subscription patterns, revenue exposure and support interactions.

2. Business Objectives — What & Why?

The analysis focuses on five key business objectives:

* Measure customer churn: Understand the proportion of customers who have cancelled their subscriptions.
* Identify high-risk segments: Determine which subscription plans and customer groups experience higher churn.
* Understand revenue impact: Estimate recurring revenue exposed to customer cancellations.
* Analyse customer support: Explore whether complaints and escalations are associated with churn.
* Support retention decisions: Identify areas where businesses should prioritise customer-retention efforts.

3. Dataset & Database Structure

The project uses a SQLite database named customer_churn.db, containing three relational tables.

1. db_customer — Customer Information

* Customer ID and name
* Country and state
* Gender and date of birth
* Customer interests and pincode

2. db_subscription — Subscription Information

* Subscription start and renewal dates
* Subscription source and plan type
* Contract type
* Cancellation date and reason
* Monthly charges
* Customer Lifetime Value (CLTV)
* Churn score

3. db_support — Customer Support Information

* Complaint date
* Escalation status
* Customer Satisfaction (CSAT) score
* Customer comments

The tables are connected using customerid to analyse customer behaviour across different business dimensions.

4. Tools & Technologies

* Python: Overall analysis and data processing
* SQLite & sqlite3: Database connection and data extraction
* Pandas: Data cleaning, transformation and aggregation
* NumPy: Feature engineering and numerical operations
* Matplotlib: Data visualisation
* Seaborn: Statistical visualisation and correlation analysis

5. Analytical Approach — How?

The project follows an end-to-end data analysis workflow.

Step 1: Database Connection & Data Extraction

* Connected Python to SQLite using sqlite3.
* Retrieved database tables using SQL queries.
* Loaded relational data into separate Pandas DataFrames.

Step 2: Data Cleaning

* Inspected data types and missing values.
* Renamed columns and removed unnecessary fields.
* Converted date columns into appropriate datetime formats.
* Standardised inconsistent gender values.
* Handled missing country values using available state information.
* Removed unnecessary columns from the support dataset.

Step 3: Feature Engineering

Created additional analytical variables:

* Churn Flag: Identified churned customers using cancellation dates.
* Customer Tenure: Calculated the number of days customers remained subscribed.
* Complaint Count: Calculated complaints associated with each customer.
* Churn Risk: Categorised customers into Low, Medium and High risk using churn scores.
* Cancellation Month: Extracted the cancellation month for time-based analysis.

Step 4: Data Integration

* Merged customer, subscription and support datasets using customerid.
* Addressed duplicate customer records in the support table before merging.
* Prepared a consolidated dataset for analysis.

Step 5: Exploratory Data Analysis

Calculated key business metrics and examined churn across different dimensions.

Step 6: Data Visualisation

Created visualisations to understand:

* Monthly churn trends.
* Churn rates by subscription plan.
* Churn distribution across states.
* Correlations between selected numerical and encoded variables.
* Relationships between customer segments and subscription charges.

6. Key Business Questions

The analysis addresses the following questions:

1. What is the overall customer churn rate?
2. What percentage of customers are retained?
3. Which subscription plan experiences the highest churn?
4. How does churn vary across geographical regions?
5. What is the average revenue per user (ARPU)?
6. What is the average customer subscription tenure?
7. How much monthly revenue is exposed to customer cancellations?
8. What proportion of customers have escalated support interactions?
9. How frequently do customers raise complaints?
10. Is there an association between support escalations and customer churn?
11. How can customers be segmented based on churn risk?

7. Key Findings — What Did the Analysis Reveal?

The following findings are taken from the executed Python notebook.

Overall Customer Churn

* Total customers analysed: 21
* Churn rate: 28.57%
* Retention rate: 71.43%

Approximately 29% of the analysed customers had cancelled their subscriptions.

Churn by Subscription Plan

Subscription Plan	Churn Rate
Basic	60.00%
Standard	22.22%
Premium	14.29%

Key finding: The Basic plan recorded the highest churn rate at 60%, significantly higher than the Premium and Standard plans.

Revenue & Customer Tenure

* Average Revenue Per User (ARPU): ₹18.85
* Average Customer Tenure: 1,452 days
* Monthly Revenue at Risk: ₹73.94 (reported in the notebook as Rs ‘K’)

The analysis identifies monthly recurring revenue associated with customers who have cancelled their subscriptions.

Customer Support & Churn

* Escalation Rate: 19.05%
* Average Complaints per Customer: 0.43
* Correlation between Escalations and Churn: 0.77

The positive correlation indicates an association between support escalations and churn in this dataset. It does not establish that escalations cause customers to leave.

Customer Risk Segmentation

Customers were classified into three churn-risk categories using their churn scores:

* Low Risk: Churn score below 50
* Medium Risk: Churn score from 50 to 69
* High Risk: Churn score of 70 or above

This segmentation helps identify customers who may require additional retention attention.

8. Business Insights & Recommendations

Based on the analysis, the following actions could help improve customer retention.

1. Investigate Basic Plan Churn

The Basic subscription plan has the highest observed churn rate. Review pricing, subscription benefits and customer expectations to understand the reasons behind cancellations.

2. Prioritise High-Risk Customers

Use churn scores and customer lifetime value to prioritise retention campaigns and proactive customer engagement.

3. Improve Customer Support

Investigate escalated complaints and identify recurring service issues. Improving complaint resolution may help reduce customer dissatisfaction.

4. Monitor Revenue at Risk

Track recurring revenue associated with churned and high-risk customers to understand the potential financial impact of customer loss.

5. Monitor Churn Trends

Track cancellation patterns over time to identify periods that may require additional retention campaigns.

9. Conclusion

This project demonstrates how relational customer data can be transformed into actionable business insights using Python and SQL.

By combining customer demographics, subscription information and support interactions, the analysis identifies churn patterns, high-risk subscription segments and potential revenue exposure.

The findings can help subscription-based businesses make more informed decisions about customer retention, support improvements and revenue protection.

10. Project Structure

Customer-Churn-Analysis/
│
├── churn_analysis.ipynb
├── customer_churn.db
├── Customer_Churn_Analysis_Project_Report.pdf
└── README.md

11. How to Run the Project

1. Clone or download this repository.
2. Install the required Python libraries:
    pip install pandas numpy matplotlib seaborn jupyter
3. Ensure the SQLite database is in the same directory as the notebook.
4. Open churn_analysis.ipynb using Jupyter Notebook or VS Code.
5. Execute the notebook cells sequentially to reproduce the analysis.

⸻

Note: The analysis uses a small sample dataset of 21 customers. Findings are useful for demonstrating the analytical workflow but should not be generalised to a large customer population without further data. The correlation results indicate association, not causation.
