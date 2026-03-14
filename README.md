**Spark Taxi Data Analytics & Streaming**
**Project Overview**

This project analyzes large-scale taxi trip data using distributed data processing techniques with Apache Spark. The objective is to explore batch analytics, SQL-based querying, real-time streaming pipelines, and low-level distributed transformations.

Using the NYC Yellow Taxi Trip dataset, the project demonstrates how modern big-data systems can process millions of records efficiently.

The implementation explores multiple Spark abstractions including:
1. Spark DataFrames
2. Spark SQL
3. Structured Streaming
4. RDD transformations

The project highlights how different Spark APIs can be used for batch analytics and real-time data processing pipelines.

**Dataset**

The dataset used is the NYC Yellow Taxi Trip Records, provided by the New York City Taxi & Limousine Commission.

It contains detailed records of taxi trips including:

pickup and drop-off timestamps

pickup and drop-off locations

passenger count

trip distance

fare amount

**Source:**

NYC Taxi & Limousine Commission

Data volume: Millions of trip records

For this project, one month of 2025 data was used to simulate large-scale processing.

Technologies Used:

1. Apache Spark
2. Spark SQL
3. Apache Spark Structured Streaming
4. Apache Parquet
5. Jupyter Notebook
6. Python (PySpark)

**Project Components**
**1. Data Processing with Spark DataFrames**

Taxi trip data was loaded and processed using Spark DataFrames.

Key tasks included:

- loading large CSV/Parquet datasets
- inspecting schema
- cleaning missing and invalid values
- performing distributed analytical queries

**Example analytics:**

1. Average trip distance per day
2. Top pickup locations by trip volume
3. Average fare per passenger count
4. Fare distribution for trips longer than 10 miles

These operations demonstrate Spark’s ability to perform large-scale distributed analytics efficiently.

**2.SQL-Based Analytics with Spark SQL**

The dataset was converted into a temporary SQL view and queried using Spark SQL.

Key queries included:

identifying peak taxi pickup hours

calculating daily revenue

detecting busiest pickup–drop-off routes

identifying suspicious trips with unusually high fares

This shows how SQL-based analysis can be performed directly on distributed datasets.

**3. Real-Time Streaming with Structured Streaming**

To simulate real-time data ingestion, a streaming dataset was created using Spark's rate source.

The streaming pipeline performed the following tasks:

generated simulated taxi trip events

computed rolling average fares

counted trips per pickup location using window operations

wrote streaming results to:

console output

memory tables

parquet files

This demonstrates how Apache Spark Structured Streaming enables real-time analytics pipelines.

**4. Distributed Transformations Using RDDs**

Low-level transformations were implemented using Resilient Distributed Dataset.

Operations performed:

Map: extract pickup location and fare

ReduceByKey: compute total fare per pickup location

Filter: identify trips with high passenger counts

This component illustrates the differences between Spark’s lower-level RDD API and higher-level abstractions.

**Results**

Key insights from the analysis include:

Identification of high-demand pickup zones

Peak taxi usage hours across the city

Revenue distribution across days

Detection of suspicious fare patterns

The project demonstrates how Spark enables scalable analytics on large transportation datasets.

**Key Learnings**

This project highlights the strengths of different Spark abstractions:

**Framework	Strength**
RDD	Low-level distributed control
DataFrames	Optimized structured analytics
Spark SQL	Familiar SQL-based analysis
Structured Streaming	Real-time data processing

Spark’s query optimizer improves performance by automatically optimizing execution plans.

**Real-World Applications**

The techniques used in this project can be applied to many real-world systems:

ride-sharing analytics platforms

transportation demand forecasting

fraud detection in transaction streams

real-time mobility dashboards

smart city infrastructure analytics

**Author**

Afeena Gafoor
Master’s Student – Business Analytics & AI
Ontario Tech University

**GitHub Portfolio:** https://github.com/AfeenaG
