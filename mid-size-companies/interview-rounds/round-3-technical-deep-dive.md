# Round 3: Technical Deep-Dive — How to Pass It Excellently

> **Format**: Video call with screen share (1 – 2 sessions) | **Duration**: 45 – 90 min each | **Interviewer**: Senior engineers, tech leads, or Staff+ engineers on the team

---

## What This Round Actually Is

This is the **make-or-break round**. The technical deep-dive is where the team determines if you can actually do the work. Unlike the hiring manager call (which tests depth through conversation), this round tests depth through **doing** — live coding, system design, or domain-specific problem-solving.

Mid-size companies typically run **1 – 2 sessions** that can include any combination of:

| Session Type | What It Looks Like | Likelihood |
|---|---|---|
| **Live coding** | Build something relevant to the product — API endpoint, RAG pipeline, data processing script, agent workflow | Very common |
| **System design** | Design an AI-powered system end-to-end on a whiteboard or shared doc | Very common |
| **Domain deep-dive** | In-depth technical discussion about a specific AI topic (retrieval, fine-tuning, agents, evaluation) | Common |
| **Code review / debugging** | Review existing code, identify issues, and suggest improvements | Less common but growing |
| **Pair programming** | Build something together with the interviewer | Less common |

> **Key difference from startups**: At mid-size companies, the problems are more structured, the expectations for code quality are higher, and you'll often face a **system design round** (rare at startups).

---

## Part 1: Live Coding Session

### What They're Evaluating

| Criteria | Weight | What They Want to See |
|---|---|---|
| **Problem-solving approach** | 🔴 Critical | Can you decompose a problem, clarify requirements, and work systematically? |
| **Technical competence** | 🔴 Critical | Can you write working code that solves the problem? |
| **Communication** | 🔴 Critical | Can you explain your thinking while coding? |
| **Code quality** | 🟡 High | Is your code clean, readable, well-structured, and idiomatic? |
| **Trade-off awareness** | 🟡 High | Do you make and articulate pragmatic decisions? |
| **Testing mindset** | 🟡 Medium | Do you think about edge cases and validation? |
| **Speed** | 🟢 Lower than you think | Hiring managers consistently say they prefer slow-and-clear over fast-and-messy |

### Common Problem Types for AI Roles

Based on the role type, expect problems in these categories:

#### AI Engineer
- **Build a RAG pipeline**: Given a set of documents and a query, implement retrieval-augmented generation.
- **Prompt engineering challenge**: Design prompts that handle edge cases for a specific use case (extraction, classification, summarization).
- **API integration**: Build a FastAPI/Flask endpoint that takes user input, calls an LLM, and returns structured output.
- **Data processing**: Parse, clean, and transform data for use in an AI pipeline.
- **Evaluation**: Write code to evaluate model outputs against a golden dataset.

#### AI Systems Engineer
- **Build a model serving endpoint**: Containerize a model and serve it via an API with proper error handling.
- **Pipeline implementation**: Build a data processing or training pipeline with proper logging and error handling.
- **Infrastructure coding**: Write a Dockerfile, docker-compose, or Kubernetes manifest for an AI service.
- **Monitoring script**: Implement monitoring/alerting for an AI system (latency, quality drift, errors).
- **Optimization**: Profile and optimize an existing pipeline for latency or throughput.

#### AI Agentic Engineer
- **Build an agent**: Implement a multi-step agent with tool calling for a specific task.
- **Tool design**: Design and implement tools (API wrappers) that an agent can call.
- **Agent orchestration**: Build a multi-agent system or supervisor pattern.
- **Error handling**: Implement retry logic, fallbacks, and graceful degradation for agent failures.
- **State management**: Implement conversation memory or persistent state for an agent.

### How to Excel at Live Coding

#### Before the Session

1. **Set up your environment in advance:**
   - Python environment with common libraries pre-installed:
     ```
     openai, anthropic, langchain, langchain-community, langgraph,
     fastapi, uvicorn, pydantic, chromadb, pinecone-client,
     pandas, numpy, pytest, python-dotenv, httpx, tiktoken
     ```
   - API keys in `.env` file (OpenAI, Anthropic — whatever you use).
   - VS Code or your preferred editor configured and comfortable.
   - Terminal tested. Screen sharing tested.
   - **Two monitors** if possible — one for coding, one for docs/notes.

