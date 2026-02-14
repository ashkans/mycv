# Interview Prep Report: Canva Senior MLE - Visual Suite

> Generated from a detailed requirement-by-requirement analysis of the job ad against CV and experience.

---

## Skills Assessment Overview

| # | Requirement | Strength | My Experience (Keywords) | Learning Opportunities | Priority | Time |
|---|---|---|---|---|---|---|
| 1 | Python expertise + ML frameworks | **Strong** | Python (expert), PyTorch (LSTM), Scikit-learn (RF), LangChain (LLM) | — | — | — |
| 2 | Commercial K8s experience | **Strong** | K8s CronJobs, pipeline orchestration, Docker, CI/CD | — | — | — |
| 3 | Building data pipelines | **Strong** (tooling gap) | K8s real-time pipeline, Azure 2M simulations, anomaly detection, ETL | Apache Airflow (hands-on), Feature Stores (conceptual), web-scale concepts | HIGH | 6-9 hrs |
| 4 | Model evaluations | **Strong** (framing gap) | Baseline comparisons, temporal eval, 20+ publications, NeurIPS reviewer | LLM evaluation (LLM-as-judge, red-teaming), A/B testing basics | HIGH / MED | 1.5-2.5 hrs |
| 5 | Inference optimisation & serving | **Weak** (biggest gap) | K8s, Docker, FastAPI, production model deployment (batch) | Quantization/ONNX/batching, Triton/vLLM, GPU serving on K8s | HIGH | 2.5-3.5 hrs |
| 6 | Supporting research/DS/product teams | **Very strong** | Led team of 3, directed team of 4, supervised 8 students, cross-agency work | — | — | — |
| 7 | Debugging across full ML stack | **Very strong** | Data (anomaly tools), training (LSTM/RF), infra (K8s/Azure), cross-language (C++/C) | — | — | — |
| 8 | Context-switching across projects | **Very strong** | 6 concurrent projects at CSIRO, multiple parallel at BoM, side projects | — | — | — |
| 9 | Communication for varied audiences | **Very strong** | 20+ publications, 20+ conference talks, NeurIPS reviewer, technical reports, team leadership | — | — | — |
| 10 | Collaborative / enabling mindset | **Very strong** | HRM blueprint for other teams, team leadership, 8 students supervised, "force multiplier" | — | — | — |
| 11 | Java (not tested) | **None** | Cross-language experience: C++, C, TypeScript — will learn on the job | Not needed before interview | — | — |
| 12 | Terraform exposure | **None** (adjacent skills) | K8s YAML manifests, Azure, Docker, CI/CD — same IaC mindset | Watch 12 min of intro videos | LOW | 12 min |

**Total learning time (HIGH + MEDIUM only): ~10-15 hours | All items: ~11-16 hours**

---

## What to Say at the Interview

### Your Core Narrative

> "My career has been about taking complex ML problems, building robust solutions, and making them accessible to others. At CSIRO I ran six projects simultaneously across different ML domains — from PyTorch LSTMs to K8s pipelines to LLM workflows. At BoM I owned a national operational model while leading two separate teams. Throughout all of this, I've communicated findings through 20+ publications and conference talks, built reusable blueprints for other teams, and mentored 8 students. The enablement role at Canva is essentially what I've been doing — just in a different domain."

### Key Talking Points by Requirement

**1. Python + ML Frameworks:**
- "Expert-level Python. I've built production systems with PyTorch (LSTM for streamflow), Scikit-learn (Random Forest anomaly detection on 1M+ data points), and LangChain (LLM workflows). I also enforce engineering rigour: typed APIs, schema validation, 90%+ test coverage."

**2. Kubernetes:**
- "I've built and operated K8s CronJob-based pipelines for real-time data processing at CSIRO. I understand pod scheduling, resource management, and debugging in K8s environments."

**3. Data Pipelines:**
- Lead with the K8s CronJobs pipeline (real-time ECMWF data, anomaly detection, reduced latency by 25%).
- Mention Azure pipeline scale (2M+ simulations, months reduced to hours).
- Bridge to their context: "I've built equivalent orchestration with K8s — the concepts transfer directly to tools like Airflow."

**4. Model Evaluations:**
- "For every model I've built, I've designed rigorous evaluation frameworks — baseline comparisons, held-out test sets, temporal cross-validation, and domain-specific metrics. My LSTM work achieved 20% improvement over baselines through systematic evaluation across multiple forecast horizons."
- Bridge: "At Canva, evaluation also means online experimentation and LLM evaluation. The principles are the same — define clear metrics, establish baselines, test rigorously."

