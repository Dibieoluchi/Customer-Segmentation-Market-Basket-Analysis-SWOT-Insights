# Customer-Segmentation-Market-Basket-Analysis-SWOT-Insights

# Introduction
today's  marketplace IS characterized by intense competition and shifting consumer preferences, businesses are increasingly recognizing the importance of understanding their customers. The advent of data analytics has transformed the way organizations approach customer relationships, enabling them to make data-driven decisions that enhance engagement and improve retention. This research focuses on customer segmentation through Recency, Frequency, and Monetary (RFM) analysis, a powerful tool that allows companies to categorize customers based on their purchasing behavior.

RFM analysis is rooted in the premise that customers who have purchased recently (Recency), buy frequently (Frequency), and spend more (Monetary) are likely to be more valuable to a business. By analyzing these dimensions, businesses can identify distinct customer segments, tailor their marketing strategies, and ultimately drive profitability. This study aims to explore  the segmentation of a customer base, interpret behavioral patterns, and provide  recommendations that can enhance customer loyalty and reduce churn rates.

This project on Analyzing Customer Behavior and Market Trends in a UK-Based Online Retail Company aims to provide insights that can inform the company’s strategic decisions, particularly focusing on transactional data spanning December 2010 to December 2011. The company primarily specializes in unique gifts for all occasions and caters to both retail customers and wholesalers.

 # Objectives and Aims
The objective of this project is to analyze customer behavior and market trends for a UK-based online retail company specializing in unique all-occasion gifts. Using a transactional dataset spanning from 01/12/2010 to 09/12/2011, the project aims to derive actionable insights to inform strategic decision-making and business growth.
   
 # Research Questions
This research addresses the following critical questions:

1. What are the primary customer segments identified through RFM analysis, and how do they differ in purchasing behavior?
2. How do customer segments vary in terms of engagement levels and revenue contribution?
3. What targeted strategies can be developed to re-engage at-risk customers and foster loyalty among existing customers?
4. How can insights derived from customer segmentation inform broader marketing strategies and business development initiatives?
   
By answering these questions, this study aims to provide a nuanced understanding of customer dynamics, enabling businesses to craft strategies that are both effective and sustainable.

# Methodology

# Data Collection and Preparation

The analysis utilized a dataset comprising sales transactions  spanning from 01/12/2010 to 09/12/2011. The following steps were undertaken to ensure the integrity and relevance of the data:

# Dataset Overview:
InvoiceNo: Unique 6-digit number for each transaction (cancellations are marked with 'C').
StockCode: Unique 5-digit product identifier.
Description: Product name.
Quantity: Number of units per product sold in a transaction.
InvoiceDate: Timestamp of the transaction.
UnitPrice: Price per unit (in GBP).
CustomerID: Unique 5-digit number for each customer (may contain missing values).
Country: Country where the customer resides.

# Initial Observations:

Negative Values:

Quantity: Negative values indicate product returns or cancellations. The mean quantity of items purchased per transaction is around 9.55, with a standard deviation of approximately 218, This indicates a wide variation in the quantity of items purchased per transaction.

The minimum quantity is -80995, indicating product returns or cancellations, and the maximum quantity is 80995. 25% of the transactions involve quantities of 1 or less, while 75% involve quantities of 10 or less.There were 10,624 rows with negative quantities.

