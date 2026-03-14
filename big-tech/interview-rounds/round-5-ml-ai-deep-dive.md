# Round 5: Onsite — ML/AI Deep-Dive — How to Pass It Excellently

> **Format**: Video call, conversational with whiteboard/doc for diagrams | **Duration**: 45 – 60 min | **Interviewer**: ML Scientist, Senior AI Engineer, or Research Engineer (L5 – L7+)

---

## What This Round Actually Is

The ML/AI deep-dive is the round that separates **AI engineers from software engineers who happen to use AI APIs**. While the system design round tests whether you can architect a large system, this round tests whether you **deeply understand the AI/ML components** that power it.

This round is unique to AI roles. A generic SWE candidate doesn't face it. It's your **biggest competitive advantage** if you're prepared, and your **biggest vulnerability** if you're not.

### How It Differs From System Design

| Dimension | System Design Round | ML/AI Deep-Dive Round |
|---|---|---|
| **Focus** | End-to-end system architecture | The ML/AI components specifically |
| **Depth vs. breadth** | Broad — covers frontend to backend to data to ML | Deep — one or two ML topics explored exhaustively |
| **Questions feel like** | "Design a recommendation system" | "How does the attention mechanism work? Walk me through the math." |
| **You're evaluated on** | Architecture, trade-offs, scale | ML knowledge, model intuition, practical experience, research awareness |
| **Drawing** | System diagrams, data flow | Model architectures, training curves, data distributions, evaluation charts |

### What They're Evaluating (Formal Rubric)

| Criteria | Weight | What They Want to See |
|---|---|---|
| **ML fundamentals** | 🔴 Critical | Deep understanding of core ML concepts — not memorized definitions, but real intuition |
| **Model intuition** | 🔴 Critical | Can you reason about why a model behaves a certain way? Can you diagnose problems? |
| **Practical experience** | 🔴 Critical | Have you actually built, trained, deployed, and debugged ML systems? |
| **Depth on your specialty** | 🔴 Critical | Whatever you claim as your expertise — they WILL go deep. Can you hold up? |
| **Trade-off reasoning** | 🟡 High | Can you discuss model/approach trade-offs with nuance? (Not just "it depends.") |
| **Research awareness** | 🟡 High | Are you aware of recent advances? Can you evaluate new techniques critically? |
| **Communication** | 🟡 High | Can you explain complex ML concepts clearly to another ML professional? |
| **Problem-solving** | 🟡 High | Given a novel ML problem, can you reason through a solution approach? |

---

## The Three Modes of This Round

Different companies and interviewers run this round differently. Prepare for all three modes.

### Mode 1: Concept Deep-Dive (Most Common at Google, Meta)

The interviewer picks a topic and goes **increasingly deep** until you hit your knowledge boundary.

**Example progression:**
1. *"Explain how the Transformer architecture works."* (Breadth check)
2. *"Walk me through the attention mechanism mathematically."* (Depth check)
3. *"Why does multi-head attention work better than single-head?"* (Intuition check)
4. *"What's the computational complexity of self-attention? How do you reduce it?"* (Practical knowledge)
5. *"Compare FlashAttention, multi-query attention, and grouped-query attention."* (Research awareness)
6. *"If you were building a new attention mechanism for [specific use case], how would you approach it?"* (Creativity + synthesis)

**Your goal**: Go as deep as possible on each topic. The deeper you go, the higher you score.

### Mode 2: Applied Problem-Solving (Common at OpenAI, Anthropic, Amazon)

The interviewer presents a **real-world ML problem** and asks you to work through a solution.

**Example:**
> *"You're building a content moderation system. Your classifier has 95% accuracy, but the business says it's not working. Walk me through how you'd investigate and fix this."*

You need to:
1. Ask clarifying questions (what does "not working" mean? class distribution? what errors are most costly?)
2. Diagnose systematically (check for class imbalance, evaluate per-class metrics, look at failure modes)
3. Propose solutions (class weighting, threshold tuning, additional features, model architecture changes)
4. Discuss trade-offs (precision vs. recall for this specific use case)
5. Propose evaluation methodology (how would you know if your fix worked?)

### Mode 3: Project Deep-Dive (Common at Apple, Microsoft, NVIDIA)

The interviewer starts from **your resume** and picks a project to explore deeply.

**Example:**
> *"I see you built a RAG system at your current company. Walk me through the architecture. Now, let me ask some detailed questions..."*

