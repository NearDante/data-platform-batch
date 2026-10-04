# System Architecture

## Goal

Production-style batch data platform for ingestion, transformation, data quality, Parquet and analytical processing with Python, SQL and DuckDB.

## Flow

~~~text
SOURCE DATA
    |
    v
Python Ingestion
    |
    v
Raw / Bronze
(JSON / Parquet)
    |
    v
Python + SQL + DuckDB
    |
    +------------------+
    |                  |
    v                  v
Data Quality       Curated Parquet
    |                  |
    +--------+---------+
             |
             v
       Analytical SQL
          DuckDB
             |
             v
        Data Products
~~~

## Production concerns

Incremental processing, idempotency, retries, backfills, partitioning, schema validation, data-quality checks and orchestration should be first-class concerns.

## Boundary

This complements the real-time search pipeline. Batch focuses on reproducible historical transformations and analytical datasets rather than online feature serving.