2. **Practice the "narrated build" pattern:**
   Record yourself solving a problem while explaining your thought process. Watch it back. The first time you try this, you'll realize how hard it is. By the 3rd or 4th practice, you'll be fluent.

3. **Prepare reusable code patterns** you can type quickly:
   - FastAPI app setup
   - OpenAI/Anthropic API call with error handling
   - Basic RAG pipeline (embeddings → vector store → retrieval → generation)
   - Agent with tool calling
   - Pytest test structure
   - Pydantic models for structured output

   > Don't memorize — just practice typing them enough that you don't need to look up syntax.

4. **Re-read your hiring manager notes.** The HM likely hinted at what the technical round will cover.

#### During the Session: The First 5 Minutes (Critical)

These 5 minutes set the tone for the entire round.

**Step 1: Listen (60 seconds)**
- Let the interviewer fully explain the problem.
- Take notes on key requirements.
- DON'T start coding in your head yet.

**Step 2: Repeat and Clarify (2 – 3 minutes)**

Ask 3 – 5 clarifying questions. This is **expected and valued**:

> "Before I start, I want to make sure I understand the problem correctly."

Great clarifying questions for AI problems:

| Question | Why It's Smart |
|---|---|
| "What's the expected input format?" | Shows you think about contracts/interfaces |
| "Should I optimize for latency, quality, or cost?" | Shows production awareness |
| "Is this a single-user or multi-user system?" | Shows scaling awareness |
| "Should I handle the happy path first, or do you want me to account for edge cases from the start?" | Manages scope and shows planning |
| "Can I use [specific library/API]?" | Avoids wasting time on something they'd prefer you not use |
| "What does success look like for this task?" | Aligns expectations explicitly |
| "Should I write tests, or focus on the implementation?" | Time management |

**Step 3: State Your Plan (1 – 2 minutes)**

Before writing a single line of code:

> "Here's my plan. I'll start by [high-level approach]. The components I need are: [list them]. I'll build [component A] first because it's the foundation, then [component B], and if time allows, [component C, D]. I'm going to use [library/framework] because [reason]. Does that sound reasonable?"

This does three things:
1. Shows you can plan before diving in.
2. Gives the interviewer a chance to redirect you if needed.
3. Creates a roadmap that makes your coding session easy to follow.

#### During the Session: The Building Phase

**Follow this rhythm:**

```
Plan a component → Narrate what you're about to do → Code it → Test it → Move on
```

**Narration examples (say these OUT LOUD while coding):**

| Moment | What to Say |
|---|---|
| Starting a new function | "I'm going to create a function that handles document chunking. It'll take raw text and return a list of chunks with metadata." |
| Making a design choice | "I'm using recursive character splitting here because the documents have sections of varying length. In production, I'd consider semantic chunking, but for now this is good enough." |
| Writing an API call | "Setting up the OpenAI call with gpt-4o. I'm using a low temperature because we want consistent, factual responses for this use case." |
| Handling an edge case | "I should handle the case where the API returns an empty response — let me add a check here." |
| Skipping something for time | "In production, I'd add retry logic with exponential backoff here. I'll skip it for now but I want to note it." |

**Code quality patterns that impress:**

```python
# ✅ Good: Type hints, clear naming, docstring
async def retrieve_relevant_chunks(
    query: str,
    collection: chromadb.Collection,
    top_k: int = 5,
) -> list[dict]:
    """Retrieve the most relevant document chunks for a given query."""
    results = collection.query(
        query_texts=[query],
        n_results=top_k,
    )
    return [
        {"text": doc, "metadata": meta, "score": score}
        for doc, meta, score in zip(
            results["documents"][0],
            results["metadatas"][0],
            results["distances"][0],
        )
    ]

# ❌ Bad: No types, unclear naming, no structure
def get_stuff(q, c, n=5):
    r = c.query(query_texts=[q], n_results=n)
    return r
```

**Run your code incrementally:**
- After each logical unit (function, endpoint, pipeline step), **run it**.
- Don't write 100 lines and then discover a bug at line 12.
- Testing as you go shows professionalism and reduces panic.

#### When You Get Stuck

Everyone gets stuck. How you handle it is part of the evaluation.

