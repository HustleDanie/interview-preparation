# Round 4: Onsite — System Design — How to Pass It Excellently

> **Format**: Video call with virtual whiteboard (Excalidraw, Google Jamboard, or shared doc) | **Duration**: 45 – 60 min | **Interviewer**: Senior/Staff+ engineer (L6 – L7+), often from the target team or adjacent teams

---

## What This Round Actually Is

The system design round is where Big Tech evaluates whether you can **architect large-scale AI systems end-to-end**. This is not a coding round — you will not write production code. Instead, you'll draw boxes, discuss data flows, make trade-offs, and demonstrate that you can think about systems at **massive scale** (millions to billions of users, petabytes of data, sub-second latency).

This round is **the primary differentiator between mid-level and senior+ candidates**.

| Level | What's Expected |
|---|---|
| **L3 – L4** | Some companies skip this round. If included, expect a simpler, focused problem. You should be able to discuss components and basic trade-offs. |
| **L5 (Senior)** | This round is **critical**. You should drive the discussion, cover all major components, go deep on the AI/ML aspects, and make reasoned trade-offs. |
| **L6+ (Staff+)** | You should lead like you're running a design review. Discuss cross-service concerns, team boundaries, organizational trade-offs, and multi-quarter evolution. |

### What They're Evaluating (Formal Rubric)

| Criteria | Weight | What They Want to See |
|---|---|---|
| **Requirement gathering** | 🔴 Critical | Do you ask the right clarifying questions? Do you define scope before designing? |
| **High-level architecture** | 🔴 Critical | Can you lay out a coherent system with clear data flow between components? |
| **AI/ML depth** | 🔴 Critical (for AI roles) | Can you design the ML pipeline in detail? Model selection, training, serving, evaluation? |
| **Trade-off reasoning** | 🔴 Critical | Do you make explicit decisions and justify them? (Latency vs. throughput, cost vs. accuracy, etc.) |
| **Scale awareness** | 🟡 High | Do you think about what happens at 10x, 100x, 1000x scale? |
| **Data modeling** | 🟡 High | Can you design the data schema, storage choices, and data flow correctly? |
| **Production readiness** | 🟡 High | Do you discuss monitoring, failure modes, rollback, A/B testing? |
| **Communication** | 🟡 High | Can you drive a collaborative design discussion, not just monologue? |
| **Follow-up adaptability** | 🟢 Medium | When the interviewer changes constraints, can you adapt your design? |

---

## Before You Walk In: Core Knowledge Checklist

### Fundamental Building Blocks

You need to be able to **draw from memory** and explain the purpose of each:

| Component | What It Does | When to Use |
|---|---|---|
| **Load Balancer** | Distributes requests across servers | Any multi-server system (always) |
| **API Gateway** | Single entry point for clients, handles auth, rate limiting, routing | Multi-service architectures |
| **Application Server** | Runs business logic, serves API requests | Always |
| **Cache (Redis, Memcached)** | Fast in-memory storage for frequently accessed data | Read-heavy systems, reducing DB load |
| **CDN** | Serves static content from geographically distributed edge servers | User-facing content (images, models, static assets) |
| **Relational DB (PostgreSQL)** | Structured data with ACID transactions | User data, metadata, configuration |
| **NoSQL (DynamoDB, MongoDB)** | Flexible schema, high throughput | Log data, user activity, embeddings metadata |
| **Object Storage (S3)** | Large binary files — models, datasets, artifacts | Model storage, training data, evaluation results |
| **Message Queue (Kafka, SQS)** | Asynchronous event-driven communication between services | Decoupling services, event processing, data pipelines |
| **Vector Database (Pinecone, Weaviate, Qdrant, pgvector)** | Store and search high-dimensional vectors | Semantic search, RAG, recommendation, similarity |
| **Feature Store (Feast, Tecton)** | Store, serve, and version ML features | ML pipelines, consistent online/offline features |
| **Experiment Tracking (MLflow, W&B)** | Track training runs, hyperparameters, metrics | ML development lifecycle |
| **Model Registry** | Version and manage model artifacts | Model deployment and rollback |
| **Orchestrator (Airflow, Dagster)** | Schedule and manage complex data/ML pipelines | Training pipelines, batch processing |
| **Model Serving (Triton, vLLM, TGI)** | Run model inference at scale with batching and optimization | Real-time inference, LLM serving |
| **Kubernetes** | Container orchestration for deploying and scaling services | Any large-scale distributed system |