**5. Inference Optimisation & Serving (your biggest gap — be honest, then bridge):**
- "My production deployment experience has been in batch and scheduled inference on K8s. I understand the orchestration and deployment side well. The real-time serving and optimisation layer — quantization, dynamic batching, Triton — is an area I'm actively deepening. My K8s experience gives me a strong foundation to ramp up quickly."

**6. Supporting Teams:**
- HRM blueprint story: "I designed a package architecture that other teams at CSIRO now follow as their standard blueprint. That's the force-multiplier impact I want to bring to Canva."
- BoM leadership: "I led teams of 3-4 scientists and supervised 8 students, consistently bridging research methodology and production engineering."

**7. Debugging:**
- Have one concrete STAR story ready. Best candidates:
  - K8s pipeline debugging (data layer → infra layer → root cause → automated prevention)
  - LSTM convergence debugging (data → architecture → hyperparameters → solution)
  - C++ SWIFT codebase (navigating unfamiliar large codebase in a different language)

**8. Context-Switching:**
- "At CSIRO I managed six concurrent projects: HRM package, LSTM model, K8s pipeline, Macquarie analysis, data quality tool, and LLM workflow — all in different ML domains."

**9. Communication:**
- "20+ peer-reviewed publications, 20+ international conference talks, NeurIPS reviewer. I've communicated to audiences ranging from academic researchers to emergency services to government agencies."

**10. Collaborative / Enabling Mindset:**
- "The HRM blueprint, the team leadership, the student supervision — my career has been about making others more effective, not just solving problems myself."

**11. Java:**
- "I haven't worked in Java, but I've contributed to large C++ and C codebases alongside Python. Picking up a new language isn't the hard part — understanding the system architecture is, and I've done that repeatedly."

**12. Terraform:**
- "I haven't used Terraform directly, but I work with K8s manifests and CI/CD pipelines — the declarative IaC pattern is familiar. I'd pick it up quickly."

---

## STAR Stories to Rehearse

### Story 1: HRM Blueprint (hits: enabling, debugging, communication, pipelines)
- **Situation:** CSIRO needed a production-ready ML package for hydrological modelling
- **Task:** Architect a system that other teams could reuse and follow
- **Action:** Built plugin-based architecture with typed APIs, schema validation, 90%+ test coverage, full CI/CD
- **Result:** Other teams now follow it as their standard blueprint — force multiplier impact

### Story 2: K8s Real-Time Pipeline (hits: data pipelines, debugging, K8s, infrastructure)
- **Situation:** Daily ECMWF climate forecasts needed automated processing with quality checks
- **Task:** Build a reliable, real-time data pipeline
- **Action:** Designed K8s CronJob-based pipeline with anomaly detection
- **Result:** Reduced latency by 25%, automated data quality monitoring

### Story 3: Six Concurrent Projects (hits: context-switching, collaboration, organisational skills)
- **Situation:** Multiple high-priority projects running simultaneously at CSIRO
- **Task:** Deliver across all workstreams without dropping quality
- **Action:** Managed HRM, LSTM, K8s pipeline, Macquarie analysis, data quality tool, and LLM workflow concurrently
- **Result:** All delivered successfully across diverse ML domains

### Story 4: BoM Team Leadership (hits: collaboration, mentoring, communication)
- **Situation:** Needed to adapt JULES model for Australian conditions + prepare research reports
- **Task:** Lead two separate teams (3 + 4 people) while owning a national operational model
- **Action:** Directed technical work, translated findings into reports for varied stakeholders
- **Result:** Successful model adaptation, published findings, maintained operational system serving thousands daily

---

## Overall Assessment

**Strongest areas (differentiators):** Enablement mindset, communication, cross-team collaboration, context-switching, debugging breadth, scientific rigour

**Solid areas (meet requirements):** Python/ML frameworks, K8s, data pipelines, model evaluations

**Gap areas (needs learning):** Inference optimisation & serving (biggest gap), modern orchestration tools (Airflow), LLM evaluation, Terraform/Java (minor)

**Strategic positioning:** Most competing candidates will have stronger inference/serving experience from big tech. Your edge is the combination of technical breadth + communication + enablement mindset + cross-team leadership. Lean into the "force multiplier" narrative — it's the core of this role and your strongest match.
