# Customer-Segmentation-Market-Basket-Analysis-SWOT-Insights

# Introduction
Today's marketplace is characterized by intense competition and shifting consumer preferences, businesses are increasingly recognizing the importance of understanding their customers. The rise of data analytics has transformed the way organizations approach customer relationships, enabling them to make data-fueled decisions that enhance engagement and improve retention. This research focuses on customer segmentation through Recency, Frequency, and Monetary (RFM) analysis, a powerful tool that allows companies to categorize customers based on their purchasing behavior.

RFM analysis is rooted in the premise that customers who have purchased recently (Recency), buy frequently (Frequency), and spend more (Monetary) are likely to be more valuable to a business. By understanding these dimensions, companies can identify distinct customer segments, tailor their marketing strategies, and ultimately drive profitability. This study aims to explore the segmentation of a customer base of a UK-based online retail company, interpret their customer's behavioral patterns, and provide recommendations that can improve customer loyalty and reduce churn rates. It focuses on transactional data spanning December 2010 to December 2011. The company primarily specializes in unique gifts for all occasions and caters to both retail customers and wholesalers.

   

# Methodology

https://lucid.app/lucidchart/0d6cab3e-60af-4c01-a4b9-43428d3fc0dc/edit?viewport_loc=-1668%2C-1100%2C4416%2C1788%2C0_0&invitationId=inv_3c531fd0-5cbf-42d4-a206-ab65f82a9101

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

# Negative Values:

i. Quantity: Negative values indicate product returns or cancellations. The mean quantity of items purchased per transaction is around 9.55, with a standard deviation of approximately 218, This indicates a wide variation in the quantity of items purchased per transaction. The minimum quantity is -80995, indicating product returns or cancellations, and the maximum quantity is 80995. 25% of the transactions involve quantities of 1 or less, while 75% involve quantities of 10 or less.There were 10,624 rows with negative quantities.