### AI/ML-Specific Components (This Is Your Differentiator)

For AI roles, the **ML pipeline** is where you should go deepest. Generic system design books won't cover this.

| Component | What to Discuss |
|---|---|
| **Data ingestion & cleaning** | How does raw data enter the system? What cleaning/validation happens? How do you handle data quality? |
| **Feature engineering** | What features are computed? Online (real-time) vs. offline (batch)? Feature store for consistency? |
| **Training pipeline** | Distributed training? GPU/TPU allocation? Hyperparameter tuning? Training data versioning? |
| **Model architecture** | Why this model? What are the alternatives? Trade-offs (accuracy vs. latency vs. cost)? |
| **Model evaluation** | Offline metrics, online evaluation (A/B test, shadow mode), human evaluation? |
| **Model serving** | Batch vs. online? Latency requirements? Batching strategy? Model compression? Caching? |
| **Feedback loop** | How do user signals improve the model? Label collection? Active learning? |
| **Monitoring** | Data drift, model drift, prediction quality monitoring, alerting? |
| **Model lifecycle** | Versioning, canary deployment, rollback, champion-challenger? |

---

## The 7-Step Framework: Your 45-Minute Battle Plan

### Step 1: Clarify Requirements (3 – 5 min)

**Never start designing without clarifying.** This is the #1 mistake candidates make. Jumping into a design without understanding requirements is the fastest way to fail.

**Functional requirements** — What does the system do?
> *"Let me make sure I understand what we're building. [Restate the problem]. The core user flows are: [1], [2], [3]. Is there anything I'm missing?"*

**Non-functional requirements** — How well does it need to do it?

Ask about each of these:
| Requirement | What to Ask | Why It Matters |
|---|---|---|
| **Scale** | "How many users? How many requests/sec? How much data?" | Determines architecture complexity |
| **Latency** | "What's the acceptable latency? Real-time or near-real-time?" | Online vs. batch architecture |
| **Availability** | "What's the availability target? 99.9%? 99.99%?" | Redundancy and failover design |
| **Consistency** | "Is strong consistency required, or is eventual consistency acceptable?" | Database and caching choices |
| **Cost** | "Are there budget constraints? Is there a cost-per-query target?" | Model choice, infrastructure decisions |
| **Data freshness** | "How fresh does the data need to be? Real-time updates or daily batch?" | Pipeline architecture |

**Define scope explicitly:**
> *"For this discussion, I'll focus on [core flow — e.g., the real-time inference path]. I'll cover [training pipeline] at a higher level and can deep-dive into it if we have time. Does that work?"*

### Step 2: Define the API / Interface (2 – 3 min)

Before designing internals, define the **external contract**.

> *"Let me define the core API endpoints:"*

```
POST /v1/recommend
  Input: { user_id: str, context: dict, num_results: int }
  Output: { items: [{ id: str, score: float, reason: str }], latency_ms: int }

POST /v1/feedback
  Input: { user_id: str, item_id: str, action: str (click/skip/purchase) }
  Output: { status: "ok" }
```

This shows the interviewer you think about systems from the **user's perspective**, not just the backend.

### Step 3: High-Level Architecture (8 – 10 min)

Draw the major components and data flow. **Start with the happy path** (the most common request flow).

**Template for an AI system:**

```
[Client] → [API Gateway / Load Balancer]
              ↓
         [Application Server]
              ↓                    ↓
    [Feature Store (online)]   [Cache (Redis)]
              ↓
    [Model Serving (Triton/vLLM)]
              ↓
    [Post-processing / Ranking]
              ↓
         [Response to Client]

--- Async / Batch path ---

[Event Stream (Kafka)] → [Data Pipeline (Spark/Airflow)]
       ↓                          ↓
[Feedback DB]            [Feature Store (offline)]
                                  ↓
                         [Training Pipeline]
                                  ↓
                         [Model Registry]
                                  ↓
                         [Model Serving (deploy)]
```

