# Project3--OnlineRetail Overview 
This project focuses on analyzing customer purchasing behavior using RFM (Recency, Frequency, Monetary) analysis, Cohort Analysis, and K-Means Clustering to derive actionable business insights.
The objective is to identify high-value customers, understand retention patterns, and uncover customer segments for targeted marketing and engagement strategies.

—Dataset:— InvoiceNo:StockCode:Description:Quantity:UnitPrice:CustomerID:Country

# Key Objectives
Segment customers based on purchasing behavior using RFM methodology
Analyze customer retention trends over time using cohort analysis
Identify distinct customer groups using K-Means clustering
Generate actionable insights for improving customer retention and revenue

# Techniques and tools
Python (Pandas, NumPy) – Data cleaning and transformation
Matplotlib / Seaborn – Data visualization
Scikit-learn – K-Means clustering
RFM Analysis – Rule-based customer segmentation
Cohort Analysis – Retention tracking
Data Preprocessing – Log transformation & feature scaling

# Methodology
---RFM Segmentation || Cohort Analysis || K-means Clusters

# (i) Perform a preliminary data inspection and Data cleaning
# (ii) Cohort Analysis: A cohort is a group of subjects who share a defining characteristic. We can observe how a cohort behaves across time and compare it to other cohorts. 

# Objective: To analyze customer retention behavior over time by grouping customers into cohorts based on their first purchase month and tracking their repeat activity.

→ Step1: date format 

→ Step2: Create Invoice Month

→ Step3:Create Cohort Month(first invoice month per customer) ||
here cohort_index =0 means customer first invoice or new customers
cohort_index =1,2,3 are retuning customer in subsequent months 

→ Step4: Create Cohort Index(months since first invoice)

→ Step5: Count active customers

→ Step6:pivot(cohort table)

→ Step7:Cohort Size(Month0)

→ Step8: Retention Rate

→ Step9: convert to %

Summary: 

CohortMonth	   0	  |   1	   |   2	`

----------|---------|--------|---------

       
2010-01  	|    98	   |   9	   |   4	

--------  |--------- |--------|---------

         
2010-02	  |   108    |   2     |   0	
        
----------|--------- |-------- |------------
          
2010-03	  |    49	   |    0	  |   1	
         
----------|--------- |-------- |-------

         
2010-05   |    	33	 |     0   |   0	

				
 	Jan	FEB	March	May
Cohort	2010-01	2010-02 	2010-02 	2010-02
 	M1  9/98 ~ 9% 	M1  2/108 ~ 2% 	M1  0/49 ~ 0% 	No retention
 	M2  4/98 ~ 4% 	M2  0/98 ~ 0% 	M2  1/49~ 2% 	No retention

M0 – Total customers Acquired
M1, M2 – Returning customers

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

# (iii) 	Calculate RFM metrics.
# (iv)    Build RFM Segments: 

→ Step1: Give Recency Frequency and Monetary scores individually by dividing them in to quartiles.

→ Step2:  Champions have the highest monetary and frequency scores, indicating strong repeat purchasing and high value || At Risk customers have high past frequency but low recency, suggesting churn risk

# (v) clusters using k means clustering algorithm, Analyze cluster and comment on the results

CustomerID	|  R_score  |	       | F_score |	               | M_score	|              | Segment |

-----------------------------------------------------------------------------------

12395       | 	4	    |      |    1	  |        |      3   |           | New Customers|

----------------------------------------------------------------------------------------

12427	          4	                    1	                  3	             New Customers

------------------------------------------------------------------------------------------

12431	          1	                     1	                3	             Lost Customers

-------------------------------------------------------------------------------------------

12433	          2	                     1	                4	              Others

------------------------------------------------------------------------------------------

12557	          4	                      1	                4	              New Customers

------------------------------------------------------------------------------------------------


Metrics:
Recency –   lower the better
Frequency – higher is better
Monetary –  higher is better

Cluster 0 (Recency ~53) is low
Customer purchased 53 days ago is  is relatively recent  better than remaining clusters, 1,2,3. So it falls in to upper Quartile ~3-4 scores
Cluster 1 (Recency ~ 86) is high
        Customer purchased 86 days ago is not recentRarely purchasespend very less
	Low value and inactive customers, indicating minimal engagement.
Cluster 2 (Recency ~114) is high
      Customer haven’t purchased for ~114 days InactiveBig spenders, indication a strong churn risk.
Cluster 3 (Recency ~ 89) is high
       Customer show good spending potential but low engagement, possible one-time or occasional buyersoccasion high spenders.


# Key Insights
Customer retention drops significantly after the first purchase, indicating a need for stronger onboarding and engagement strategies
A small proportion of customers contribute disproportionately to revenue (high-value segment)
Identified a segment of high-spending but inactive customers, representing churn risk
Majority of customers fall into low-frequency or early-stage segments

# Business Recommendations
Implement targeted retention campaigns for at-risk customers
Introduce loyalty programs for high-value customers
Design onboarding strategies to improve second purchase conversion
Use personalized marketing to increase engagement

# Conclusion.
This project demonstrates how combining rule-based segmentation (RFM) with time-based analysis (Cohort) and machine learning (K-Means) provides a comprehensive understanding of customer behavior and supports data-driven decision-making.