Then they go deep:
- *"How did you decide on your chunking strategy?"*
- *"What embedding model did you use and why? Did you consider alternatives?"*
- *"How did you evaluate retrieval quality? What metrics?"*
- *"What was your biggest failure, and how did you debug it?"*
- *"If you had to rebuild it from scratch, what would you do differently?"*

**Your goal**: Demonstrate that you made thoughtful decisions, not just "it worked so I shipped it."

---

## Core Topics and How to Prepare

### Topic 1: ML Fundamentals (Required for All Levels)

These are the **foundational concepts** that every ML interviewer expects you to know cold.

#### Supervised Learning

| Concept | What to Know | Common Questions |
|---|---|---|
| **Bias-Variance Trade-off** | Underfitting = high bias. Overfitting = high variance. How to balance (regularization, data, model complexity). | "Your model performs well on training but poorly on test. Diagnose." |
| **Regularization** | L1 (sparsity, feature selection) vs. L2 (weight decay, smooth). Dropout. Early stopping. | "When would you use L1 vs. L2? What does dropout do mechanistically?" |
| **Cross-Validation** | K-fold, stratified K-fold, time-series split. Why holdout isn't enough. | "How would you evaluate a model on imbalanced data?" |
| **Loss Functions** | Cross-entropy (classification), MSE (regression), focal loss (imbalanced), contrastive loss (embeddings). | "Why cross-entropy instead of MSE for classification?" |
| **Optimization** | SGD, Adam, learning rate schedules (cosine, warmup). Batch size effects. | "What does Adam do differently from SGD? When would you prefer SGD?" |
| **Evaluation Metrics** | Precision, recall, F1, AUC-ROC, AUC-PR, NDCG, MAP, calibration. | "Your model has AUC 0.95 but F1 0.3. How is that possible?" |

**How to explain metrics with depth (example for Precision vs. Recall):**

> *"Precision is the fraction of positive predictions that are actually positive — it answers 'when the model says yes, how often is it right?' Recall is the fraction of actual positives that the model caught — it answers 'of all the true positives, how many did we find?'"*
>
> *"The choice depends on the cost of errors. For spam detection, high precision matters (users hate false positives in their inbox). For cancer screening, high recall matters (missing a positive case is far more costly than a false alarm)."*
>
> *"F1 is the harmonic mean and balances them, but it treats them equally. In practice, you'd often set a threshold to optimize for the business-relevant metric, not F1."*

#### Unsupervised Learning

| Concept | What to Know |
|---|---|
| **Clustering** | K-Means, DBSCAN, hierarchical. How to choose K. Silhouette score. |
| **Dimensionality Reduction** | PCA (linear), t-SNE (visualization), UMAP (preserves global structure) |
| **Anomaly Detection** | Isolation Forest, autoencoders, statistical methods. When to use which. |

### Topic 2: Deep Learning & Neural Networks

| Concept | What to Know | Depth Expected |
|---|---|---|
| **Feedforward Networks** | Architecture, activation functions (ReLU, GELU, SiLU), universal approximation. | Can explain why non-linearity is needed, vanishing/exploding gradients. |
| **Convolutional Networks** | Convolution operation, pooling, stride, receptive field. | Can explain how CNNs learn hierarchical features. Used less for NLP now but foundational. |
| **Recurrent Networks** | RNN, LSTM, GRU. Vanishing gradient problem. | Can explain why LSTM gates solve the vanishing gradient problem. Historical knowledge — Transformers replaced these. |
| **Transformers** | **THIS IS THE MOST IMPORTANT TOPIC.** Self-attention, multi-head attention, positional encoding, FFN layers, layer norm. | Must be able to explain from first principles, including the math. See deep-dive below. |
| **Training at Scale** | Distributed training (data parallelism, model parallelism, pipeline parallelism), mixed precision, gradient accumulation. | Can discuss how to train a large model across multiple GPUs. |
| **Normalization** | Batch norm, layer norm, RMS norm. When to use which. | Layer norm is standard in Transformers. Know why. |

#### Transformer Deep-Dive (Must-Know)

You **will** be asked about Transformers. Be able to explain at three levels:

**Level 1 — High-level (30 seconds):**
> *"The Transformer processes input tokens in parallel using self-attention, which lets each token attend to all other tokens. This captures long-range dependencies without the sequential bottleneck of RNNs. It consists of encoder and/or decoder blocks, each with multi-head self-attention and a feedforward network."*

