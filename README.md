# Customer-Behavior-Analysis

# Customer Shopping Behavior Analysis (End-to-End Analytics)

## 📌 Project Overview
This project delivers an end-to-end data analytics solution evaluating retail transactional data across **3,900 purchases** and **18 distinct features**. The project models a real-world analytics architecture, moving from exploratory data preparation and programmatic feature engineering in **Python (Pandas)**, to deep business transaction querying in **PostgreSQL / SQL Server**, and concluding with executive-level interactive business intelligence reporting in **Power BI**.

The analysis isolates core drivers of retail revenue, flags discount dependencies, segments customer populations, and evaluates the financial impact of premium shipping and subscription programs.

---

## ⚙️ Data Pipeline Architecture

┌──────────────────────┐      ┌───────────────────────┐      ┌───────────────────────┐
│       Phase 1:       │      │       Phase 2:        │      │       Phase 3:        │
│   Data Prep & EDA    │ ───> │  Relational Database  │ ───> │ Interactive BI Panel  │
│       (Python)       │      │   Business Queries    │      │      (Power BI)       │
└──────────────────────┘      └───────────────────────┘      └───────────────────────┘

1. **Phase 1 (Python/Pandas):** Ingested the raw metrics, executed data quality checks (`.info()`, `.describe()`), handled structural missingness, and engineered clean feature attributes.
2. **Phase 2 (SQL Server):** Established integration from Python into the relational database engine. Developed 10 complex analytical business queries to extract direct customer insights.
3. **Phase 3 (Power BI):** Designed an interactive dynamic reporting layer displaying macro-KPI charts, customer behavior distributions, and active slicing capabilities.

---

## 🛠️ Technical Deep Dive

### 1. Python Data Preprocessing & Feature Engineering
Using a Jupyter Notebook/Python script, the data was programmatically cleaned and standardized:
* **Missing Value Imputation:** Identified 37 missing values in the `Review Rating` attribute and imputed them dynamically using the category-specific median score to prevent statistical skew.
* **Schema Standardization:** Restructured original columns into normalized `snake_case` naming conventions for uniform schema documentation.
* **Feature Engineering:** 
  * Binned demographic attributes to construct an optimized categorical `age_group` column.
  * Extracted operational granular tracking metrics to build out a structured `purchase_frequency_days` attribute.
* **Redundancy Evaluation:** Verified correlation metrics between `discount_applied` and `promo_code_used`; dropped the redundant `promo_code_used` column to reduce dimensionality.
* **Database Pipeline Loading:** Configured an active SQL database engine connection and programmatically migrated the cleaned data frame into PostgreSQL/SQL Server.

### 2. SQL Server Analytics (Business Inquiries)
I structured 10 key business transactions to unpack operational questions directly from the database schema:
1. **Revenue by Gender:** Isolated spending parameters, showing Male demographics produced 157,890 in revenue vs. Female demographics at 75,191.
2. **High-Spending Discount Users:** Target-queried margin-compressed transactions by extracting clients using a discount while outspending the overall baseline ticket price average.
3. **Top 5 Products by Rating:** Identified optimal consumer market trust, isolating *Gloves (3.86)*, *Sandals (3.84)*, and *Boots (3.81)* as top-rated items.
4. **Shipping Tier Comparisons:** Computed ticket average variances between standard distribution formats (58 average spend) vs. express distribution formats (60 average spend).
5. **Subscription Tier Contribution:** Calculated revenue distributions across membership statuses, identifying non-subscribers generated 170,436 compared to subscribers at 62,645.
6. **Discount-Dependent SKUs:** Uncovered products highly reliant on margin price drops, led by *Hats* where 50% of purchases required active discounts.
7. **Customer Loyalty Segmentation:** Wrote custom segmenting logic to categorize the database into 3 segments: **3,116 Loyal customers**, **701 Returning customers**, and **83 New customers**.
8. **Top 3 Products Per Category:** Used window functions/rankings to map top inventory items (e.g., *Jewelry, Sunglasses, Belt* leading the Accessories category).
9. **Retention to Subscription Conversion:** Audited highly active buyers (>5 purchases) to evaluate cross-over metrics into active subscribers (1,053 subscribers vs 2,847 non-subscribers).
10. **Revenue by Age Group:** Measured exact revenue variations across generated age groups, with *Young-adult* leading contributions at 62,143.

### 3. Power BI Executive Interface Design
* **KPI Matrix Dashboarding:** Created clean summary metric points tracking overall customer count (4K), overall average spend ($59.76), and collective product satisfaction ratings (3.75).
* **Advanced Visual Cross-Filtering:** Configured dynamic multi-select filtering via subscription status, regional category, gender breakdowns, and shipping channels.
* **Distribution Mapping:** Plotted clear bar and donut visualizations capturing structural revenue breakdowns by product segment and age bracket volumes.

---

## 📈 Strategic Business Recommendations

* **Optimize the Subscription Conversion Loop:** While loyal customer retention segments are high, only ~27% of active shoppers are subscription members. The company should launch target promotions offering free express shipping to non-subscribers with high-frequency purchase history.
* **Mitigate Product Margin Degradation:** 47% to 50% of items like Hats, Coats, and Sneakers rely heavily on markdown promotions. Marketing campaigns should lean on highlighting high review ratings instead of running margin-compressing discount cycles.
* **Scale High-Value Demographic Campaigns:** Tailor future ad budgets toward the *Young-adult* and *Middle-aged* consumer categories, as they represent the highest total revenue brackets.

---

## 🚀 Skills Showcase
* **Python:** Pandas, Data Profiling, Feature Binning, Missing Value Imputation.
* **SQL Server / PostgreSQL:** Window Functions, Data Aggregations, Relational Table Writes, Multi-level Segmentation.
* **Power BI Desktop:** Executive KPI Modeling, Categorical Visualizations, User Interaction Controls, Dashboard Storytelling.