**Tier 1: Self-rescue (try this first)**
1. **Verbalize the problem**: "I'm stuck because I expected [X] but I'm getting [Y]."
2. **Break it down**: "Let me isolate the issue. I'll print the inputs and outputs at each step."
3. **Try an alternative**: "My first approach isn't working. Let me try [alternative]."

**Tier 2: Collaborative recovery (if Tier 1 fails after 3 – 5 minutes)**
4. **Ask for a nudge**: "I'm stuck on this part — could you point me in the right direction?"
5. **Propose options**: "I see two possible approaches: [A] and [B]. Which one would you prefer I explore?"

> Asking for help is **not a failure**. It's a signal of collaboration and maturity. What's a failure is sitting in silence for 10 minutes making no progress.

#### The Last 5 – 10 Minutes

This is where good candidates become great:

1. **Run a final demo**: Show the working solution end-to-end.
2. **Summarize what you built**: "I've implemented a [description] with [key components]. It takes [input] and produces [output]."
3. **Acknowledge what's missing**: "With more time, I'd add: error handling for [X], caching at [Y], and tests for [Z]."
4. **Connect to their product**: "This is essentially the [pipeline/feature] you'd need for [their use case], though in production I'd also consider [production concern]."
5. **Mention scale considerations**: "At scale, I'd add [caching / async processing / queue / monitoring]."

---

## Part 2: System Design Session

### What They're Evaluating

| Criteria | Weight | What They Want to See |
|---|---|---|
| **Structured approach** | 🔴 Critical | Can you decompose a complex problem into manageable components? |
| **AI/ML expertise** | 🔴 Critical | Do you make informed choices about models, pipelines, retrieval, evaluation? |
| **Production thinking** | 🔴 Critical | Do you think about latency, cost, monitoring, failure modes, scaling? |
| **Trade-off articulation** | 🟡 High | Can you explain *why* you chose one approach over alternatives? |
| **Communication** | 🟡 High | Can you explain a complex system clearly, using diagrams? |
| **Breadth** | 🟢 Medium | Do you understand how the AI layer connects to the rest of the system? |

### Common System Design Prompts for AI Roles

- "Design a document Q&A system for our product."
- "Design an AI-powered search and recommendation system."
- "Design a pipeline that processes 50,000 documents daily and extracts structured data."
- "Design a conversational agent that can access internal tools and databases."
- "Design an AI content moderation system for our platform."
- "Design a real-time translation feature powered by LLMs."
- "Design a system that automatically categorizes and routes customer support tickets."
- "Design an evaluation and monitoring platform for our AI features."

### The 6-Step Framework

#### Step 1: Clarify Requirements (3 – 5 min)

Ask questions to define the scope:

**Functional requirements:**
- "What are the specific user actions and expected outputs?"
- "What data sources are available?"
- "What quality bar does the output need to hit?"

**Non-functional requirements:**
- "What's the expected query volume? (10/day? 10,000/day? 1M/day?)"
- "What's the latency requirement? (Real-time? Under 5 seconds? Batch is fine?)"
- "What's the budget context? (Unlimited API calls? Cost-sensitive?)"
- "What's the accuracy threshold? (Best-effort? Must be > 95%?)"
- "Any compliance or security constraints? (PII, GDPR, SOC 2?)"

**Scope:**
- "Should I design the full system or focus on the AI layer?"
- "Are we designing for day-one or for the system at scale in a year?"

#### Step 2: Define the Problem (2 min)

Restate the problem with your understanding:

> "So we're designing a document Q&A system that takes natural language questions from legal professionals, retrieves relevant information from a corpus of ~100K legal documents, and generates accurate, cited answers. The system needs to respond in under 5 seconds, handle ~1,000 queries per day, and the answers need to be trustworthy enough that professionals don't need to verify every response. Is that right?"

Get a "yes" before proceeding.

#### Step 3: High-Level Architecture (10 – 15 min)

Draw the major components and data flow. **Always start with the user.**

**Template for AI systems:**

```
[User] → [API Gateway / Frontend]
                ↓
         [Application Layer]
                ↓
    ┌───────────┼───────────┐
    ↓           ↓           ↓
[Data Layer] [AI Layer]  [Cache Layer]
    ↓           ↓           ↓
[Storage]  [Models/APIs] [Redis/Memcached]
                ↓
         [Monitoring & Eval]
```