**Level 2 — Mechanism (2 minutes):**
> *"Each attention head computes three linear projections from the input: Query (Q), Key (K), and Value (V). The attention score between tokens i and j is the dot product of Q_i and K_j, scaled by √d_k to prevent softmax saturation. We apply softmax to get attention weights, then compute a weighted sum of V vectors."*
>
> *"Multi-head attention runs H parallel attention heads with different learned projections, concatenates their outputs, and projects back. This lets the model attend to different types of relationships simultaneously (e.g., one head might focus on syntactic relationships, another on semantic ones)."*
>
> *"Positional encoding is needed because attention is permutation-invariant — without it, the model has no sense of token order. The original paper used sinusoidal encodings; modern models use learned positional embeddings or rotary position embeddings (RoPE)."*

**Level 3 — Details and trade-offs (2+ minutes):**
> *"The computational complexity of self-attention is O(n²·d) where n is sequence length and d is dimension, because every token attends to every other token. This quadratic scaling is the biggest limitation for long sequences."*
>
> *"Solutions to the quadratic problem: FlashAttention (IO-aware exact attention that tiles computations to fit in GPU SRAM — no approximation, just hardware-efficient), multi-query attention (share K,V across heads to reduce KV cache size), grouped-query attention (GQA — intermediate between MHA and MQA), sparse attention (only attend to local windows + strided patterns), linear attention (approximate softmax attention with kernel methods)."*
>
> *"Modern LLMs use decoder-only architecture (GPT-style) with causal masking, RoPE for position, GQA for efficient inference, RMSNorm instead of LayerNorm, and SwiGLU activation in the FFN. Flash Attention is now standard for training."*

### Topic 3: LLMs and Generative AI

| Concept | What to Know |
|---|---|
| **Pre-training** | Causal language modeling (predict next token), massive dataset (Common Crawl, books, code), training compute (GPUs, TPUs), scaling laws (Chinchilla) |
| **Tokenization** | BPE, SentencePiece, WordPiece. Why tokenization matters (rare words, multilingual, code). Vocabulary size trade-offs. |
| **Fine-tuning** | Full fine-tuning (all parameters), LoRA/QLoRA (parameter-efficient), instruction tuning, domain adaptation. When to use each. |
| **RLHF / Alignment** | Reward model training, PPO for policy optimization, DPO (direct preference optimization) as a simpler alternative, Constitutional AI. |
| **Inference Optimization** | KV cache (avoids recomputing attention for previous tokens), speculative decoding, quantization (INT8, INT4, GPTQ, AWQ), batching strategies (continuous batching). |
| **Prompting** | Zero-shot, few-shot, chain-of-thought, self-consistency, retrieval-augmented. When to use prompting vs. fine-tuning. |
| **Hallucination** | Why it happens (distributional vs. factual knowledge), mitigation (RAG, grounding, fact-checking, constrained decoding). |
| **Evaluation** | Human eval, LLM-as-judge, BLEU/ROUGE (limited), task-specific benchmarks (MMLU, HumanEval, MT-Bench), red-teaming. |
| **Scaling Laws** | Chinchilla scaling laws (compute-optimal training), emergent abilities, relationship between model size/data/compute. |

### Topic 4: RAG Systems (Essential for AI Engineers)

| Component | What to Know | Common Questions |
|---|---|---|
| **Chunking** | Fixed-size, semantic, recursive, parent-child. Chunk size vs. retrieval quality trade-off. Overlap. | "How do you choose chunk size? What happens if it's too large or too small?" |
| **Embedding** | Models (OpenAI, Cohere, BGE, E5), dimensions, fine-tuning embeddings for domain. | "When would you fine-tune the embedding model vs. using off-the-shelf?" |
| **Indexing** | HNSW, IVF, Product Quantization. Build vs. search trade-offs. | "Explain HNSW. What are the parameters and their trade-offs?" |
| **Retrieval** | Dense retrieval, sparse (BM25), hybrid (reciprocal rank fusion). | "Why would you combine dense and sparse retrieval?" |
| **Reranking** | Cross-encoder reranking, ColBERT, LLM-based reranking. | "Why rerank instead of just using a better retrieval model?" |
| **Generation** | Context formatting, instruction design, handling conflicting sources. | "What do you do when retrieved documents contradict each other?" |
| **Evaluation** | Retrieval metrics (precision@k, recall@k, MRR), generation metrics (faithfulness, relevance, correctness). | "How would you evaluate a RAG system end-to-end?" |

