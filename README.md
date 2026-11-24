# Insurance Domain Medallion Lakehouse Pipeline

An end-to-end **Medallion Architecture (Bronze, Silver, Gold)** data engineering pipeline built with **Python, Pandas/PySpark, and Parquet/Delta Lake patterns**.

## Architecture Flow
- **Bronze Layer:** Raw immutable Parquet ingestion from JSON landing batches.
- **Silver Layer:** Deduplication and automated quarantine (`quarantine_claims`) for `NULL` foreign keys and invalid claim amounts.
- **Gold Layer:** Star Schema fact table (`fact_policy_claims`) and regional KPI mart (`gold_regional_claims_kpi`) ready for Power BI.

## Quick Start
```bash
pip install pandas pyarrow
python data/synthetic_generator.py
python pipelines/medallion_pipeline.py