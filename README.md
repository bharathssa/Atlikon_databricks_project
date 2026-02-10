# FMCG Data Lakehouse Analytics: S3 to Power BI

## 📌 Project Overview
This project implements a **Modern Data Lakehouse Architecture** using **Databricks** and **AWS S3** for a Parent-Child organizational structure in the FMCG sector. The pipeline automates the ingestion, transformation, and aggregation of retail transaction data, moving from raw landing zones to actionable business insights in Power BI.

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

![Architecture Diagram 1](Images%20for%20readme%20file/architecture_1.png)
![Architecture Diagram 2](Images%20for%20readme%20file/architecture_2.png)

---

## 📊 Data Modeling (Star Schema)
The Gold layer is designed around a **Star Schema** to provide intuitive and performant querying for BI tools.

*   **Fact Table**: `Fact_Sales` (Transactions, quantities, amounts).
*   **Dimensions**: `Dim_Product`, `Dim_Store`, `Dim_Time`, `Dim_Customer`.

![Star Schema Diagram](Images%20for%20readme%20file/star_schema.png)

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
