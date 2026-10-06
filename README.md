<div class="projects-grid">

  <div class="project-card">
    <span class="project-category">Batch ELT</span>
    <h3>OpenMeteo weather ELT</h3>
    <p>Hourly weather for four European cities. Open-Meteo data lands in MinIO, passes Great Expectations checks, and is modeled with dbt for Metabase. Airflow runs the load in Docker.</p>
    <p><strong>Stack:</strong> Python · PostgreSQL · dbt · Airflow · Metabase · Great Expectations · MinIO</p>
    <a href="e2e_openmeteo/index.html" class="project-link">View weather ELT</a>
  </div>

  <div class="project-card">
    <span class="project-category">Streaming</span>
    <h3>Binance trades pipeline</h3>
    <p>Binance aggregate trades go through Kafka and Spark Structured Streaming in 10-second micro-batches, then into Elasticsearch and Kibana. The stack runs in Docker Compose.</p>
    <p><strong>Stack:</strong> Python · Kafka · Spark · Elasticsearch · Kibana · Docker</p>
    <a href="streaming_data_pipeline/index.html" class="project-link">View streaming pipeline</a>
  </div>

  <div class="project-card">
    <span class="project-category">Lakehouse</span>
    <h3>Delta, Iceberg, and Hudi</h3>
    <p>The same NYC taxi path on Delta Lake, Apache Iceberg, and Apache Hudi, on EMR Serverless. Iceberg stored the sample in 174.5 MB. Delta and Hudi used about 348 MB.</p>
    <p><strong>Stack:</strong> AWS EMR · Spark · Delta Lake · Iceberg · Hudi · Athena · Glue</p>
    <a href="lakehouse_demo/index.html" class="project-link">View lakehouse comparison</a>
  </div>

  <div class="project-card">
    <span class="project-category">Cloud</span>
    <h3>Serverless FX ingestion</h3>
    <p>Daily ECB FX rates loaded with Terraform, Cloud Run, Cloud Scheduler, and BigQuery. The estimate for this small workload is about $0.32/month.</p>
    <p><strong>Stack:</strong> Terraform · GCP · Cloud Run · BigQuery · Cloud Scheduler · GitHub Actions</p>
    <a href="iaas_for_data/index.html" class="project-link">View FX ingestion</a>
  </div>

  <div class="project-card">
    <span class="project-category">Data quality</span>
    <h3>NYC 311 quality checks</h3>
    <p>NYC 311 requests in DuckDB. Pandera checks the API payload, Great Expectations runs before the dbt marts, and Plotly draws the metrics.</p>
    <p><strong>Stack:</strong> Python · DuckDB · dbt · Great Expectations · Pandera · Plotly</p>
    <a href="data_quality_testing_framework/index.html" class="project-link">View quality checks</a>
  </div>

</div>
