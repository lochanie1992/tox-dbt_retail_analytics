# Retail Analytics with dbt + Tox (Snowflake Edition)

## Project Overview

This project demonstrates a **complete retail analytics pipeline** using **dbt** on **Snowflake**, automated with **Tox** for reproducible execution. It is designed to showcase **best practices in data engineering**, including layered architecture, macros, testing, and documentation.

### Key Features

- **Layered Architecture**  
  - **Stage Layer (`stage`)**: Cleans and standardizes raw data tables (`raw_customers`, `raw_orders`, `raw_products`).  
  - **Intermediate Layer (`intermediate`)**: Performs transformations, joins, and enrichment, such as calculating discounted product prices using a **macro**.  
  - **Warehouse Layer (`warehouse`)**: Aggregates data into business-ready models (e.g., sales summaries) for reporting or analytics.

- **Macros**  
  - Reusable SQL logic like `calc_discount(price, discount_percent)`.  
  - Ensures **consistency and DRY principles** across models.

- **Testing**  
  - **Generic tests**: `not_null`, `unique` on key columns.  
  - **Custom tests**: e.g., ensuring order `quantity > 0`.  
  - Guarantees **data quality** and prevents downstream errors.

- **Documentation**  
  - Full model, column, and macro descriptions.  
  - Auto-generated lineage and documentation via `dbt docs generate`.

- **Tox Automation**  
  - Runs all dbt commands in a **clean Python environment**.  
  - Handles dependency installation, model compilation, execution, and tests.  
  - Ensures **reproducible local and CI/CD execution**.

- **Sample Data**  
  - Includes inserts for **customers, orders, and products** in Snowflake.  
  - Enables easy testing and demonstration of transformations and tests.