### Topic 5: Embeddings and Similarity Search (Cross-Cutting)

| Concept | What to Know |
|---|---|
| **Vector spaces** | Dense embeddings represent semantic meaning. Similar items are close in vector space. |
| **Distance metrics** | Cosine similarity (direction), Euclidean distance (magnitude), dot product (both). When to use each. |
| **ANN algorithms** | HNSW (graph-based, best general-purpose), IVF (partition-based, good for very large datasets), PQ (compression, reduces memory). |
| **Vector databases** | Pinecone (managed), Weaviate (open-source), Qdrant (Rust-based), pgvector (PostgreSQL extension), Milvus (distributed). Trade-offs. |
| **Dimensionality** | Higher dimensions = more information but slower search and more memory. 256 – 1536 is typical. Matryoshka embeddings for flexible dimensionality. |
| **The curse of dimensionality** | In very high dimensions, distances converge. Why this matters for cosine similarity effectiveness. |

### Topic 6: ML Systems and Infrastructure (Essential for AI Systems Engineers)

| Topic | What to Know |
|---|---|
| **Distributed training** | Data parallelism (replicate model, split data), model parallelism (split model across GPUs), pipeline parallelism (split layers), FSDP (fully sharded), ZeRO optimization. |
| **Model serving** | Triton Inference Server (multi-framework, dynamic batching), vLLM (LLM-specific, PagedAttention, continuous batching), TGI (HuggingFace), TensorRT-LLM (NVIDIA optimized). |
| **GPU fundamentals** | A100 specs (80GB HBM2e, 312 TFLOPS FP16), H100 specs (80GB HBM3, 989 TFLOPS FP16), NVLink (GPU-GPU communication), InfiniBand (node-to-node). |
| **Quantization** | INT8, INT4 (GPTQ, AWQ, bitsandbytes). Trade-off: smaller model, faster inference, slight accuracy loss. |
| **Model optimization** | Operator fusion, kernel optimization, graph optimization (TensorRT, ONNX Runtime), speculative decoding. |
| **Feature stores** | Feast (open-source), Tecton (managed). Online store (Redis-backed, low latency) vs. offline store (data warehouse, batch). Point-in-time correctness. |

### Topic 7: Agentic AI (Essential for AI Agentic Engineers)

| Topic | What to Know |
|---|---|
| **Agent architectures** | ReAct (Reason + Act loop), Plan-and-Execute (plan first, then execute steps), Tree of Thought (explore multiple reasoning paths), Reflexion (self-critique and retry). |
| **Tool use** | Function calling schemas, tool selection, schema design, authentication, error handling, tool output parsing. |
| **Memory** | Short-term (conversation context), long-term (persistent storage), episodic (past task memory), working memory (current task state). |
| **Multi-agent systems** | Orchestrator-worker pattern, peer-to-peer, hierarchical delegation. Communication protocols. |
| **Evaluation** | Task completion rate, tool call accuracy, cost-per-task, safety evaluation, user satisfaction. |
| **Safety** | Jailbreak prevention, output validation, constrained actions, human-in-the-loop gates, permission systems. |
| **Orchestration** | LangGraph, CrewAI, AutoGen. State management, error recovery, retry logic, timeout handling. |

---

## Common Questions and How to Answer Them

### Theoretical Questions

**"Explain how the Transformer architecture works."**
→ Use the three-level explanation above. Start at Level 1, then go deeper as they probe.

**"What is the attention mechanism? Walk me through the math."**

> *"Attention lets each position in a sequence focus on other relevant positions. Given input X, we compute three matrices: Q = XW_Q, K = XW_K, V = XW_V."*
>
> *"The attention score is: Attention(Q, K, V) = softmax(QK^T / √d_k) · V"*
>
> *"We scale by √d_k because without it, the dot products grow large for high d_k, pushing the softmax into saturated regions where gradients are near zero."*
>
> *"Multi-head: we run this H times with different W_Q, W_K, W_V, concatenate, and project. This lets different heads learn different attention patterns."*

**"What's the difference between pre-training, fine-tuning, and RLHF?"**