Walk through each component:

- **Ingestion pipeline**: How does data get into the system?
- **Processing / AI layer**: Where do models, retrieval, and generation happen?
- **Serving layer**: How does the output get to the user?
- **Storage**: What databases and stores are needed?
- **Monitoring**: How do you know the system is working?

#### Step 4: Deep-Dive on the AI Layer (15 – 20 min)

This is **your time to shine**. Go deep on the AI-specific components:

**For a RAG system, cover:**
| Component | What to Discuss |
|---|---|
| **Document processing** | Ingestion format (PDF, HTML, etc.), parsing strategy, metadata extraction |
| **Chunking** | Strategy (recursive, semantic, structural), chunk size trade-offs, overlap |
| **Embedding** | Model choice (OpenAI, Cohere, open-source), dimensionality, fine-tuning considerations |
| **Vector store** | Choice (Pinecone, Weaviate, Qdrant, pgvector), indexing strategy, filtering |
| **Retrieval** | Dense vs. sparse vs. hybrid search, query transformation, reranking |
| **Generation** | Model choice, prompt design, context window management, citation extraction |
| **Evaluation** | Retrieval metrics (precision@k, recall@k), answer quality (LLM-as-judge, human eval) |

**For an agent system, cover:**
| Component | What to Discuss |
|---|---|
| **Agent architecture** | Pattern choice (ReAct, Plan-and-Execute, etc.) and why |
| **Tool ecosystem** | What tools the agent needs, schema design, authentication |
| **Orchestration** | Single agent vs. multi-agent, supervisor pattern, state machine |
| **Memory** | Short-term (conversation buffer) and long-term (vector store) |
| **Error handling** | Retries, fallbacks, circuit breakers, human escalation |
| **Guardrails** | Output validation, safety filters, budget limits |

**Make trade-offs explicit at every step:**

> "For the embedding model, I'd start with OpenAI's text-embedding-3-small because it's fast and cost-effective. The trade-off is slightly lower quality than text-embedding-3-large, but for our volume (1,000 queries/day), the cost saving is significant. If quality becomes the bottleneck, we can upgrade later — the vector store supports re-indexing."

#### Step 5: Production Considerations (5 – 10 min)

This separates senior candidates from junior ones:

| Concern | What to Discuss |
|---|---|
| **Latency** | Where are the bottlenecks? How do you optimize (caching, streaming, async)? |
| **Cost** | API costs at expected volume. Where to optimize (caching, model selection, batching). |
| **Caching** | Semantic cache for similar queries, exact cache for repeated queries, embedding cache. |
| **Scaling** | Horizontal scaling of the API, vector DB scaling, async processing for ingestion. |
| **Failure modes** | What happens when the LLM API is down? When retrieval returns bad results? When the model hallucinates? |
| **Monitoring** | Latency dashboards, quality metrics, cost tracking, anomaly detection, alerting. |
| **A/B testing** | How to test improvements (shadow mode, gradual rollout, metric collection). |
| **Security** | PII filtering, data access controls, prompt injection prevention, audit logging. |

#### Step 6: Trade-Offs & Extensions (5 min)

Close with maturity:

- "The main trade-offs I made are: [X] for simplicity, [Y] for cost, [Z] for speed-to-market."
- "If we needed to handle 10x the volume, I'd change [specific component]."
- "If quality is the top priority over cost, I'd switch from [A] to [B]."
- "The first thing I'd build is [most critical component], because [reason]."

---

## Part 3: Domain Deep-Dive (Discussion-Based)

Some companies replace or supplement the live coding with a **technical discussion** where they probe your depth on specific AI topics.

### How It Works
The interviewer asks a series of progressively deeper questions on a topic. There's no code — just discussion and whiteboarding.

### How to Excel

**Structure your answers in layers:**

```
Layer 1: Concept overview (30 seconds)
Layer 2: How you've applied it (60 seconds)
Layer 3: Nuances, trade-offs, and edge cases (as deep as they go)
```

**Example topic: "Tell me about your experience with RAG systems."**