**Narrate as you draw:**
> *"The online path handles real-time requests. User request comes in through the API gateway, hits the application server, which fetches features from the online feature store and sends them to the model serving layer. The model returns predictions, which go through post-processing and ranking before returning to the user."*
>
> *"The offline path handles model training and improvement. User feedback events flow through Kafka into our data pipeline, which computes training features and stores them in the offline feature store. The training pipeline runs on a schedule, trains new models, stores them in the model registry, and deploys to serving after evaluation."*

### Step 4: Data Model & Storage (5 – 7 min)

Discuss what data is stored, where, and why.

| Data Type | Storage Choice | Reasoning |
|---|---|---|
| **User profiles** | PostgreSQL or DynamoDB | Structured, transactional, relatively small |
| **Item catalog** | PostgreSQL + Elasticsearch | Structured + full-text search |
| **User-item interactions** | Kafka → S3 (raw) + data warehouse | High volume, append-only, needed for training |
| **Embeddings** | Vector DB (Pinecone/Qdrant) | Fast ANN search for retrieval |
| **Features** | Feature Store (Feast/Tecton) | Consistency between online and offline |
| **Models** | S3 + Model Registry | Large binary files, versioned |
| **Cache** | Redis | Low-latency access for hot data |

**Discuss capacity estimates:**
> *"If we have 100M users and each generates 50 events/day, that's 5B events/day or ~58K events/sec. Each event is ~500 bytes, so ~2.5 TB/day of raw event data. We'll need a streaming pipeline (Kafka) and batch processing (Spark) to handle this volume."*

### Step 5: AI/ML Deep-Dive (10 – 15 min) — THIS IS YOUR SECTION

This is where you differentiate yourself from a generic software engineer. Go **deep** on the ML aspects.

#### Model Architecture

> *"For the recommendation model, I'd use a two-stage approach:"*
>
> **Stage 1 — Retrieval (candidate generation):**
> - *"Use a two-tower model (user embedding + item embedding) for fast candidate retrieval."*
> - *"Store item embeddings in a vector DB for approximate nearest neighbor search."*
> - *"This stage retrieves ~500 candidates in <10ms."*
>
> **Stage 2 — Ranking:**
> - *"Use a cross-attention model or gradient-boosted tree (GBDT) that takes rich features from both user and candidate."*
> - *"Features include: user history, item features, context (time, device, location), cross features."*
> - *"This stage scores ~500 candidates and returns the top-K."*
>
> *"Why two stages? Single-stage scoring all items is O(N) which is too slow at 100M items. Two-tower + ANN gives us O(log N) retrieval, and we only run the expensive ranker on a small candidate set."*

#### Training Pipeline

> *"Training runs daily on the previous day's data. Architecture:"*
> - *"Data: user interactions from the last 30 days, stored in the data warehouse."*
> - *"Features: computed via Spark jobs, written to the offline feature store."*
> - *"Training: distributed training on a GPU cluster (8 × A100). Using PyTorch + DDP."*
> - *"Hyperparameter tuning: Bayesian optimization via W&B Sweeps."*
> - *"Evaluation: offline metrics (NDCG, MAP, HR@K) + online A/B test."*
> - *"Deployment: new model goes through shadow mode for 24h, then gradual rollout (5% → 25% → 100%)."*

#### Feature Engineering

> *"Key features for the ranking model:"*

| Feature Type | Examples | Computation |
|---|---|---|
| **User features** | Watch history embedding, avg session length, preferred genres | Batch-computed daily, stored in feature store |
| **Item features** | Content embedding, popularity score, freshness | Batch-computed or pre-indexed |
| **Cross features** | User-item similarity, genre match score | Computed at request time (online) |
| **Context features** | Time of day, device type, country | Extracted from request |
| **Real-time signals** | Recent clicks, current session items | Streamed via Kafka, stored in Redis |

#### Evaluation Strategy

> *"I'd use a layered evaluation approach:"*
> 1. **Offline evaluation**: NDCG@10, MAP@10, Hit Rate@10 on a held-out test set.
> 2. **Shadow mode**: New model runs in parallel with production model. Compare outputs without affecting users.
> 3. **A/B test**: Serve new model to 5% of traffic. Compare engagement metrics (CTR, session length, retention).
> 4. **Guardrail metrics**: Monitor for regressions in diversity, freshness, and safety metrics.

### Step 6: Scale, Reliability, and Production Concerns (5 – 8 min)

This is where you show **systems maturity**.

#### Scaling

