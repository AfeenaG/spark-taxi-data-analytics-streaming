# Assignment 2: NY Taxi Cab Trips Analysis

## Objective

Perform exploratory data analysis (EDA) and statistical analysis on the New York City Taxi and Limousine Commission (TLC) trip data to uncover patterns in trip duration, distance, fares, and demand across boroughs and time periods.

## Dataset

- **Source**: [NYC TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
- **Format**: Parquet / CSV
- **Key Fields**:

| Field | Description |
|-------|-------------|
| `tpep_pickup_datetime` | Date and time when the meter was engaged |
| `tpep_dropoff_datetime` | Date and time when the meter was disengaged |
| `passenger_count` | Number of passengers in the vehicle |
| `trip_distance` | Elapsed trip distance in miles |
| `PULocationID` | TLC Taxi Zone where the meter was engaged |
| `DOLocationID` | TLC Taxi Zone where the meter was disengaged |
| `fare_amount` | Base fare computed by the meter |
| `tip_amount` | Tip amount for credit card payments |
| `total_amount` | Total amount charged to passengers |
| `payment_type` | How the passenger paid (credit card, cash, etc.) |

## Analysis Steps

### 1. Data Loading & Preprocessing
- Load raw trip data using **Apache Spark** or **Pandas**.
- Handle missing values, duplicates, and outliers.
- Parse datetime columns and derive new features (hour, day of week, month).

### 2. Exploratory Data Analysis (EDA)
- Distribution of trip distances and fares.
- Hourly and daily demand patterns (heatmaps).
- Most popular pickup and drop-off zones.
- Average trip duration by borough and time of day.

### 3. Statistical Analysis
- Correlation between trip distance and fare amount.
- Average tip percentage by payment type.
- Peak vs. off-peak fare comparison.

### 4. Visualizations
- Time-series plot of trip counts per hour/day.
- Bar charts of top 10 pickup/drop-off locations.
- Scatter plot of distance vs. fare.
- Heatmap of trip demand by hour and day of week.

## Tools & Technologies

| Tool | Purpose |
|------|---------|
| Apache Spark (PySpark) | Large-scale data loading and processing |
| Pandas | Local data manipulation and cleaning |
| Matplotlib / Seaborn | Static visualizations |
| Plotly | Interactive visualizations |
| Jupyter Notebook | Analysis and reporting |

## Key Findings (Summary)

- Trip demand peaks between **7–9 AM** and **5–7 PM** on weekdays.
- Midtown Manhattan accounts for the highest volume of pickups.
- Credit card payments make up the majority of transactions and correlate with higher tip amounts.
- Average trip distance is approximately **3–4 miles** with fares averaging **$12–15**.

## How to Run

1. Download the dataset from the NYC TLC website (e.g., Yellow Taxi trips for a chosen month).
2. Place the data file in the `data/` directory.
3. Open `ny_taxi_analysis.ipynb` in Jupyter Notebook.
4. Run all cells sequentially.

```bash
# Install dependencies
pip install pyspark pandas matplotlib seaborn plotly jupyter

# Launch Jupyter Notebook
jupyter notebook ny_taxi_analysis.ipynb
```

## References

- [NYC TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
- [PySpark Documentation](https://spark.apache.org/docs/latest/api/python/)
- [Pandas Documentation](https://pandas.pydata.org/docs/)