> *"Pre-training is unsupervised learning on massive text data — the model learns to predict the next token. This gives it broad language understanding and world knowledge."*
>
> *"Fine-tuning (instruction tuning / SFT) is supervised training on curated instruction-response pairs. This teaches the model to follow instructions and be helpful."*
>
> *"RLHF further aligns the model with human preferences. You train a reward model on human preference data (ranking outputs), then use it as a signal to optimize the policy (the LLM) via PPO. DPO is a simpler alternative that skips the reward model."*
>
> *"Think of it as: pre-training gives the model knowledge, SFT teaches it to be helpful, and RLHF teaches it to be safe and preferred."*

**"When would you fine-tune vs. use prompt engineering?"**

> *"Prompt engineering first — it's cheaper, faster, and reversible. You can often get 80% of the way with good prompts, few-shot examples, and structured output."*
>
> *"Fine-tune when: (1) prompt engineering can't bridge the gap, (2) you have a consistent format/style requirement, (3) you need to reduce inference cost (shorter prompts), (4) you need domain-specific knowledge not in the base model, or (5) latency requirements mean you need a smaller, specialized model."*
>
> *"The trade-off: fine-tuning requires data, compute, and ongoing maintenance (data drift, model updates). Prompting is fragile but flexible."*

### Applied / Diagnostic Questions

**"Your LLM is hallucinating on 10% of queries. How do you diagnose and fix this?"**

> *"First, I'd categorize the hallucinations:"*
> - *"Factual errors (model generates plausible but wrong facts)"*
> - *"Faithfulness errors (model contradicts the context/documents provided)"*
> - *"Fabrication (model invents information not in any source)"*
>
> *"Diagnosis:"*
> 1. *"Sample 50 – 100 hallucinated outputs and manually categorize."*
> 2. *"Check if hallucination correlates with specific query types, document types, or topics."*
> 3. *"Check retrieval quality (if RAG): are the right documents being retrieved?"*
> 4. *"Check context window usage: is the model attending to the provided context?"*
>
> *"Fixes, in order of effort:"*
> 1. *"Prompt engineering: add 'only answer based on the provided context' instructions."*
> 2. *"Improve retrieval: better chunking, reranking, hybrid search."*
> 3. *"Add post-processing: citation extraction, fact-checking against source documents."*
> 4. *"Fine-tune: if hallucination is systematic, fine-tune on examples of faithful responses."*
> 5. *"Constrained decoding: force outputs to contain only information from retrieved documents."*
>
> *"Evaluation: set up automated hallucination detection (LLM-as-judge for faithfulness) and track the rate over time."*

**"You need to reduce inference latency from 2 seconds to 200ms. What are your options?"**

> *"I'd approach this systematically from easiest to hardest:"*
>
> 1. **Quantization** (effort: low) — *"Quantize the model from FP16 to INT8 or INT4 using GPTQ or AWQ. This typically gives 2-4x speedup with minimal quality loss."*
> 2. **Batching** (effort: low) — *"Implement continuous batching with vLLM or TGI. Better GPU utilization can significantly reduce per-request latency under load."*
> 3. **KV cache optimization** (effort: low-medium) — *"Enable PagedAttention (vLLM does this automatically). Reduces memory waste and enables serving more concurrent requests."*
> 4. **Model distillation** (effort: medium) — *"Train a smaller model to mimic the large model's outputs on your specific task. A 7B model may perform as well as a 70B model for narrow tasks."*
> 5. **Speculative decoding** (effort: medium) — *"Use a small draft model to generate candidate tokens, verified in parallel by the large model. Can give 2-3x speedup."*
> 6. **Hardware** (effort: low, cost: high) — *"Move to faster GPUs (H100 vs. A100) or add tensor parallelism across GPUs."*
> 7. **Architecture change** (effort: high) — *"If the task allows it, switch from an autoregressive LLM to a smaller, task-specific model (BERT-based classifier, smaller encoder, etc.)."*
>
> *"The right choice depends on the quality-latency trade-off tolerance and budget. I'd start with quantization + batching (often enough), then consider distillation if needed."*

**"Design an evaluation framework for a new RAG system."**

