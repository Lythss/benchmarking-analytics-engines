# Benchmarking Analytical Engines on the TPC-H Dataset

## Overview

This project is a comprehensive benchmark study comparing analytical engines for large-scale data workloads. It evaluates performance, scalability, and storage optimization using the **TPC-H benchmark** on the **1BRC dataset**.

## Objectives

- Design a scalable and efficient analytical architecture.
- Evaluate memory-based (Polars, DuckDB) vs distributed (Dask, Spark) engines.
- Optimize data processing and query execution.
- Visualize query performance across storage formats and data scales.

## Benchmark Framework

The benchmark is built on the **TPC-H** standard and uses the **1BRC dataset** as the main data source ([1BRC GitHub](https://github.com/gunnarmorling/1brc)).

### Scale Factors:
- **SF10** â†’ 10% of dataset
- **SF50** â†’ 50% of dataset
- **SF100** â†’ 100% of dataset

### Analytical Queries:
Test of complex SQL queries with aggregations:
`MAX`, `MIN`, `AVG`, `SUM`, `COUNT`, `GROUP BY`, etc.

## Engines Compared

### In-Memory & Vectorized
- [Polars](https://www.pola.rs/)
- [DuckDB](https://duckdb.org/)

### Distributed & Scalable
- [Dask](https://www.dask.org/)
- [Apache Spark](https://spark.apache.org/)

## Storage Formats Evaluated

- Apache Parquet
- Apache ORC
- Delta Lake
- Apache Iceberg

Each storage format is assessed on:
- Execution time
- Compression rate
- Metadata handling
- Compatibility with engines

## Evaluation Metrics

- **Query Execution Time** (ms)
- **Scalability** across SF10, SF50, SF100
- **Ease of Implementation**
- **Data Format Efficiency**

## Results Visualization

Performance results are visualized using interactive plots:
- Query execution time comparisons
- Engine performance vs data scale
- Storage format impact

## Architecture

```
                          +------------------+
                          |   Data Sources   |
                          |  (1BRC, TPC-H)   |
                          +--------+---------+
                                   |
                          +--------v---------+
                          | Storage Formats  |
                          | (Parquet, ORC,   |
                          |  Delta, Iceberg) |
                          +--------+---------+
                                   |
                +------------------+------------------+
                |                                     |
       +--------v--------+                 +---------v--------+
       | Memory Engines  |                 | Distributed Eng. |
       | (Polars, DuckDB)|                 | (Dask, Spark)    |
       +--------+--------+                 +---------+--------+
                |                                    |
         +------v-------+                    +------v--------+
         | SQL Queries  |                    | Query Engines |
         +------+-------+                    +------+--------+
                |                                    |
         +------v-------+                    +------v--------+
         | Visualization |                  | Performance    |
         | Dashboards    |                  | Comparison     |
         +--------------+                  +----------------+
```

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/benchmarking-analytics-engines.git
   cd benchmarking-analytics-engines
   ```

2. Install required environments:
   - Python (3.10+)
   - Jupyter / VS Code
   - Docker (for Delta & Iceberg support)
   - Apache Spark / Dask / Polars / DuckDB

3. Load and convert datasets into each format.
4. Execute benchmark queries.
5. Generate visualizations.

## Resources

- [1BRC GitHub](https://github.com/gunnarmorling/1brc)
- [ClickHouse 1BRC Blog](https://clickhouse.com/blog/clickhouse-one-billion-row-challenge)
- [DuckDB TPC-H Docs](https://duckdb.org/docs/stable/extensions/tpch)

## License

This project is licensed under the MIT License.
