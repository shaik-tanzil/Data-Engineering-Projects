# 🚀 Databricks LakeFlow Analytics Hub

End-to-End Retail Data Engineering Pipeline built using Databricks Lakeflow Designer, featuring data ingestion, transformation, aggregation, AI-powered sentiment analysis, and analytics-ready outputs in Unity Catalog.

---

### 📌 Project Overview

This project demonstrates how to build a complete Retail Analytics Platform using Databricks Lakeflow Designer.

The pipeline integrates data from multiple sources, performs joins and transformations, generates business metrics, and enriches customer reviews using AI-powered sentiment analysis.

The final outputs are stored in `designer_catalog.enr` for business reporting and analytics.

---

### 🏗️ Architecture

```text
Orders ────────┐
Order Items ───┼─► Lakeflow Designer Pipeline
Customers ─────┤    ├── Data Ingestion & Joins
Shipments ─────┤    ├── Transformations & Aggregations
Reviews ───────┘    └── Sentiment Analysis (AI)
                         │
                         ▼
                    Unity Catalog (designer_catalog.analytics)
                     ├── AggregatedOrders
                     ├── OrderStatus
                     └── Sentiment
```

---

### 🔥 Key Features

* **Data Integration:** Unified ingestion for Orders, Order Items, Customers, Shipments, and Reviews.
* **Data Engineering:** Multi-table joins, aggregations, sorting, filtering, and feature enrichment.
* **AI Functions:** Sentiment Analysis using Databricks AI Functions:
  ```sql
  SELECT ai_analyze_sentiment(review_body); -- Outputs: positive, negative, neutral, mixed
  ```

---

### 📊 Pipeline Components

1. **Orders + Order Items Join:** Combines order information with purchased products using a `Left Join` on `order_id`.
2. **Customer & Shipment Enrichment:** Enhances core order data with vital customer demographics and shipment tracking details.
3. **Orders By City:** Aggregates and calculates `Total Orders`, `Revenue`, and `Order Counts` grouped by city.
4. **Monthly Order Status Analysis:** Extracts tracking trends by organizing metrics into `Year`, `Month`, `Order Status`, and `Order Count`.
5. **AI-Powered Sentiment Analysis:** Evaluates customer reviews (`review_body`) into structured tags: `Positive`, `Neutral`, `Negative`, or `Mixed`.

---

### 📂 Output Tables

#### 🔹 `designer_catalog.analytics.AggregatedOrders`
*Business-level city-wise order insights.*

| Column | Description |
| :--- | :--- |
| **City** | Customer City |
| **TotalOrders** | Total Orders Placed |
| **Revenue** | Revenue Metrics |

#### 🔹 `designer_catalog.analytics.OrderStatus`
*Monthly order status tracking.*

| Column | Description |
| :--- | :--- |
| **Year** | Order Year |
| **Month** | Order Month |
| **Status** | Order Status |
| **Count** | Number of Orders |

#### 🔹 `designer_catalog.analytics.Sentiment`
*AI-generated sentiment insights.*

| Column | Description |
| :--- | :--- |
| **review_id** | Review Identifier |
| **product_name** | Product Name |
| **rating** | Product Rating |
| **review_body** | Raw Review Content |
| **sentiment_score** | AI Generated Sentiment |

---

### 📸 Project Screenshots

<br>

#### Complete Lakeflow Pipeline
<p align="center">
  <img width="100%" alt="Complete Lakeflow Pipeline" src="https://github.com/user-attachments/assets/d5bca9cd-cc3b-4d91-b46f-4134a9cfbc89" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
</p>

<br>

#### Orders Join Flow
<p align="center">
  <img width="90%" alt="Orders Join Flow" src="https://github.com/user-attachments/assets/5bfd18ef-6d9b-412e-b114-f9e5835d0978" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
</p>

<br>

#### Sentiment Analysis Node
<p align="center">
  <img width="90%" alt="Sentiment Analysis Node" src="https://github.com/user-attachments/assets/ac8e5315-8b5f-44d8-bfa1-44c05c5949c5" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
</p>

<br>

#### Sentiment Output Data
<p align="center">
  <img width="100%" alt="Sentiment Output" src="https://github.com/user-attachments/assets/01f983d3-944f-4672-bc61-7ee387490aae" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
</p>

<br>

---

### 🛠️ Technologies Used

* **Orchestration & Compute:** Databricks Lakeflow Designer, Delta Tables, Python
* **Governance & Storage:** Unity Catalog
* **Analytics & AI:** Databricks SQL, Databricks AI Functions
* **Dataset Domain:** Retail Analytics Dataset

---

### 📈 Business Use Cases

* **Retail Analytics:** City-wise sales volumes, monthly order trends, and shipment tracking optimization.
* **Customer Insights:** In-depth customer behavior mapping paired with direct product review analytics.
* **AI Analytics:** Enterprise-wide sentiment tracking, processing the "Voice of Customer" into actionable feature backlogs.