> *"I'd evaluate at three levels: retrieval, generation, and end-to-end."*
>
> **Retrieval Evaluation:**
> - *"Metrics: Precision@K, Recall@K, MRR, NDCG. These tell us if we're retrieving the right documents."*
> - *"Method: Create a golden dataset of queries + relevant documents. Run queries through the retrieval pipeline and compute metrics."*
>
> **Generation Evaluation:**
> - *"Faithfulness: Does the answer match the retrieved context? (LLM-as-judge with a prompt like 'Is this answer supported by the context?')"*
> - *"Relevance: Does the answer actually address the question? (LLM-as-judge or human eval.)"*
> - *"Correctness: Is the answer factually correct? (Compare against gold-standard answers for the test set.)"*
> - *"Completeness: Does the answer cover all aspects of the question?"*
>
> **End-to-End:**
> - *"Task completion rate: For how many queries does the system produce a satisfactory answer?"*
> - *"User satisfaction: Thumbs up/down feedback, NPS scoring."*
> - *"Cost: Average tokens used per query, average latency per query."*
>
> *"I'd build an automated eval pipeline (using RAGAS or a custom framework) that runs nightly against the golden dataset. Manual eval (human annotators) monthly for a subset. A/B test in production for any major change."*

### Open-Ended / Opinion Questions

**"What are the biggest challenges with deploying LLMs in production?"**

> *"I see five main challenges:"*
> 1. **Latency and cost**: *"LLMs are expensive to run. Serving costs scale with token usage. Need optimization (quantization, caching, model selection) to meet latency SLAs within budget."*
> 2. **Hallucination and reliability**: *"LLMs generate plausible-sounding wrong answers. In production, this erodes trust. RAG, guardrails, and constrained outputs help but don't fully solve it."*
> 3. **Evaluation**: *"Hard to measure quality automatically. Human eval doesn't scale. LLM-as-judge has its own biases. Building robust eval is a significant investment."*
> 4. **Prompt fragility**: *"Small changes in prompts can cause large changes in output. Prompt-based systems need version control, testing, and monitoring like code."*
> 5. **Safety and compliance**: *"Preventing misuse, ensuring privacy (PII in outputs), meeting regulatory requirements (especially in healthcare, finance). This requires guardrails, filtering, and audit logging."*

**"What's the most interesting AI paper or technique you've seen recently?"**

> **Prepare 2 – 3 genuine answers.** Pick papers/techniques you've actually read or used. Example:
>
> *"I've been very interested in [specific technique]. It addresses [problem] by [approach]. What I find compelling is [specific insight]. I've experimented with it for [your use case] and found that [practical observation]. One limitation I see is [critical thinking]."*

---

## How to Handle "I Don't Know"

You WILL hit the boundary of your knowledge. That's expected and designed. How you handle it determines whether you get "reached boundary gracefully" (positive) vs. "couldn't handle depth" (negative).

**Good responses:**
> *"I'm less familiar with the specifics of [topic], but based on my understanding of [related topic], I'd expect it to work by [reasoning from first principles]."*

> *"I haven't implemented [technique] directly, but I understand the concept at a high level: [explanation]. For the implementation details, I'd reference [specific resource]."*

> *"That's at the edge of my current knowledge. What I do know is [what you know]. To go deeper, I'd need to review [what you'd look up]."*