![image](https://github.com/user-attachments/assets/25962cf4-7e70-4ee9-9dce-e8f8a96e5ae3)
The histogram shows that most transactions involve smaller quantities, with a right-skewed distribution. The peak around 0 indicates a significant number of transactions with negative quantities, likely representing returns or cancellations.

Unit Price: Only 2 rows had negative unit prices.
The mean unit price of items is about £4.61, with a standard deviation of approximately £96.76,This suggests a wide range of prices for the items sold by the company.

The minimum unit price is £0, and the maximum unit price is £38970. 25% of the items have a unit price of £1.25 or less, while 75% have a unit price of £4.13 or less.
![image](https://github.com/user-attachments/assets/39fd5f85-95c6-48ad-9346-da5aae853ad5)
The histogram displays the distribution of unit prices, showing a right-skewed distribution with a peak around lower values. There might be a few outliers with very high unit prices, as indicated by the long tail towards the higher prices.

 # we checked if they is a customer ID with either negative quantity ordered or nagative unit price : [nan]
 
based on the provided information,the rows with negative values in both quantity and unit price do not have a corresponding Customer ID. This suggests that these rows may be incomplete or corrupted data entries, as they lack a crucial identifier (Customer ID) for associating the transaction with a specific customer. Therefore, when cleaning the data, i choose to remove these rows separately considering the absence of a Customer ID.

# Missing Data:

CustomerID was missing for 132,220 rows, which could affect customer segmentation or behavior analysis.

# Data Cleaning:

Removing Negative Quantities and Unit Prices:
Transactions with negative quantities and unit prices were filtered out.
![image](https://github.com/user-attachments/assets/8be25938-47e3-4cdd-beb1-baa489e7a94c)

The cleaned dataset had a total of 409,689 transactions.

# Standardizing Product Descriptions:

Some products had multiple descriptions for the same StockCode (e.g., StockCode 23396 had several different descriptions).
This inconsistency was resolved by standardizing the descriptions.

# Descriptive Statistics (Post-Cleaning):

Quantity: Mean = 12.99, 
Max = 80,995, 
Min = 1. A wide range in quantities, with the distribution skewed toward smaller transactions.
Unit Price:
Mean = £3.12, 
Max = £8,142.75,
Min = £0.001. 
Prices show a right-skewed distribution, with most products priced low, and a few expensive outliers.

# RFM Scoring: 
Each customer was assigned an RFM score based on the following criteria:

Recency (R): The number of days since the customer last made a purchase. Recent purchases were scored higher.

Frequency (F): The total number of purchases made by the customer within a specific timeframe. More frequent buyers received higher scores.

Monetary (M): The total monetary value spent by the customer. Higher spending resulted in higher scores.

# Segmentation: 
Customers were then segmented into distinct groups based on their RFM scores. This segmentation allowed for the identification of various customer types, such as loyal customers, at-risk customers, and those who have churned.

# Importance of the Methodology

The methodology employed is crucial for several reasons. First, RFM analysis provides a structured framework that allows businesses to categorize customers quantitatively. By utilizing precise metrics, organizations can identify not only who their customers are but also how to engage them effectively. Furthermore, the visualization of data through charts and heatmaps aids in the communication of complex findings to stakeholders, making it easier to develop targeted marketing strategies.

# Exploratory Analysis 
![image](https://github.com/user-attachments/assets/55992e5e-b173-4b7d-b95b-13ef25b08ae9)

UK Dominance:

The UK accounts for 82% of total sales, making it the most significant market for the company.

The top 10 countries by sales include France, Germany, and Ireland, but their sales contribution is significantly smaller than the UK.

Top Customers:
![image](https://github.com/user-attachments/assets/a7cd8af4-72bc-45e0-8e89-8c56986fca4a)

The top 10 customers contributed 17.26% of the total sales, with the highest sales coming from Customer 14646.

Top Products:

![image](https://github.com/user-attachments/assets/71aea83f-779f-4b71-b730-83d3d00f7a77)

An analysis of top-selling products revealed that they represented a significant portion of total sales and invoices, suggesting that certain products drive a large part of the company’s revenue.

# Customer Segmentation Insights

![image](https://github.com/user-attachments/assets/79d80fc0-a753-4226-818a-695a6a5a4513)

At Risk Customers (55.7%): The analysis revealed that a significant portion of customers falls into the at-risk category, indicating a pressing need for businesses to implement re-engagement strategies. These customers may exhibit decreased purchasing frequency, reduced spending, or lack of recent purchases.

Loyal Customers (38.1%): A substantial number of customers are categorized as loyal, reflecting a stable and engaged customer base. This segment represents an opportunity for businesses to further nurture relationships through targeted loyalty programs and exclusive offers.

Lost Customers (5.3%): A smaller percentage of customers have likely churned, representing a challenge for businesses. Understanding the reasons behind this churn is critical for developing win-back strategies that could potentially revive this segment.

VIP Customers (0.9%): The analysis identified a very limited number of VIP customers, suggesting that there is significant potential for growth within this category. By focusing on the traits of these customers, businesses can develop strategies to cultivate more VIPs.

# Heatmap Analysis
![image](https://github.com/user-attachments/assets/cac3e865-0f00-4114-aae2-9e6e8f0d83ba)

The heatmap visualization highlighted the relationship between R, F, and M scores:

Top-Right Quadrant (High R and F Scores): This area was associated with customers who frequently purchase and have done so recently, resulting in higher average Monetary values. This segment should be prioritized for retention strategies, such as personalized experiences and premium services.

Bottom-Left Quadrant (Low R and F Scores): Customers in this quadrant purchase infrequently and have not made recent purchases, resulting in lower spending. Targeted win-back strategies are necessary to engage these customers and stimulate purchasing behavior.

Middle Areas (Moderate R and F Scores): Customers in these areas displayed moderate engagement. Strategies should focus on converting these customers into higher tiers by enhancing their engagement and spending through promotions and personalized marketing.

# Cluster Analysis Insights
The cluster analysis identified four distinct customer segments:


![image](https://github.com/user-attachments/assets/eef8187e-3e18-475d-97ab-194ea3709868)

Recency  Frequency       Monetary
0   17.124402  22.019139   12546.983206
1   13.615385  82.538462  127338.313846
2  267.569495   1.551444     498.987835
3   52.297207   3.702793    1356.652863

![image](https://github.com/user-attachments/assets/10a003e1-0c94-4c42-8146-e9b59b6cf5af)

![image](https://github.com/user-attachments/assets/fb95f1cf-3963-4b67-a38d-f0ace3589273)

![image](https://github.com/user-attachments/assets/f4671981-76ca-4dd4-986b-56d9e41da3a9)



Cluster 0:

Recency: 17.12 days
Frequency: 22.02 purchases
Monetary: $12,546.98

Interpretation: Customers in this cluster are moderately frequent purchasers with decent spending. They exhibit potential to evolve into loyal customers with targeted engagement.


Cluster 1:

Recency: 52.26 days
Frequency: 3.70 purchases
Monetary: $1,356.20
Interpretation: These customers are at risk of churning. Their infrequent purchases and low spending highlight the need for urgent re-engagement strategies.
Cluster 2:

Recency: 267.57 days
Frequency: 1.55 purchases
Monetary: $498.99
Interpretation: This cluster represents likely lost customers, as they exhibit very low purchasing activity. Win-back campaigns may be necessary, although success is uncertain.
Cluster 3:

Recency: 13.62 days
Frequency: 82.69 purchases
Monetary: $127,338.31
Interpretation: Customers in this cluster are highly engaged and spend significantly. They should be prioritized for retention strategies, such as exclusive offers and personalized services.


# Key Findings

The analysis led to several critical findings:

High Proportion of At-Risk Customers: The fact that over half of the customer base is at risk highlights a pressing challenge that requires immediate attention. This segment is crucial for revenue stability, and strategies must be implemented to engage and retain them.

Significant Loyal Segment: A robust segment of loyal customers indicates that there is a solid foundation for retention strategies. Nurturing this group can enhance customer lifetime value and brand loyalty.

Limited VIP Customers: The scarcity of VIP customers represents an opportunity for growth. By identifying the traits of existing VIP customers, businesses can tailor their offerings to cultivate more customers within this segment.

Behavioral Patterns: The analysis revealed distinct purchasing behaviors among customer segments, underscoring the importance of tailored marketing strategies. Understanding these patterns is essential for optimizing customer engagement efforts.

# Recommendations

Based on the analysis and findings, the following recommendations are proposed:

Re-engagement Strategies for At-Risk Customers:

Develop personalized marketing campaigns that address the specific needs and preferences of at-risk customers. Utilize targeted emails, exclusive discounts, and incentives to encourage repeat purchases.
Conduct surveys to gather feedback from this segment, allowing businesses to understand the reasons behind decreased engagement and address them effectively.
Nurturing Loyal Customers:

Continue to provide rewards for loyalty through loyalty programs, exclusive offers, and personalized experiences that recognize their value to the business.
Regularly solicit feedback from loyal customers to ensure their needs are met and enhance their overall satisfaction.
Win-Back Campaigns for Lost Customers:

Analyze the reasons behind customer churn by conducting exit surveys or follow-up communications. This feedback will help inform win-back strategies.
Implement win-back campaigns that offer strong incentives to entice lost customers back to the brand, such as discounts or special offers on popular products.

Cultivating VIP Customers:

Identify the characteristics and behaviors of VIP customers to replicate their engagement patterns among other customer segments. Focus on providing personalized experiences that cater to their preferences.
Consider introducing a tiered loyalty program that rewards higher spending customers with exclusive access to events, products, or services.

Data-Driven Marketing Strategies:

Utilize insights from RFM analysis to inform broader marketing strategies, ensuring that campaigns are aligned with customer behaviors and preferences.
Regularly update RFM scores to capture shifts in customer behavior over time and adjust marketing strategies accordingly.