- **Layer 1**: "RAG combines retrieval from a knowledge base with LLM generation to produce grounded, accurate responses. It's useful when the LLM needs access to domain-specific or up-to-date information."
- **Layer 2**: "I built a RAG system for legal document Q&A. The pipeline uses structure-aware chunking, hybrid search in Weaviate, a cross-encoder reranker, and GPT-4 for generation. We serve about 2,000 queries daily with 89% answer accuracy."
- **Layer 3**: Follow-ups:
  - *"How do you handle documents that are too long for the context window?"* → Discuss hierarchical summarization, map-reduce patterns, or iterative retrieval.
  - *"How do you evaluate retrieval quality?"* → Discuss precision@k, recall@k, MRR, NDCG, and how you built golden eval sets.
  - *"What's the hardest failure mode you've dealt with?"* → Discuss a real example — maybe the model was confidently wrong because retrieved chunks were semantically similar but factually irrelevant.
  - *"When would you move away from RAG to fine-tuning?"* → When the knowledge is static, the task is narrow, and retrieval adds unnecessary latency/cost.

### Preparing for Domain Deep-Dives

For each major topic in your domain, prepare a **depth ladder**:

| Topic | Level 1 (Define It) | Level 2 (Applied It) | Level 3 (Edge Cases & Trade-Offs) |
|---|---|---|---|
| RAG | What it is, when to use it | Your specific implementation | Failure modes, eval strategies, optimization |
| Fine-tuning | What it is, LoRA/QLoRA | Dataset you prepared, metrics you measured | Catastrophic forgetting, data quality, cost analysis |
| Agent design | Patterns (ReAct, Plan-Execute) | Agent you built, tools you designed | Failure recovery, evaluation, multi-agent coordination |
| Evaluation | Standard metrics | Your eval pipeline | Human eval design, LLM-as-judge limitations, statistical significance |
| Deployment | Docker, CI/CD | What you deployed and how | Rollback strategies, canary deployments, monitoring |
| Prompt engineering | Basic techniques | Prompt you optimized and the result | Prompt versioning, A/B testing prompts, adversarial robustness |

---

## Universal Tips for the Technical Round

### Do These

| Action | Why |
|---|---|
| **Ask before you build** | Shows maturity and saves time |
| **Plan before you code** | Shows structure and makes your code easier to follow |
| **Narrate constantly** | The interviewer should never wonder what you're thinking |
| **Test incrementally** | Shows quality mindset and catches bugs early |
| **Use meaningful variable names** | Readability > cleverness |
| **Acknowledge production concerns** even when not implementing them | Shows senior-level thinking |
| **Draw diagrams** in system design | Visual thinkers communicate better |

### Avoid These

| Mistake | Why It Hurts |
|---|---|
| Coding in silence for 5+ minutes | Interviewer can't evaluate your thinking |
| Trying to build the perfect solution from line 1 | Wastes time; start simple, iterate |
| Refusing to ask for help when stuck | Looks stubborn, not strong |
| Over-engineering the solution | Shows poor scope judgement |
| Not handling errors at all | Shows you haven't worked in production |
| Memorizing solutions instead of understanding them | Falls apart under novel follow-ups |
| Ignoring the interviewer's hints | They're trying to help — take the hint |

---

## After the Session

- **Breathe.** This is the hardest round. If it felt challenging, that's normal — it was designed to be.
- **Note what you discussed**, what went well, and what you struggled with. This helps you prepare if there's another technical round.
- **Don't over-analyze.** Many candidates feel they "failed" technical rounds that they actually passed. Interviewers account for time pressure and nerves.

---

## Quick-Reference Checklist: Day of the Round

- [ ] Dev environment set up and tested
- [ ] Common libraries installed and imported
- [ ] API keys loaded and tested
- [ ] Screen sharing tested (show correct screen, hide personal tabs)
- [ ] Practiced narrated build at least 2 – 3 times
- [ ] Reviewed reusable code patterns
- [ ] Re-read hiring manager notes for topic hints
- [ ] Studied the company's product and likely AI challenges
- [ ] Prepared depth ladders for your core topics
- [ ] Water bottle nearby, quiet room, camera on

---

## Key Takeaway

> The technical deep-dive is not a test of what you know — it's a test of **how you think, build, and communicate under pressure**. A clean, narrated solution to 80% of the problem beats a messy, silent attempt at 100%. Show your process, make trade-offs explicit, and always connect your work to production reality.