![image](https://github.com/user-attachments/assets/479fe10b-53df-43ab-b4b3-f87ba5ffd798)


The histogram shows that most transactions involve smaller quantities, with a right-skewed distribution. The peak around 0 indicates a significant number of transactions with negative quantities, likely representing returns or cancellations.

ii. Unit Price: Only 2 rows had negative unit prices.The mean unit price of items is about £4.61, with a standard deviation of approximately £96.76,This suggests a wide range of prices for the items sold by the company. The minimum unit price is £0, and the maximum unit price is £38970. 25% of the items have a unit price of £1.25 or less, while 75% have a unit price of £4.13 or less.

![image](https://github.com/user-attachments/assets/98ec41be-88e6-4198-9130-50df41edfd08)

The histogram displays the distribution of unit prices, showing a right-skewed distribution with a peak around lower values. There might be a few outliers with very high unit prices, as indicated by the long tail towards the higher prices.

 iii. Customer Id:  checked if they is a customer ID with either negative quantity ordered or nagative unit price : [nan],  based on the provided information,the rows with negative values in both quantity and unit price do not have a corresponding Customer ID. This suggests that these rows may be incomplete or corrupted data entries, as they lack a crucial identifier (Customer ID) for associating the transaction with a specific customer. Therefore, when cleaning the data, i choose to remove these rows separately considering the absence of a Customer ID.

# Missing Data:

CustomerID was missing for 132,220 rows, which could affect customer segmentation or behavior analysis.

# Data Cleaning:

# Descriptive Statistics (Post-Cleaning):

Quantity	UnitPrice	CustomerID
count	397884.000000	397884.000000	397884.000000
mean	12.988238	3.116488	15294.423453
std	179.331775	22.097877	1713.141560
min	1.000000	0.001000	12346.000000
25%	2.000000	1.250000	13969.000000
50%	6.000000	1.950000	15159.000000
75%	12.000000	3.750000	16795.000000
max	80995.000000	8142.750000	18287.000000

The cleaned dataset had a total of 409,689 transactions.

# Quantity:
The mean quantity of items purchased per transaction is approximately 12.99, with a standard deviation of around 179.33.
The minimum quantity is 1, indicating the lowest quantity of items purchased in a single transaction after removing negative quantities.
The maximum quantity is 80995, which remains unchanged from the original dataset.
25% of the transactions involve quantities of 2 or less, while 75% involve quantities of 12 or less.

# UnitPrice:
The mean unit price of items is roughly £3.12, with a standard deviation of approximately £22.10.
The minimum unit price is £0.001, indicating the lowest unit price of items after removing negative prices.
The maximum unit price is £8142.75, which remains unchanged from the original dataset.
25% of the items have a unit price of £1.25 or less, while 75% have a unit price of £3.75 or less.

![image](https://github.com/user-attachments/assets/4442c00f-bc05-40b3-945f-d1084349d671)


# Distribution of Quantity:
The histogram displays the distribution of quantities in the cleaned dataset.
With negative quantities removed, the distribution appears to be more focused on positive values, as expected.
There might still be a few transactions with very high quantities, as indicated by the long tail towards higher quantities.

Overall, after filtering out transactions with negative quantities, the summary statistics and distribution of quantities remain largely similar, ensuring that no valid information is lost while addressing the issue of negative values in the dataset.

# Standardizing Product Descriptions:

Some products had multiple descriptions for the same StockCode (e.g., StockCode 23396 had several different descriptions).
This inconsistency was resolved by standardizing the descriptions,This data cleaning process involves identifying and resolving inconsistencies or discrepancies in the dataset. In this case, I  addressed the issue of multiple descriptions for the same stock code by standardizing them. that is ensuring each stock has the same description.


# Exploratory Analysis 

![image](https://github.com/user-attachments/assets/f583c71c-bdc7-4aac-92c8-57891231ed7e)

![image](https://github.com/user-attachments/assets/29956e1d-2902-42f9-ac2d-ebca98ecce57)


# UK Dominance:

Based on the sales amounts across different countries and the classification of the United Kingdom as an internal (domestic) market:

The analysis shows that the United Kingdom (UK) has the highest sales amount among all countries, indicating that it is a significant contributor to overall sales. This suggests that the UK market plays a crucial role in driving revenue for the business.

Additionally, the pie chart illustrates that approximately 82% of the total sales come from the internal market, which includes the United Kingdom. This indicates that the UK serves as a major internal (domestic) market for the business.

The top 10 countries by sales include France, Germany, and Ireland, but their sales contribution is significantly smaller than the UK.

# Top Customers:

![image](https://github.com/user-attachments/assets/3bd434c5-cf82-4fd1-80fd-d5547c8b7cfe)


The top 10 customers contributed 17.26% of the total sales, with the highest sales coming from Customer 14646.

# Top Products:

![image](https://github.com/user-attachments/assets/edd2bcc2-f1ac-437f-a4e5-dff5c7abdfef)


An analysis of top-selling products revealed that These top 10 products represent approximately 9.95% of the total sales amount and about 2.6% of the total number of events (invoices).
which rrepresent  a significant portion of total sales and invoices, suggesting that certain products drive a large part of the company’s revenue.

# Customer Segmentation Insights

# RFM Scoring: 
Each customer was assigned an RFM score based on the following criteria:

Recency (R): The number of days since the customer last made a purchase. Recent purchases were scored higher.

Frequency (F): The total number of purchases made by the customer within a specific timeframe. More frequent buyers received higher scores.

Monetary (M): The total monetary value spent by the customer. Higher spending resulted in higher scores.

# Segmentation: 
Customers were then segmented into distinct groups based on their RFM scores. This segmentation allowed for the identification of various customer types, such as loyal customers, at-risk customers, and those who have churned.

# Importance of the Methodology

The methodology employed is crucial for several reasons. First, RFM analysis provides a structured framework that allows businesses to categorize customers quantitatively. By utilizing precise metrics, organizations can identify not only who their customers are but also how to engage them effectively. Furthermore, the visualization of data through charts and heatmaps aids in the communication of complex findings to stakeholders, making it easier to develop targeted marketing strategies.

![image](https://github.com/user-attachments/assets/4657ae5a-4775-46ee-b9a4-d16a40610891)


At Risk Customers (55.7%): The analysis revealed that a significant portion of customers falls into the at-risk category, indicating a pressing need for businesses to implement re-engagement strategies. These customers may exhibit decreased purchasing frequency, reduced spending, or lack of recent purchases.

Loyal Customers (38.1%): A substantial number of customers are categorized as loyal, reflecting a stable and engaged customer base. This segment represents an opportunity for businesses to further nurture relationships through targeted loyalty programs and exclusive offers.

Lost Customers (5.3%): A smaller percentage of customers have likely churned, representing a challenge for businesses. Understanding the reasons behind this churn is critical for developing win-back strategies that could potentially revive this segment.

VIP Customers (0.9%): The analysis identified a very limited number of VIP customers, suggesting that there is significant potential for growth within this category. By focusing on the traits of these customers, businesses can develop strategies to cultivate more VIPs.

# Heatmap Analysis

![image](https://github.com/user-attachments/assets/cb276dda-fac9-40bf-94a1-4b1d15e31244)


The heatmap visualization highlighted the relationship between R, F, and M scores:

Top-Right Quadrant (High R and F Scores): This area was associated with customers who frequently purchase and have done so recently, resulting in higher average Monetary values. This segment should be prioritized for retention strategies, such as personalized experiences and premium services.

Bottom-Left Quadrant (Low R and F Scores): Customers in this quadrant purchase infrequently and have not made recent purchases, resulting in lower spending. Targeted win-back strategies are necessary to engage these customers and stimulate purchasing behavior.

Middle Areas (Moderate R and F Scores): Customers in these areas displayed moderate engagement. Strategies should focus on converting these customers into higher tiers by enhancing their engagement and spending through promotions and personalized marketing.

# Cluster Analysis Insights
The cluster analysis identified four distinct customer segments:

![image](https://github.com/user-attachments/assets/9ce3951a-47f4-40ec-b66e-f1d4d107c954)


Recency  Frequency       Monetary
0   17.124402  22.019139   12546.983206
1   13.615385  82.538462  127338.313846
2  267.569495   1.551444     498.987835
3   52.297207   3.702793    1356.652863

![image](https://github.com/user-attachments/assets/3c1ac6a6-3cbd-4b21-9e65-995396121e3f)

![image](https://github.com/user-attachments/assets/24e32731-468b-4312-b9b6-4bbf8a0d3559)

![image](https://github.com/user-attachments/assets/eeb39ee0-4b80-4829-b983-6e5308b23108)


# Cluster 0:

Recency: 17.12 days
Frequency: 22.02 purchases
Monetary: $12,546.98

Interpretation: Customers in this cluster are moderately frequent purchasers with decent spending. They exhibit potential to evolve into loyal customers with targeted engagement.

# Cluster 1:

Recency: 52.26 days
Frequency: 3.70 purchases
Monetary: $1,356.20
Interpretation: These customers are at risk of churning. Their infrequent purchases and low spending highlight the need for urgent re-engagement strategies.

# Cluster 2:
Recency: 267.57 days
Frequency: 1.55 purchases
Monetary: $498.99
Interpretation: This cluster represents likely lost customers, as they exhibit very low purchasing activity. Win-back campaigns may be necessary, although success is uncertain.

# Cluster 3:
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

