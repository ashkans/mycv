# Learning Opportunities: Inference Optimisation & Serving Infrastructure

> Context: Gaps identified while preparing for Canva Senior MLE - Visual Suite role.
> Goal: This is the biggest gap relative to the role. Build conceptual fluency and be able to speak confidently about the key techniques and tools.

---

## Your Existing Strengths (foundation to build on)

- Kubernetes experience — serving infrastructure runs on K8s, so you already understand the orchestration layer
- End-to-end ML lifecycle ownership — you've taken models from training through to production deployment
- FastAPI — you've built API services, which is a building block for model serving
- Production model deployment — AWRA-L v7 (thousands of daily users), Random Forest anomaly detection (operationally deployed)

## The Gap

Your production models serve batch/scheduled predictions (daily CronJobs, on-demand runs). Canva needs **real-time, low-latency, high-throughput serving** for millions of concurrent users. You haven't worked with GPU serving, model serving frameworks, or inference optimisation techniques like quantization.

---

## 1. Inference Optimisation Concepts (Priority: HIGH)

**Why learn this:**
- Core to making ML features viable in production at Canva (fast + cheap enough to serve)
- Interviewers may ask: "A model is too slow for production — what do you do?"
- These techniques are universal across all ML serving, not tied to a specific framework

**What to learn:**

### Quantization
- **What**: Reducing model precision (FP32 → FP16 → INT8) to make inference faster and use less memory
- **Types**: Post-training quantization (easy, some accuracy loss) vs quantization-aware training (harder, less accuracy loss)
- **When**: Almost always the first thing to try — often 2-4x speedup with minimal quality loss

### Model Compilation & Runtime Optimisation
- **ONNX Runtime**: Convert models to ONNX format for optimised cross-platform inference
- **TensorRT** (NVIDIA): Compiles models for maximum GPU performance — commonly used for production serving
- **torch.compile** (PyTorch 2.0+): Built-in compilation for speedups without leaving PyTorch

### Batching
- **Dynamic batching**: Grouping incoming requests together to maximise GPU utilisation
- **Why it matters**: A GPU processing 1 request vs 32 requests takes nearly the same time — batching is essentially free throughput

### Other Techniques
- **Knowledge distillation**: Training a smaller "student" model to mimic a larger "teacher" model
- **Pruning**: Removing unnecessary weights/neurons from a model
- **Caching**: Caching frequent predictions or intermediate results (embedding caches, KV-cache for LLMs)
- **Profiling**: Identifying bottlenecks — is it preprocessing? model forward pass? postprocessing? network I/O?

**Learning plan (~1-2 hours):**
1. [ ] Watch a video on "ML inference optimisation" or "how to make ML models faster in production"
2. [ ] Read a blog post on quantization (Hugging Face has good practical guides)
3. [ ] Understand the optimisation decision tree: profile first → try quantization → try batching → try compilation → consider distillation
4. [ ] Be able to explain: "A model is too slow — walk me through how you'd optimise it"

**How to talk about it in interviews:**
- "I'd start by profiling to identify the actual bottleneck. If it's the model itself, I'd try quantization first — FP16 or INT8 — since it's often 2-4x faster with minimal quality loss. Then I'd look at dynamic batching to maximise GPU throughput, and model compilation with TensorRT or ONNX Runtime. If that's still not enough, I'd consider knowledge distillation to a smaller architecture."

---

## 2. Model Serving Frameworks (Priority: MEDIUM)

**Why learn this:**
- These are the standard tools Canva likely uses to serve models
- As an enablement engineer, you'd help teams choose and configure serving infrastructure
- Your K8s knowledge makes this a natural extension

**What to learn:**

### Key Frameworks
- **Triton Inference Server** (NVIDIA): Industry standard for GPU model serving. Supports multiple frameworks (PyTorch, TensorFlow, ONNX), dynamic batching, model versioning, ensemble pipelines
- **TorchServe** (PyTorch): Simpler, PyTorch-native serving. Good for teams already in the PyTorch ecosystem
- **vLLM**: Specialised for LLM serving — PagedAttention for efficient memory use, continuous batching. Very relevant for Canva's generative AI features
- **BentoML / Seldon Core / KServe**: Higher-level frameworks for packaging and deploying models on K8s

### Key Concepts
- **Model versioning**: Running multiple model versions simultaneously (for A/B testing, rollback)
- **gRPC vs REST**: gRPC is faster for model serving (binary protocol, streaming), REST is simpler
- **Health checks & readiness probes**: Ensuring models are loaded and ready before receiving traffic
- **Autoscaling**: Scaling replicas based on request queue depth, GPU utilisation, or latency targets

**Learning plan (~1 hour):**
1. [ ] Watch a video on "Triton Inference Server introduction" (~20 min)
2. [ ] Read the vLLM overview page (~10 min) — understand why it's important for LLM serving
3. [ ] Understand the serving architecture: load balancer → model server replicas (on K8s) → GPU inference → response
4. [ ] Be able to explain: "How would you serve a PyTorch model in production?", "What's the difference between Triton and TorchServe?"

**How to talk about it in interviews:**
- "For GPU model serving, I'd use Triton Inference Server or TorchServe deployed on K8s with GPU node pools. Triton is my default recommendation because it supports dynamic batching, model versioning, and multiple frameworks out of the box. For LLM serving specifically, vLLM with continuous batching and PagedAttention is the current best practice."

---

## 3. GPU Serving on Kubernetes (Priority: LOW — for awareness)

**Why learn this:**
- Connects your existing K8s knowledge to the GPU serving world
- Not critical to learn deeply, but useful to mention in interviews

**Topics to be aware of:**
- **GPU node pools**: Dedicated K8s nodes with GPUs (e.g., NVIDIA A100, T4)
- **NVIDIA device plugin**: How K8s schedules GPU resources to pods
- **GPU sharing**: MIG (Multi-Instance GPU), time-slicing — running multiple models on one GPU
- **Spot/preemptible instances**: Using cheaper GPU instances for non-critical workloads
- **Monitoring**: GPU utilisation, memory usage, inference latency per model

**Learning plan (~30 min, optional):**
1. [ ] Read a blog post on "running GPU workloads on Kubernetes"
2. [ ] Understand how K8s resource requests/limits work for GPUs (`nvidia.com/gpu: 1`)
3. [ ] Be able to explain: "How would you set up GPU serving on K8s?"

**Your existing experience that connects:**
- K8s CronJobs and pipeline orchestration at CSIRO
- Docker containerisation
- You just need to extend this mental model to include GPU scheduling

---

## Summary

| Topic | Priority | Time Investment | Type |
|---|---|---|---|
| Inference optimisation concepts | HIGH | 1-2 hours | Conceptual (video + reading) |
| Model serving frameworks | MEDIUM | 1 hour | Conceptual (video + docs) |
| GPU serving on K8s | LOW | 30 min | Awareness (blog post) |

**Total estimated time: 2.5-3.5 hours**

**Note:** This is your biggest gap area. Even conceptual fluency here will significantly strengthen your interview performance. Focus on being able to answer: "A model is too slow/expensive — what do you do?" and "How would you serve this model in production?"