| Challenge | Solution |
|---|---|
| **High QPS (100K+ req/sec)** | Horizontal scaling of app servers behind load balancer. Auto-scaling based on CPU/latency. |
| **Model serving throughput** | GPU-based serving with batching (Triton Inference Server). Multiple replicas. |
| **Vector search latency** | Sharded vector DB with replicas. Pre-filter to reduce search space. |
| **Feature serving latency** | Online feature store with Redis-backed cache. Pre-materialize common features. |
| **Training on large datasets** | Distributed training with data parallelism. Incremental training instead of training from scratch. |

#### Reliability

| Failure Mode | Mitigation |
|---|---|
| **Model serving crashes** | Multiple replicas, health checks, automatic restart. Fallback to a simpler model or cached results. |
| **Feature store unavailable** | Default feature values. Graceful degradation (use cached features or skip personalization). |
| **New model performs worse** | Canary deployment with automatic rollback on metric regression. Champion-challenger pattern. |
| **Data pipeline failures** | Retry logic, dead-letter queue, alerting. Training skips if data quality is below threshold. |
| **Surge traffic** | Rate limiting, request queuing, auto-scaling. Serve cached/simpler results under load. |

#### Monitoring

> *"I'd monitor at three levels:"*

| Level | What to Monitor | Alert On |
|---|---|---|
| **System** | Latency (p50, p95, p99), throughput (QPS), error rate, CPU/GPU utilization | p99 latency > SLA, error rate > 0.1%, GPU OOM |
| **Model** | Prediction distribution, feature distributions, embedding drift | Distribution shift > threshold, sudden prediction skew |
| **Business** | CTR, engagement, user satisfaction, revenue per user | Metric drops > 5% (A/B test guardrail breach) |

### Step 7: Trade-Offs and Future Evolution (3 – 5 min)

End your design by explicitly discussing the **key trade-offs** you made and the **evolution path**.

**Trade-offs narration:**
> *"The key trade-offs in this design are:"*
> 1. *"Two-stage retrieval vs. single-stage: We trade some recall for massive latency improvement. At 100M items, this is necessary."*
> 2. *"Batch feature computation vs. real-time: We compute most features in batch for cost efficiency, but stream real-time signals for freshness. Trade-off: features are at most 24 hours stale."*
> 3. *"Daily retraining vs. online learning: Daily is simpler and more stable, but we miss intra-day trends. V2 could add online learning for trending content."*

**Evolution roadmap:**
> *"For V2, I'd consider:"*
> - *"Multi-modal features (integrating image/video understanding into embeddings)."*
> - *"Exploration-exploitation: adding a bandit layer for new items."*
> - *"Cross-platform personalization (sharing user context across mobile and web)."*
> - *"LLM-based explanation generation for recommendations."*

---

## Common System Design Prompts at Big Tech (with Approach Hints)

### AI Engineer Prompts

| Prompt | Key Components to Discuss |
|---|---|
| "Design a RAG-based Q&A system" | Document pipeline (chunking, embedding, indexing), retrieval (vector search + reranking), generation (LLM with context), evaluation (faithfulness, relevance), scale |
| "Design a content moderation system" | Multi-modal classification (text + image), real-time inference, human-in-the-loop, policy rules engine, appeals process |
| "Design a search ranking system" | Query understanding, candidate retrieval, learning-to-rank, A/B testing, feature engineering, freshness vs. relevance |
| "Design a chatbot / conversational AI platform" | Intent recognition, dialogue management, context/memory, multi-turn handling, safety filtering, escalation to human |
| "Design a notification/recommendation system" | User modeling, timing optimization, multi-channel delivery, feedback loop, do-not-disturb logic |

### AI Systems Engineer Prompts

| Prompt | Key Components to Discuss |
|---|---|
| "Design an ML training platform" | Multi-framework support, distributed training, GPU scheduling, experiment tracking, model registry, hyperparameter tuning |
| "Design a model serving platform" | Multi-model support, dynamic batching, canary deployment, auto-scaling, GPU management, latency SLOs |
| "Design a feature store" | Online vs. offline stores, point-in-time correctness, feature versioning, backfill, monitoring |
| "Design a data labeling platform" | Task distribution, annotator agreement, active learning, quality monitoring, annotation UI |
| "Design a real-time ML inference pipeline" | Streaming ingestion, feature computation, model inference, result delivery, monitoring at each stage |

