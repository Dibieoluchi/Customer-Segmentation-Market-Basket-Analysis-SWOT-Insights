# Customer-Segmentation-Market-Basket-Analysis-SWOT-Insights

# Introduction
Today's marketplace is characterized by intense competition and shifting consumer preferences, businesses are increasingly recognizing the importance of understanding their customers. The rise of data analytics has transformed the way organizations approach customer relationships, enabling them to make data-fueled decisions that enhance engagement and improve retention. This research focuses on customer segmentation through Recency, Frequency, and Monetary (RFM) analysis, a powerful tool that allows companies to categorize customers based on their purchasing behavior.

RFM analysis is rooted in the premise that customers who have purchased recently (Recency), buy frequently (Frequency), and spend more (Monetary) are likely to be more valuable to a business. By understanding these dimensions, companies can identify distinct customer segments, tailor their marketing strategies, and ultimately drive profitability. This study aims to explore the segmentation of a customer base of a UK-based online retail company,  and provide recommendations that can improve customer loyalty and reduce churn rates. It focuses on transactional data spanning December 2010 to December 2011. The company primarily specializes in unique gifts for all occasions and caters to both retail customers and wholesalers.


# Methodology

![image](https://github.com/user-attachments/assets/c2d88ef0-ee78-47aa-ad41-39162bf46a18)


# Data Collection and Preparation

The analysis utilized a dataset comprising sales transactions  spanning from 01/12/2010 to 09/12/2011. The following steps were undertaken to ensure the integrity and relevance of the data:

# Dataset Overview:
1. InvoiceNo: Unique 6-digit number for each transaction (cancellations are marked with 'C').
2. StockCode: Unique 5-digit product identifier.
3. Description: Product name.
4. Quantity: Number of units per product sold in a transaction.
5. InvoiceDate: Timestamp of the transaction.
6. UnitPrice: Price per unit (in GBP).
7. CustomerID: Unique 5-digit number for each customer (may contain missing values).
8. Country: Country where the customer resides.

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

# uk internal market

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

The analysis yielded several critical insights into the company's customer base and sales performance.

Sales Distribution and Market Presence: The UK market is paramount to the company’s success, accounting for a substantial 82% of total sales. This highlights the importance of the UK in generating revenue. Additionally, while there is a growing audience in key international markets such as France, Germany, and Ireland, their sales contributions remain relatively modest compared to the UK.

Customer Contribution to Revenue: The top customers constitute 17.26% of overall sales, revealing their significant impact on revenue. However, these customers and the top-selling products represent a small fraction of total transactions, suggesting that a limited number of customers drive a disproportionate amount of sales.

Challenge of At-Risk Customers: A concerning finding is that over half of the customer base is categorized as at-risk. This highlights a pressing challenge for the business, as these customers have shown a notable decline in engagement and purchasing frequency. Their diminishing activity raises concerns about their potential exit from active shopping behavior, indicating a need for focused strategies to address this issue.

Loyal Customer Segment: The presence of a significant segment of loyal customers presents a solid foundation for retention efforts. These customers exhibit consistent purchasing patterns and engagement, contributing a reliable stream of revenue. Their repeated purchases indicate a strong connection to the brand, suggesting opportunities to strengthen this relationship further.

Limited VIP Customer Base: The analysis reveals a scarcity of VIP customers, who represent the highest value segment. Characterized by high purchase frequency and substantial transaction value, this group plays a crucial role in the store's revenue. Their limited number presents an opportunity for growth, indicating that there is potential to enhance engagement with this valuable segment.

Lost Customers: The data indicates that 5.3% of customers are classified as lost, meaning they once demonstrated high activity but have not interacted with the store for an extended period. This presents a challenge, as it signifies a notable portion of the customer base has churned, pointing to potential gaps in retention strategies.


# Recommendations Based on Analysis and Findings

To address the needs of different customer segments effectively, the following strategies are recommended:

1. Expand International Market Initiatives: While the UK market is critical, the growing international audience should not be overlooked. Developing  marketing strategies for France, Germany, and Ireland could improve  brand visibility and drive sales in these markets. This may include localized promotions, partnerships with regional influencers, or culturally relevant product offerings.

2. Re-engagement strategies are essential for retaining at-risk customers. Personalized marketing campaigns should be developed, focusing on their specific needs and preferences. Targeted emails, exclusive discounts, and other incentives can encourage these customers to make repeat purchases. Additionally, surveys should be conducted to gather feedback from this group, helping the business understand and address the factors contributing to decreased engagement.
3. For loyal customers, continued recognition is key. Rewarding loyalty through exclusive offers, well-structured loyalty programs, and personalized experiences will reinforce their connection to the brand. Regularly collecting feedback from these customers will help ensure their satisfaction and that their needs are consistently met.
4. For customers who have disengaged, win-back campaigns should be designed based on an understanding of the reasons behind customer churn. Exit surveys or follow-up communications can provide valuable insights, which can then inform effective win-back strategies. Campaigns could include strong incentives, such as discounts or special offers on popular products, to attract lost customers back to the brand.
5. Lastly, VIP customers should receive distinct attention. By understanding the behaviors and preferences of VIP customers, the brand can replicate successful engagement strategies among other segments. VIPs should experience highly personalized services that cater to their preferences, and a tiered loyalty program can offer higher-spending customers unique benefits like early access to events, products, or exclusive services, further enhancing their relationship with the brand.
