# PySpark Fundamentals — Guided Labs on NYC Taxi Data

Hands-on labs working through the core of **Apache Spark's Python API**: DataFrames, Spark SQL, RDDs, batch ETL jobs, and Structured Streaming — applied to the [NYC TLC Yellow Taxi trip records](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page) (~3M trips/month, Parquet).

> **Provenance:** a guided learning project I completed to build practical PySpark skills, based on a lab structure by <!-- TODO(Danish): name/link the original repo or its author (your colleague?) -->, worked through together with a colleague. The notebook executions, queries, and analysis runs are my own; the lab scaffolding and workflow diagrams are from the original project.

## 🗂️ Labs

| Notebook | Covers |
|---|---|
| `Load-&-Simple-query.ipynb` | SparkSession setup, reading Parquet, schema inspection, first DataFrame queries |
| `Query-&-Create-RDD.ipynb` | The RDD layer under DataFrames — SparkContext, transformations vs. actions |
| `Load-&-Join.ipynb` | Multi-source loading (CSV + JSON), DataFrame joins, temp views, error logging |
| `SparkSQL.ipynb` | Spark SQL in depth — explicit `StructType` schemas, temp views, SQL-side joins and aggregations |
| `Spark-Streaming.ipynb` | Structured Streaming — `readStream`/`writeStream`, streaming aggregations, checkpointing |
| `Spark-Job-Load-Query.ipynb` | A batch ETL job: load taxi trips, filter multi-passenger trips, write partitioned Parquet to a reporting layer |
| `Final-Analysis.ipynb` | Consuming the ETL job's output for downstream analysis |

## 🏗️ Workflow

![project workflow](img/project-workflow.svg)

## 📦 Data

- **Small samples included** (`data/`): employee CSV + department-budget JSON used in the join/SQL labs
- **Taxi data not included** (47 MB Parquet): download `yellow_tripdata_2023-01.parquet` from the [TLC Trip Record Data page](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page) and place it in `data/`. Spark outputs, checkpoints, and warehouse artifacts are `.gitignore`d — the ETL notebooks regenerate them.

## 🚀 Setup

```bash
git clone https://github.com/danishmahmoodali/pyspark-fundamentals-lab.git
cd pyspark-fundamentals-lab
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt   # PySpark requires Java 8/11/17 on PATH
jupyter notebook notebooks/
```

## 🛠️ Tech stack

`Python` · `PySpark 3.5` (DataFrames, Spark SQL, RDDs, Structured Streaming) · `Parquet` · `Jupyter`