### AI Agentic Engineer Prompts

| Prompt | Key Components to Discuss |
|---|---|
| "Design an AI agent platform (like GPTs/Assistants)" | Agent definition, tool registry, memory/context, orchestration, safety, multi-agent coordination |
| "Design a code generation and execution system" | Code generation (LLM), sandboxed execution, test validation, iterative refinement, security |
| "Design an autonomous workflow automation system" | Task decomposition, tool calling, error recovery, human approval gates, cost management |
| "Design a multi-agent collaboration system" | Agent roles, communication protocol, shared state, conflict resolution, orchestration layer |

---

## Company-Specific System Design Nuances

| Company | What to Emphasize |
|---|---|
| **Google** | Scale (billions of users), global infrastructure, data processing (BigQuery, Spanner, Bigtable). They love discussion of data pipelines and distributed systems. |
| **Meta** | Social graph, real-time features, ranking systems. Emphasis on "Move Fast" — discuss how you'd build an MVP and iterate. |
| **Amazon** | AWS services knowledge helps. Discussed through the lens of their Leadership Principles (especially "Customer Obsession" and "Dive Deep"). |
| **Apple** | Privacy-preserving design (on-device ML, differential privacy, federated learning). Less about pure scale, more about user experience. |
| **Microsoft** | Enterprise-focused. Think about multi-tenancy, compliance, integration with existing systems (Azure services). |
| **OpenAI / Anthropic** | LLM-specific: serving infrastructure, safety filtering, cost optimization, evaluation. Less generic system design, more AI-specific. |
| **NVIDIA** | GPU optimization, inference throughput, CUDA kernels, hardware-aware design. The most systems-focused. |

---

## Common Mistakes That Kill Your Score

| Mistake | Why It's Fatal | What to Do Instead |
|---|---|---|
| **Jumping into components without requirements** | Shows you build without understanding the problem. | Always spend 3 – 5 min on requirements. |
| **Drawing boxes without explaining data flow** | Architecture without data flow is meaningless. | Narrate how a request flows through the system, end to end. |
| **Ignoring the ML pipeline** | For AI roles, this is the core of the design. Generic system design = generic candidate. | Spend 10 – 15 min on the ML components. This is YOUR section. |
| **Not discussing scale** | Big Tech operates at massive scale. Not addressing it = not ready for Big Tech. | Always ask about QPS, data volume, user count. Design for it. |
| **Monologuing for 40 minutes** | The interviewer is not a wall. System design is a **conversation**. | Pause at each step: "Does this make sense? Any concerns before I continue?" |
| **Being vague on trade-offs** | "It depends" without specifics = no signal. | Be explicit: "I chose X over Y because [specific reason]. The trade-off is [downside]." |
| **Not discussing failure modes** | Shows you've never operated a real system. | Discuss at least 3 failure scenarios and their mitigations. |
| **Overcomplicating the design** | Adding Kafka, Redis, Elasticsearch, vector DB, feature store to a system with 100 users. | Match complexity to scale. Ask about scale first, then design accordingly. |

---

## Quick Reference: The 7 Steps on a Card

```
┌─────────────────────────────────────────────────────┐
│ SYSTEM DESIGN — 45-MINUTE FRAMEWORK                │
├─────────────────────────────────────────────────────┤
│ 1. REQUIREMENTS (3 – 5 min)                        │
│    Functional + Non-functional + Scope definition   │
│                                                     │
│ 2. API / INTERFACE (2 – 3 min)                     │
│    Define the external contract                     │
│                                                     │
│ 3. HIGH-LEVEL ARCHITECTURE (8 – 10 min)            │
│    Major components + data flow + happy path        │
│                                                     │
│ 4. DATA MODEL & STORAGE (5 – 7 min)                │
│    Schema + storage choices + capacity estimates    │
│                                                     │
│ 5. AI/ML DEEP-DIVE (10 – 15 min) ⭐ YOUR SECTION  │
│    Model → Training → Serving → Features → Eval    │
│                                                     │
│ 6. SCALE & PRODUCTION (5 – 8 min)                  │
│    Scaling + Reliability + Monitoring               │
│                                                     │
│ 7. TRADE-OFFS & EVOLUTION (3 – 5 min)              │
│    Key decisions + V2 roadmap                       │
└─────────────────────────────────────────────────────┘
```
