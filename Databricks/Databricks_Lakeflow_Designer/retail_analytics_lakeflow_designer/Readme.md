🚀 Databricks LakeFlow Analytics Hub

End-to-End Retail Data Engineering Pipeline built using Databricks Lakeflow Designer, featuring data ingestion, transformation, aggregation, AI-powered sentiment analysis, and analytics-ready outputs in Unity Catalog.





📌 Project Overview

This project demonstrates how to build a complete Retail Analytics Platform using Databricks Lakeflow Designer.

The pipeline integrates data from multiple sources, performs joins and transformations, generates business metrics, and enriches customer reviews using AI-powered sentiment analysis.

The final outputs are stored in:

designer_catalog.enr

for business reporting and analytics.

🏗️ Architecture
Orders
   │
Order Items
   │
Customers
   │
Shipments
   │
Reviews
   ▼

Lakeflow Designer Pipeline
   │
   ├── Data Ingestion
   ├── Joins
   ├── Transformations
   ├── Aggregations
   ├── Sentiment Analysis (AI)
   │
   ▼

Unity Catalog
designer_catalog.analytics

   ├── AggregatedOrders
   ├── OrderStatus
   └── Sentiment
🔥 Key Features
Data Integration
Orders
Order Items
Customers
Shipments
Reviews
Data Engineering
Multi-table joins
Aggregations
Sorting and filtering
Feature enrichment
AI Functions
Sentiment Analysis using Databricks AI Functions

Example:

ai_analyze_sentiment(review_body)

Output:

positive
negative
neutral
mixed
📊 Pipeline Components
1️⃣ Orders + Order Items Join

Combines order information with purchased products.

Join Type
Left Join
Join Key
order_id
2️⃣ Customer & Shipment Enrichment

Enhances order data with:

Customer information
Shipment details
3️⃣ Orders By City

Calculates:

Total Orders
Revenue
Order Counts

Grouped by city.

4️⃣ Monthly Order Status Analysis

Creates:

Year
Month
Order Status
Order Count

for trend analysis.

5️⃣ AI-Powered Sentiment Analysis

Reviews are analyzed using Databricks AI Functions.

Input:

review_body

Output:

sentiment_score

Categories:

Positive
Neutral
Negative
Mixed
📂 Output Tables
designer_catalog.analytics.AggregatedOrders

Business-level city-wise order insights.

Column	Description
City	Customer City
TotalOrders	Total Orders
Revenue	Revenue Metrics
designer_catalog.analytics.OrderStatus

Monthly order status tracking.

Column	Description
Year	Order Year
Month	Order Month
Status	Order Status
Count	Number of Orders
designer_catalog.analytics.Sentiment

AI-generated sentiment insights.

Column	Description
review_id	Review Identifier
product_name	Product Name
rating	Rating
review_body	Review Content
sentiment_score	AI Sentiment
📸 Project Screenshots
Complete Lakeflow Pipeline
![Pipeline](images/<img width="1317" height="678" alt="Screenshot 2026-06-12 212759" src="https://github.com/user-attachments/assets/5bfd18ef-6d9b-412e-b114-f9e5835d0978" />
<img width="1556" height="540" alt="Screenshot 2026-06-12 210909" src="https://github.com/user-attachments/assets/d5bca9cd-cc3b-4d91-b46f-4134a9cfbc89" />
.png)
Orders Join Flow
![Join Flow](images/orders_join.p![Uploading Screenshot 2026-06-12 212759.png…]()
ng)
Sentiment Analysis Node
![Sentiment Analysis](images/sentiment_<img width="1357" height="711" alt="Screenshot 2026-06-12 213245" src="https://github.com/user-attachments/assets/ac8e5315-8b5f-44d8-bfa1-44c05c5949c5" />
analysis.png)
Sentiment Output
![Sentiment Output](images/senti<img width="1548" height="705" alt="Screenshot 2026-06-12 213315" src="https://github.com/user-attachments/assets/01f983d3-944f-4672-bc61-7ee387490aae" />
ment_output.png)
🛠️ Technologies Used
Databricks Lakeflow Designer
Unity Catalog
Databricks SQL
Databricks AI Functions
Delta Tables
Python
Retail Analytics Dataset
📈 Business Use Cases
Retail Analytics
City-wise sales analysis
Monthly order trend tracking
Shipment monitoring
Customer Insights
Customer behavior analysis
Product review analytics
AI Analytics
Sentiment analysis
Voice of customer analytics
Product feedback monitoring
