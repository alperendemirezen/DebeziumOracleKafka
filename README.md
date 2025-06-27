# Debezium Oracle CDC to Kafka

This project sets up a **Change Data Capture (CDC)** pipeline that automatically captures changes (INSERT, UPDATE, DELETE) from an **Oracle database** and streams them to **Apache Kafka** using **Debezium** and **Kafka Connect**.

# Purpose

To build a real-time data ingestion system where any change in the Oracle database is instantly published to a Kafka topic. This is useful for:

- Real-time analytics
- Microservice synchronization
- Event-driven architecture
- Data lake ingestion

# Technologies Used

- **Oracle XE** (source database)
- **Debezium Oracle Connector**
- **Kafka & Kafka Connect**
- **Docker Compose** (for container orchestration)
- **Kafka Topics** to stream change events (in JSON)

# How It Works

1. Oracle database starts with supplemental logging enabled.
2. Debezium Oracle Connector uses **LogMiner** to capture DML changes.
3. Kafka Connect loads the connector and pushes events into a Kafka topic (e.g., `dbz.DEZEBIUM.CUSTOMERS`).
4. You can consume the topic using `kafka-console-consumer` or integrate it into other systems.
