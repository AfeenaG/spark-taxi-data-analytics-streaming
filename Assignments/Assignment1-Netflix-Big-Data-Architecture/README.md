# Assignment 1: Big Data Architecture for Netflix

## Objective

Design a comprehensive Big Data Architecture for Netflix that supports large-scale video streaming, personalized recommendations, and real-time analytics.

## Architecture Overview

Netflix handles massive volumes of data including user interactions, streaming events, and content metadata. The architecture follows a **Lambda Architecture** pattern combining batch and real-time (speed) processing layers.

```
                        ┌─────────────────────────────────────────────────┐
                        │                  DATA SOURCES                   │
                        │  User Events | Streaming Logs | Content Metadata│
                        └─────────────────────┬───────────────────────────┘
                                              │
                        ┌─────────────────────▼───────────────────────────┐
                        │              INGESTION LAYER                    │
                        │         Apache Kafka  |  AWS Kinesis            │
                        └──────────┬──────────────────────┬───────────────┘
                                   │                      │
               ┌───────────────────▼───┐      ┌──────────▼────────────────┐
               │     BATCH LAYER       │      │      SPEED LAYER          │
               │  Apache Spark / HDFS  │      │  Apache Flink / Spark     │
               │  (Historical data)    │      │  Streaming                │
               └───────────────────┬───┘      └──────────┬────────────────┘
                                   │                      │
                        ┌──────────▼──────────────────────▼───────────────┐
                        │              SERVING LAYER                      │
                        │   Apache Cassandra  |  Elasticsearch  |  Redis  │
                        └─────────────────────┬───────────────────────────┘
                                              │
                        ┌─────────────────────▼───────────────────────────┐
                        │           ANALYTICS & ML LAYER                  │
                        │  Recommendation Engine | A/B Testing | Reports  │
                        └─────────────────────────────────────────────────┘
```

## Key Components

### 1. Ingestion Layer
- **Apache Kafka**: Collects real-time streaming events (play, pause, search, ratings) from millions of users.
- **AWS Kinesis**: Supplementary stream processing for cloud-native data pipelines.

### 2. Storage Layer
- **HDFS / Amazon S3**: Distributed storage for raw and processed data (batch).
- **Apache Cassandra**: NoSQL database for low-latency, high-throughput user profile and viewing history reads.
- **Redis**: In-memory cache for session data and frequently accessed recommendation results.

### 3. Processing Layer
- **Batch Processing – Apache Spark**: Runs nightly ETL jobs to compute aggregate statistics, update recommendation models, and generate reports.
- **Stream Processing – Apache Flink**: Processes real-time user events to detect trends, update watch-progress in near real-time, and trigger instant notifications.

### 4. Serving Layer
- **Elasticsearch**: Powers content search and catalog browsing.
- **REST / GraphQL APIs**: Expose processed data to the Netflix client applications.

### 5. Analytics & ML Layer
- **Recommendation Engine**: Collaborative filtering and deep learning models (e.g., matrix factorization, neural collaborative filtering) trained on historical viewing data.
- **A/B Testing Platform**: Evaluates changes to ranking algorithms, UI features, and content thumbnails.

## Data Flow

1. User actions (play, pause, search, rate) are emitted as events.
2. Events are published to **Kafka** topics.
3. **Flink** consumes events in real-time to update watch progress and trending content.
4. **Spark** batch jobs run periodically to retrain recommendation models and generate aggregated reports.
5. Results are stored in **Cassandra / Redis** and served via APIs to client apps.

## Technologies Used

| Component | Technology |
|-----------|-----------|
| Message Broker | Apache Kafka |
| Batch Processing | Apache Spark |
| Stream Processing | Apache Flink |
| Distributed Storage | HDFS / Amazon S3 |
| NoSQL Database | Apache Cassandra |
| Cache | Redis |
| Search | Elasticsearch |
| ML / Recommendations | Spark MLlib / TensorFlow |
| Cloud Platform | AWS |

## References

- [Netflix Tech Blog](https://netflixtechblog.com/)
- [Apache Kafka Documentation](https://kafka.apache.org/documentation/)
- [Apache Spark Documentation](https://spark.apache.org/docs/latest/)
- [Apache Flink Documentation](https://flink.apache.org/)
