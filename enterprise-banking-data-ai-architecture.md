# Enterprise Banking Data AI Platform V2 - Architecture

## Architecture Objective

The objective is to enable AI-assisted data access in banking without weakening governance, security, or compliance.

The platform separates structured metric questions from document knowledge questions:

- Metric, KPI, reporting, customer, account, card, and transaction questions use the governed semantic data path.
- Policy, glossary, procedure, runbook, and architecture questions use the document RAG path.

## Logical Layers

### 1. Source Layer

Representative banking source systems:

- Core banking
- CRM
- Cards platform
- Payments
- Accounts
- Transactions
- Oracle
- SQL Server
- PostgreSQL
- Files and reference data

### 2. Ingestion And Orchestration Layer

Supported ingestion patterns:

- Real-time CDC using Debezium.
- Streaming through Kafka.
- Batch orchestration using Airflow.
- Transformation using Spark and PySpark.

### 3. Lakehouse Layer

The lakehouse is organized using Apache Iceberg and medallion architecture:

- Bronze: raw CDC and batch landing.
- Silver: cleaned, standardized, validated data.
- Gold: curated business-ready data products.

Supporting components:

- Object storage such as MinIO/S3.
- Hive Metastore or compatible catalog.
- Spark SQL and Spark Thrift Server.

### 4. Semantic And Governance Layer

The semantic layer provides:

- Governed business views.
- Data virtualization.
- Approved metric definitions.
- Metadata and lineage.
- Security and masking rules.
- Business glossary alignment.

Denodo is used as the reference semantic/data virtualization layer in this architecture.

### 5. AI / Self-Service Layer

The AI layer includes:

- Prompt UI / Agent.
- LLM reasoning layer.
- Intent and entity extraction.
- Hybrid router.
- MCP-style tool selection.
- Governed SQL template execution.
- Document RAG retrieval.
- Grounded answer formatting.
- Answer validation.

### 6. Consumption Layer

Consumption channels:

- Power BI dashboards.
- Prompt-based self-service answers.
- Governed reports.
- Data engineering SQL tools.
- Audit and monitoring reports.

## Design Principle

```text
The LLM reasons and formats.
MCP controls tool execution.
Denodo governs structured facts.
Document RAG provides approved knowledge context.
The validator protects trust.
```