**Bad responses:**
- ❌ *"I don't know."* (Full stop — no attempt to reason.)
- ❌ *"I haven't studied that."* (Sounds like you didn't prepare.)
- ❌ Making something up confidently. (Experts can tell. Instant credibility loss.)

---

## Role-Specific Deep-Dive Preparation

### AI Engineer: Focus Areas

| Priority | Topic | Depth Required |
|---|---|---|
| 🔴 Must | LLMs (architecture, inference, prompting, fine-tuning) | Can explain internals, make model selection decisions, optimize prompts |
| 🔴 Must | RAG (end-to-end: chunking → retrieval → generation → eval) | Can design and debug a production RAG system |
| 🔴 Must | Evaluation (metrics, human eval, LLM-as-judge) | Can design an eval framework for any generative task |
| 🟡 High | Embeddings and vector search | Can explain ANN algorithms, choose the right embedding model |
| 🟡 High | ML fundamentals (classification, regression, metrics) | Solid foundation, can diagnose model issues |
| 🟢 Medium | Training and fine-tuning (SFT, LoRA, RLHF) | Understand the concepts and when to apply them |

### AI Systems Engineer: Focus Areas

| Priority | Topic | Depth Required |
|---|---|---|
| 🔴 Must | Model serving (Triton, vLLM, TGI, batching, GPU management) | Can architect and optimize a serving pipeline |
| 🔴 Must | Distributed training (DDP, FSDP, model/pipeline parallelism) | Can explain trade-offs and configure distributed training |
| 🔴 Must | GPU fundamentals (memory hierarchy, compute, NVLink, InfiniBand) | Can reason about GPU utilization and bottlenecks |
| 🟡 High | Quantization and model optimization | Can explain techniques and their quality-speed trade-offs |
| 🟡 High | ML platform components (feature store, experiment tracking, model registry) | Can design these components as systems |
| 🟢 Medium | ML fundamentals | Enough to understand what the model does, not necessarily design models |

### AI Agentic Engineer: Focus Areas

| Priority | Topic | Depth Required |
|---|---|---|
| 🔴 Must | Agent architectures (ReAct, Plan-and-Execute, multi-agent) | Can design and compare architectures for specific use cases |
| 🔴 Must | Tool use and function calling (schema design, error handling, authentication) | Can build robust tool-calling systems |
| 🔴 Must | LLM internals (enough to reason about agent behavior) | Can explain why agents fail and how to fix them |
| 🟡 High | Memory systems (short-term, long-term, episodic, knowledge graphs) | Can design memory architectures for complex agents |
| 🟡 High | Safety and evaluation for agents | Can design eval frameworks and safety guardrails |
| 🟢 Medium | RAG (agents often use retrieval) | Can integrate retrieval into agent workflows |

---

## Company-Specific ML/AI Deep-Dive Nuances

| Company | What to Expect |
|---|---|
| **Google** | Deep on fundamentals. Will test Transformer knowledge exhaustively. May discuss TPU-specific training. Research-oriented — be aware of Google's contributions (BERT, T5, Gemini, PaLM). |
| **Meta** | Practical ML focus. May ask about recommendation systems, ranking, content understanding. Know about LLaMA and Meta's open-source ML ecosystem. |
| **Amazon** | Applied ML. Focus on production systems, scalability, customer-facing ML. Less research-y, more "how would you ship this?" |
| **Apple** | Privacy-preserving ML (on-device inference, federated learning, differential privacy). May discuss CoreML, on-device optimization. |
| **Microsoft** | Enterprise AI, Azure ML, responsible AI. May discuss multi-modality, Copilot-style integrations. |
| **OpenAI** | Deep on LLMs, alignment, safety. Research taste matters. Be ready to discuss recent papers critically. |
| **Anthropic** | Safety and alignment focus. RLHF, Constitutional AI, red-teaming. Want people who think deeply about responsible AI. |
| **NVIDIA** | GPU optimization, CUDA, inference performance. TensorRT, Triton. The most systems/hardware-focused interview. |

---

## Scoring: What Separates Good from Outstanding

| Signal | Good (Hire) | Outstanding (Strong Hire) |
|---|---|---|
| **Fundamentals** | Explains concepts correctly | Explains with intuition, connects to practical implications, knows the edge cases |
| **Depth** | Goes 2 – 3 levels deep | Goes to the frontier of current knowledge, discusses open problems |
| **Trade-offs** | Mentions trade-offs when asked | Proactively frames every decision as a trade-off with explicit reasoning |
| **Practical experience** | Has built ML systems | Has built, failed, debugged, and rebuilt. Shares war stories with specific lessons. |
| **Research awareness** | Knows major recent advances | Can critically evaluate new techniques, knows strengths AND limitations |
| **Problem-solving** | Follows a reasonable diagnostic process | Systematic, covers multiple hypotheses, prioritizes by likelihood, proposes measurement |
| **Communication** | Answers questions clearly | Teaches the interviewer something new. Frames complex ideas simply. Uses diagrams. |

---

## Day-of Quick Reference

### Before You Walk In
- [ ] Review your projects — expect deep questions on anything in your resume.
- [ ] Refresh Transformer architecture (Level 1, 2, and 3 explanations).
- [ ] Review evaluation metrics and when to use each.
- [ ] Prepare 2 – 3 "debugging ML problems" stories from past experience.
- [ ] Have a virtual whiteboard strategy — practice drawing model architectures.

### During the Round
- [ ] **Listen carefully** to the question. Don't assume what they're asking.
- [ ] **Start broad, then go deep.** Give the 30-second version, then ask: "Would you like me to go deeper on any part?"
- [ ] **Use diagrams.** Draw model architectures, training pipelines, data flow.
- [ ] **Connect theory to practice.** After explaining a concept, tie it to something you've built.
- [ ] **Be honest about boundaries.** If you don't know something, reason from first principles.
- [ ] **Ask clarifying questions** on applied problems. Don't assume the problem setup.
