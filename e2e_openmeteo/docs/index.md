<div class="hero-section" markdown="1">

<div class="hero-badge">Production-Ready ETL Pipeline</div>

# <span class="hero-title">OpenMeteo Weather ETL</span>

<p class="hero-subtitle">
End-to-end data engineering pipeline demonstrating modern ELT patterns, automated quality checks, and real-time orchestration. Built with industry-standard tools on a completely free tech stack.
</p>

[View on GitHub :fontawesome-brands-github:](https://github.com/a-chmielewski/endtoend-etl-openmeteo){ .custom-btn }
[See Dashboard :fontawesome-solid-chart-line:](#live-dashboard){ .custom-btn .custom-btn-secondary }

</div>

---

## :rocket: Project Highlights

<div class="feature-grid" markdown="1">

<div class="feature-card" markdown="1">
<div class="feature-icon">:material-pipeline:</div>

### **Production-Grade ELT**
Implements Extract-Load-Transform pattern with raw data lake, staging layer, and analytical marts following dimensional modeling best practices.
</div>

<div class="feature-card" markdown="1">
<div class="feature-icon">:material-check-decagram:</div>

### **Automated Quality Gates**
Great Expectations validates every batch before loading, preventing bad data from corrupting the warehouse with schema and range checks.
</div>

<div class="feature-card" markdown="1">
<div class="feature-icon">:material-refresh-auto:</div>

### **Incremental Processing**
Watermark-based ingestion fetches only new data, optimizing API usage and processing time while maintaining data freshness.
</div>

<div class="feature-card" markdown="1">
<div class="feature-icon">:material-calendar-clock:</div>

### **Airflow Orchestration**
DAG-based workflow runs hourly, handling retries, dependencies, and monitoring. Fully containerized for reproducible deployments.
</div>

<div class="feature-card" markdown="1">
<div class="feature-icon">:material-graph:</div>

### **dbt Transformations**
SQL-based transformations with built-in testing, documentation, and lineage tracking. Separates business logic from infrastructure.
</div>

<div class="feature-card" markdown="1">
<div class="feature-icon">:material-chart-box:</div>

### **BI-Ready Outputs**
Metabase dashboards provide self-service analytics with filters and drill-downs. Daily aggregations optimized for query performance.
</div>

</div>

---

## :bar_chart: Live Dashboard

<div class="dashboard-preview" markdown="1">

![Weather Analytics Dashboard](assets/dashboard.png)

**Interactive Metabase dashboard featuring:**

- Multi-city temperature comparison with time-series visualization
- Daily aggregations (min, max, avg temperature)
- Date range filters for custom analysis
- Responsive design for mobile and desktop

[View Full Dashboard Details →](dashboard.md){ .custom-btn }

</div>

---

## :building_construction: Architecture

The pipeline follows a modern medallion architecture with separation of concerns:

```mermaid
flowchart TB
    subgraph API["Data Source"]
        A[Open-Meteo API<br/>Weather Data]
    end
    
    subgraph Storage["Raw Data Lake"]
        B[MinIO S3<br/>Partitioned by Date/Hour]
    end
    
    subgraph Quality["Quality Gate"]
        F[Great Expectations<br/>Schema & Range Validation]
    end
    
    subgraph Database["Data Warehouse"]
        C[PostgreSQL Staging<br/>staging.weather_hourly]
        D[dbt Marts<br/>fct_city_day]
    end
    
    subgraph BI["Analytics Layer"]
        E[Metabase Dashboards<br/>Self-Service BI]
    end
    
    subgraph Orchestration["Workflow Management"]
        G[Apache Airflow<br/>Hourly Scheduling]
    end
    
    A -->|Extract| B
    B -->|Validate| F
    F -->|Pass| C
    C -->|Transform| D
    D -->|Visualize| E
    G -.->|Orchestrates| A
    G -.->|Orchestrates| B
    G -.->|Orchestrates| F
    G -.->|Orchestrates| C
    G -.->|Orchestrates| D
    
    style A fill:#1e2542,stroke:#00d4ff
    style B fill:#1e2542,stroke:#00d4ff
    style C fill:#1e2542,stroke:#00d4ff
    style D fill:#1e2542,stroke:#00d4ff
    style E fill:#1e2542,stroke:#00d4ff
    style F fill:#1e2542,stroke:#00d4ff
    style G fill:#1e2542,stroke:#00d4ff
```

**Key Design Decisions:**

- **Raw Data Persistence**: All source data stored in MinIO for reprocessability and audit trails
- **Quality-First**: Validation happens before database insertion, maintaining data integrity
- **Idempotent Operations**: Upsert logic allows safe pipeline reruns without data duplication
- **Incremental Processing**: Only fetches data after last successful load timestamp

[Detailed Architecture Documentation →](architecture.md){ .custom-btn }

---

## :hammer_and_wrench: Tech Stack

<div class="tech-stack" markdown="1">

<div class="tech-item" markdown="1">
**Python 3.9+**  
Core Language
</div>

<div class="tech-item" markdown="1">
**PostgreSQL 16**  
OLAP Database
</div>

<div class="tech-item" markdown="1">
**Apache Airflow 2.9+**  
Orchestration
</div>

<div class="tech-item" markdown="1">
**dbt Core 1.7+**  
Transformations
</div>

<div class="tech-item" markdown="1">
**Great Expectations**  
Data Quality
</div>

<div class="tech-item" markdown="1">
**MinIO**  
S3-Compatible Storage
</div>

<div class="tech-item" markdown="1">
**Metabase**  
BI & Dashboards
</div>

<div class="tech-item" markdown="1">
**Docker Compose**  
Infrastructure
</div>

</div>

!!! success "100% Free & Open Source"
    This entire stack runs on free, open-source tools. No cloud costs, no licensing fees. Perfect for learning, prototyping, and showcasing data engineering skills.

---

## :chart_with_upwards_trend: Key Metrics

<div class="stats-grid" markdown="1">

<div class="stat-card" markdown="1">
<span class="stat-value">5+</span>
<span class="stat-label">Technologies Integrated</span>
</div>

<div class="stat-card" markdown="1">
<span class="stat-value">24/7</span>
<span class="stat-label">Hourly Updates</span>
</div>

<div class="stat-card" markdown="1">
<span class="stat-value">100%</span>
<span class="stat-label">Data Quality Checks</span>
</div>

<div class="stat-card" markdown="1">
<span class="stat-value">4</span>
<span class="stat-label">European Cities</span>
</div>

</div>

---

## :books: Documentation

<div class="feature-grid" markdown="1">

<div class="feature-card" markdown="1">
### [:fontawesome-solid-database: Data Model](data_model.md)
Explore the schema design, dimensional models, and table relationships in the data warehouse.
</div>

<div class="feature-card" markdown="1">
### [:fontawesome-solid-check-circle: Data Quality](data_qulaity.md)
Learn about validation rules, expectations, and how bad data is prevented from entering the pipeline.
</div>

<div class="feature-card" markdown="1">
### [:fontawesome-solid-terminal: How to Run](how_to_run.md)
Step-by-step guide to deploy the pipeline locally with Docker, including troubleshooting tips.
</div>

<div class="feature-card" markdown="1">
### [:fontawesome-solid-project-diagram: dbt Lineage](dbt/index.html)
Interactive data lineage graph showing how raw data flows through transformations to final marts.
</div>

</div>

---

## :trophy: What Makes This Project Stand Out

!!! example "Industry Best Practices"
    - **Version Control**: All code, SQL, and configurations in Git
    - **Testing**: dbt tests validate data transformations automatically
    - **Documentation**: Self-documenting dbt models with descriptions
    - **CI/CD Ready**: Structured for deployment to production environments
    - **Monitoring**: Airflow tracks task success/failure with alerting capability
    - **Scalability**: Partition-based storage supports growing data volumes

!!! tip "Perfect for Data Engineering Portfolios"
    This project demonstrates comprehensive understanding of:
    
    - Building production-ready pipelines from scratch
    - Integrating multiple data engineering tools
    - Implementing data quality frameworks
    - Following dimensional modeling principles
    - Creating self-service analytics platforms
    - Containerizing data infrastructure

---

## :rocket: Quick Start

Ready to run it yourself?

[How to Run Locally →](how_to_run.md){ .custom-btn }
[View Source Code →](https://github.com/a-chmielewski/endtoend-etl-openmeteo){ .custom-btn .custom-btn-secondary }

---

<div style="text-align: center; color: #7a8ba3; padding: 2rem 0;">
Built with :material-heart: by <a href="https://github.com/a-chmielewski" style="color: #00d4ff;">Aleksander Chmielewski</a>
</div>
