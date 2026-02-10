# FMCG Data Lakehouse Analytics: S3 to Power BI

## 📌 Project Overview
This project demonstrates an end-to-end Modern Data Lakehouse implementation specifically designed for the FMCG (Fast-Moving Consumer Goods) sector. It addresses the complex data engineering challenge of aggregating high-volume retail transactions from distributed 'Child' entities into unified monthly reporting for a 'Parent' organization. 

Leveraging Databricks and AWS S3, the solution utilizes a Medallion Architecture to ensure data quality, lineage, and high-performance analytics, ultimately serving actionable insights via Power BI and AI-driven natural language querying (Genie)

### Key Objectives:
*   Build a robust **Medallion Architecture** (Bronze, Silver, Gold).
*   Automate ETL using **Databricks Lakeflow Jobs**.
*   Implement complex **Parent-Child Rollup Logic** for financial reporting.
*   Enable Generative AI insights via **Databricks Genie**.

---

## 🏗️ Architecture Design
The project follows the standard Medallion pattern focused on data quality and lineage:

1.  **Raw Ingestion (S3 Landing)**: Automated ingestion of CSV, JSON, and Parquet files.
2.  **Bronze Layer**: Raw history storage in Delta tables (Append-only).
3.  **Silver Layer**: Cleaned, standardized, and enriched data joined with reference dimensions.
4.  **Gold Layer**: Aggregated business-level tables modeled for high-performance analytics.
5.  **Rollup Logic**: Aggregates daily Child Company transactions into monthly Parent Company totals.
6.  **Serving Layer**: Optimized SQL Views for Power BI and Genie integration.

![Architecture Diagram 1](consolidated_pipeline/Images%20for%20readme%20file/architecture_1.png)
![Architecture Diagram 2](consolidated_pipeline/Images%20for%20readme%20file/architecture_2.png)

---

## 📊 Data Modeling (Star Schema)
The Gold layer is designed around a **Star Schema** to provide intuitive and performant querying for BI tools.

![Star Schema Diagram](consolidated_pipeline/Images%20for%20readme%20file/star_schema.png)

---

---
## 📊 Dashboard (Power Bi)
Developed an interactive performance dashboard to provide immediate visibility into core KPIs and high-value customer and product metrics.

![Dashboard](consolidated_pipeline/Images%20for%20readme%20file/Dashbaord.png)

---

## 🛠️ Project Structure
```bash
.
├── 0_data                  # Sample data and landing zones
├── 1_codes                 # Databricks Notebooks
│   ├── 1_setup             # Environment and schema configuration
│   ├── 2_dimension         # Dimension table processing
│   └── 3_fact              # Fact table processing and Rollup logic
├── 2_dashboarding          # Power BI / SQL Dashboards
└── resources               # Architectural assets and documentation
```

---

## 🚀 How to Run
1.  **Setup**: Execute notebooks in `1_setup` to initialize databases and schemas.
2.  **Dimension Processing**: Run notebooks in `2_dimension` to populate master data.
3.  **Fact & Rollup**: Execute `3_fact` to process daily transactions and generate Parent-level monthly rollups.
4.  **Visualization**: Connect the Gold SQL Views to Power BI or use Databricks SQL Dashboards.

---

## ✨ Features
*   **Unity Catalog**: Centralized governance and discovery.
*   **Delta Lake**: Ensuring ACID transactions and time travel capability.
*   **Parent-Child Rollup**: Multi-level organizational data synthesis.
*   **AI Serving**: Ready for natural language querying with Genie.

---
*Created and Maintained by [bharathssa]*
