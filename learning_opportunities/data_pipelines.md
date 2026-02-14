# Learning Opportunities: Data Pipelines for ML

> Context: Gaps identified while preparing for Canva Senior MLE - Visual Suite role.
> Goal: Strengthen data pipeline knowledge to complement existing K8s and Azure pipeline experience.

---

## 1. Apache Airflow (Priority: HIGH)

**Why learn this:**
- Industry-standard ML pipeline orchestration tool — very likely used at Canva or similar
- Fills the most visible gap: you have pipeline concepts but not the industry-standard tooling
- Python-native, so fast to pick up
- Allows you to confidently answer "how would you orchestrate this?" in interviews

**What to learn:**
- Key concepts: **DAG**, **Task**, **Operator**, **Sensor**, **XCom**, **Schedule**, **Backfill**
- How to define a DAG in Python
- Built-in operators (PythonOperator, BashOperator, etc.)
- Error handling, retries, and alerting
- How Airflow fits into the ML lifecycle (training pipelines, data refresh, model retraining)

**Learning plan (~4-6 hours):**
1. [ ] Watch a 30-60 min YouTube intro (search "Apache Airflow tutorial for ML engineers")
2. [ ] Install Airflow locally (`pip install apache-airflow`) or use Docker Compose quickstart
3. [ ] Build one simple DAG: ingest public data (e.g., weather API) → transform/clean → save to local DB or file
4. [ ] Add error handling and retries to the DAG
5. [ ] Be able to explain: "What is a DAG?", "How does Airflow schedule tasks?", "How would you use Airflow for ML model retraining?"

**How to talk about it in interviews:**
- "I've built equivalent orchestration with K8s CronJobs and custom scheduling — the concepts transfer directly. I've also explored Airflow and understand how DAGs, operators, and scheduling work."

**Your existing experience that connects:**
- K8s CronJobs pipeline (CSIRO) — same orchestration concept, different tool
- Azure 2M simulation pipeline — large-scale batch processing

---

## 2. Feature Stores (Priority: MEDIUM)

**Why learn this:**
- Sits at the intersection of data pipelines and ML serving — core to the enablement role
- Shows understanding of modern ML platform thinking
- Conceptual knowledge is sufficient — no need to build a full project

**What to learn:**
- What problem feature stores solve (training-serving skew, feature reuse)
- **Offline store** vs **Online store**
- Feature computation vs feature serving
- Why ML teams need them (consistency between training and inference)
- Key tools: **Feast** (open-source), Tecton, Hopsworks

**Learning plan (~1-2 hours):**
1. [ ] Watch one YouTube video on "What is a Feature Store" (Feast has good intros)
2. [ ] Read the Feast documentation overview (~15 min)
3. [ ] Understand the architecture: data source → feature transformation → offline/online store → serving
4. [ ] Be able to explain: "Why would a team use a feature store?", "What's the difference between offline and online serving?"

**How to talk about it in interviews:**
- "Feature stores solve the training-serving skew problem by providing a single source of truth for features used in both training and inference. I understand the offline/online store architecture and tools like Feast."

---

## 3. Data Pipeline Concepts at Web Scale (Priority: LOW — for awareness only)

**Why learn this:**
- Broader context for how data pipelines work at companies like Canva (billions of events)
- Not critical to learn deeply before the interview, but useful to speak about intelligently

**Topics to be aware of:**
- **Streaming vs batch pipelines**: Kafka for real-time events, Spark/Beam for batch processing
- **ETL vs ELT**: traditional extract-transform-load vs modern extract-load-transform (dbt)
- **Data quality/validation**: Great Expectations, dbt tests, schema validation
- **Monitoring**: pipeline health, data freshness, SLA tracking

**Learning plan (~1 hour, optional):**
1. [ ] Watch a high-level video on "Data Engineering for ML Engineers"
2. [ ] Skim the Kafka documentation intro to understand topics, producers, consumers
3. [ ] Be able to explain at a high level: "What's the difference between batch and streaming pipelines?"

**Your existing experience that connects:**
- Real-time anomaly detection at CSIRO and BoM
- Schema validation and data quality in HRM package
- Large-scale batch processing on Azure

---

## Summary

| Topic | Priority | Time Investment | Type |
|---|---|---|---|
| Apache Airflow | HIGH | 4-6 hours | Hands-on project |
| Feature Stores | MEDIUM | 1-2 hours | Conceptual (video + reading) |
| Web-scale pipeline concepts | LOW | 1 hour | Awareness (video) |

**Total estimated time: 6-9 hours**
