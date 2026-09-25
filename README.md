# UCI Online Retail Sales Analysis

## Project Overview

An end-to-end analysis of UCI online retail transactions to understand sales performance, customer contribution, product performance, geographic performance, and cancellations. The objective is to transform raw transaction data into actionable business insights through data cleaning, modeling, KPI development, and an interactive dashboard.

---

## Dataset

The project uses the Online Retail dataset from the UCI Machine Learning Repository. The dataset contains transactions from a UK-based online retailer between December 2010 and December 2011.

---

## Business Problem

Management wants to understand sales performance, customer contribution, product performance, geographic performance, and cancellation patterns to identify areas requiring further investigation.

---

## Business Objectives

* Evaluate overall revenue performance
* Analyze sales trends
* Identify high/low-performing products
* Understand customer contribution
* Compare country-level performance
* Analyze cancellation patterns

---

## Key Metrics

* **Sales Performance Overview:** Tracks monthly revenue, total orders, average order value (AOV), and seasonal trends.
* **Product & Customer Analysis:** Details top-performing vs. least-performing stock codes and unique customer distribution by country.   
* **Cancellation Analysis:** Analyzes cancellation trends, lost revenue, and cancellation rates across global markets.

---

## Business Questions & Executive Summary

### Questions Addressed
* How is the overall sale performance changing over time?
* Which product and countries contributed the most to revenue?
* What factors contributed to periods of low sales performance?

<div align="center"><h3>Executive Summary</h3></div>

* **Sales Over Time:** Overall performance experiences a massive seasonal surge starting at the end of Q3 and peaking heavily in Q4 (culminating in November at $1,428.4K). Monthly baselines otherwise fluctuate between $620K and $800K, with temporary dips like January 2011 seeing a 4.7% decrease in revenue compared to the previous month.  
* **Top Products & Countries:** StockCode `22423` (Regency Cakestand 3 Tier) is the top revenue-making product overall, generating $177,098, closely followed by bulk and high-demand stock codes like `23843` and `85123A`. The United Kingdom overwhelmingly dominates revenue and customer acquisition, bringing in $612K in January 2011 alone and housing 3,951 unique customers, vastly outperforming international regions like the Netherlands, EIRE, and France.   
* **Low Performance Drivers:** Low performance periods and revenue leakage are heavily driven by order cancellations (accounting for a 14.81% overall cancellation rate and $1.02M in cumulative lost revenue), particularly concentrated in specific product categories like *Paper Craft, Little Bird...* and *Medium Ceramic Top Storage...*, alongside tracking gaps from unlinked "Unknown" customer checkouts.

---

## Key Insights

### 1. Sales Trend
<p align="center">
  <img width="500" alt="Sales Trend" src="https://github.com/user-attachments/assets/dbbe7e4a-c5ac-4a11-8d11-23c131a59298" />
</p>

* **Q4 Peak Performance:** Sales really take off starting in September ($1,094.4K) and peak hard in November at a massive $1,428.4K, staying well above our $825.56K average.
* **Q1 Slump:** Following the Q4 peak, revenue drops significantly at the start of the year, hitting a low point in February ($528.9K) and April ($527.5K).
* **Mid-Year Stabilization:** Throughout Q2 and Q3 (May through August), revenue maintains a steady, predictable plateau, hovering consistently between $733.4K and $794.1K.

### 2. Geographic Distribution & Market Concentration
<p align="center">
  <img width="48%" alt="Geographic Chart" src="https://github.com/user-attachments/assets/9ff61c42-4bf7-441e-bd6b-7d68b1ae73db" />
  &nbsp;&nbsp;
  <img width="45%" alt="Customer Base" src="https://github.com/user-attachments/assets/3b8f0465-c2ec-46df-b95c-cb397dad5dee" />
</p>

* **UK Dominance:** The customer base is heavily concentrated in the United Kingdom, accounting for 3,951 unique buyers and generating $612K in revenue during January 2011.
* **International Footprint:** Other European and global markets feature minimal unique active buyers, such as Germany (95 customers), France (87 customers), Spain (29 customers), and Belgium (24 customers).

### 3. Product Performance & Inventory Dynamics
<p align="center">
  <img width="300" alt="Product Performance" src="https://github.com/user-attachments/assets/23417012-1651-4226-ad5c-4ac13f47bb61" />
</p>

* **Top Revenue Position:** When filters are set to "All", StockCode `22423` leads the "Top 10 Products" table with an impressive $177,098 in total revenue. 
* **High Transaction Volume:** It drove 1,989 total orders throughout the historical period, indicating widespread and consistent consumer demand.
* **Significant Unit Movement:** Customers purchased a total of 13,890 units of this item, maintaining a strong average order value (AOV) of roughly $89.03 per line item context.

### 4. Cancellation Risks & Revenue Leakage
<p align="center">
  <img width="400" alt="Cancellation Revenue" src="https://github.com/user-attachments/assets/4cbd88a5-8f46-4cb8-99b7-16f44fa300bf" />
</p>
<p align="center">
  <img width="48%" alt="Top Cancelled Products" src="https://github.com/user-attachments/assets/3befaf96-1cf3-4279-aa0f-e4e992b4a547" />
  &nbsp;&nbsp;
  <img width="48%" alt="Cancellation Rate by Country" src="https://github.com/user-attachments/assets/d35287da-a304-49d5-8f64-294189e557fa" />
</p>

* **Massive Total Revenue Loss:** Historical order cancellations resulted in $1.02M in lost revenue, driven by 4K cancelled orders and 278K cancelled quantities at an overall 14.81% cancellation rate.
* **Concentrated Product Vulnerability:** Over 90% of total product cancellations are driven by just two categories: *Paper Craft, Little Bird...* (47.07%) and *Medium Ceramic Top Storage...* (43.29%).
* **Geographic Disparities:** Relative cancellation ratios peak sharply in international regions like the Czech Republic, Malta, and Saudi Arabia, exceeding 0.5 on the index scale.

---

## Strategic Recommendations

* **Inventory & Fulfillment Optimization:** Investigate the root causes behind the top cancelled product lines (*Paper Craft, Little Bird...* and *Medium Ceramic Top Storage...*) to resolve quality or fulfillment bottlenecks.
* **Targeted Regional Risk Mitigation:** Implement localized checkout verification or shipping restrictions for high-cancellation regions (such as the Czech Republic and Malta) to minimize cross-border revenue leakage.
* **Customer Data Hygiene:** Address the significant volume of unlinked transactions grouped under "Unknown" customer IDs (accounting for over $442K in lost revenue) by enforcing mandatory account sign-ins during checkout.

---

## Data Model & Architecture

```text
                 DimProduct
                     │
                     │
DimCustomer ───── ucisales ───── DimLocation
                     │
                     │
                 Datetable
```
---

* Cancellation Identification: Cancellations within the dataset are systematically identified, filtered, and processed using invoice numbers starting with the prefix C.

 ## Project Metadata & Resources 

 * **Dataset Source**: UCI Online Retail Dataset (UCI Machine Learning Repository)
*  **Tools & Technologies Used**: Power BI Desktop, Power Query, DAX
