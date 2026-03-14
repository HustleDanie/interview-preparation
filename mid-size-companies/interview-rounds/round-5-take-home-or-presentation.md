# Round 5 (Optional): Take-Home Project or Presentation — How to Pass It Excellently

> **Format**: Async (take-home) or live (presentation) | **Duration**: 2 – 6 hours (take-home) or 30 – 60 min (presentation) | **Audience**: Hiring manager + 1 – 3 engineers from the team

---

## What This Round Actually Is

Not every mid-size company includes this round, but when they do, it's used as a **high-signal complement** to the live technical rounds. It exists because mid-size companies know that live coding has weaknesses — some great engineers perform poorly under time pressure, and some mediocre engineers are great at performing under pressure.

This round comes in two flavours:

| Format | What It Looks Like | When They Use It |
|---|---|---|
| **Take-home project** | You're given a prompt and 48 – 72 hours to submit a working solution | Most common; used to see how you build when you have time to think |
| **Presentation of past work** | You present a major project to the team (30 – 60 min + Q&A) | Used when they want to see depth of thinking without requiring a separate project |

Some companies offer you a **choice** between the two.

> **Key insight**: This round has the highest **differentiation potential**. Most candidates do "okay" here. A polished, thoughtful submission or presentation can vault you ahead of every other candidate.

---

# Part A: Take-Home Project

## What They're Evaluating

| Criteria | Weight | What They Want |
|---|---|---|
| **Does it work?** | 🔴 Critical | A functional, end-to-end solution that can be demonstrated |
| **Code quality** | 🔴 Critical | Clean, readable, well-structured code that a teammate could maintain |
| **Technical decisions** | 🔴 Critical | Thoughtful choices about architecture, tools, and trade-offs — documented and defensible |
| **Documentation** | 🟡 High | Clear README, setup instructions, and design rationale |
| **Testing** | 🟡 High | At least basic tests that show you think about correctness |
| **Production awareness** | 🟡 Medium | Error handling, logging, configuration management |
| **Going the extra mile** | 🟢 Differentiator | Evaluation metrics, demo video, deployment config, thoughtful README extras |

## Common Take-Home Prompts for AI Roles

### AI Engineer
- "Build a RAG-based Q&A system for this dataset of documents."
- "Create an API endpoint that takes user queries and returns AI-generated responses with source citations."
- "Build a data extraction pipeline that pulls structured information from unstructured text."
- "Implement a text classification system using an LLM and evaluate its performance."

### AI Systems Engineer
- "Build a model serving pipeline with Docker, a REST API, and basic monitoring."
- "Design and implement a data processing pipeline for [specific data type]."
- "Create a deployment configuration for an AI service with CI/CD, health checks, and logging."
- "Build a load testing framework for an AI endpoint and document the results."

### AI Agentic Engineer
- "Build a multi-step agent that can [perform specific task] using tool calling."
- "Create an agent that can query a database, analyze results, and generate a report."
- "Implement a multi-agent system that coordinates [specific workflow]."
- "Build an agent with memory that can handle multi-turn conversations with context."

## How to Execute the Take-Home Excellently

### Phase 1: Understanding (30 – 60 min)

**Read the brief 3 times.** Seriously. Then:

1. **Identify must-haves vs. nice-to-haves.** Most briefs have core requirements and "bonus" items. Get the core working first.
2. **Clarify ambiguities.** Send a short email with 1 – 3 focused questions:
   > "Thanks for sending the brief. Two quick clarifications: (1) Should the system handle both PDF and plain text, or is plain text sufficient? (2) Is there a preferred LLM provider, or can I choose? Happy to proceed once I hear back, or I'll assume [your default assumptions] if you'd prefer I just get started."
   - Asking smart clarifying questions is a signal of seniority. Don't worry about "bothering" them.
3. **Plan your layers:**

| Layer | What It Includes | Priority |
|---|---|---|
| **Layer 1: Core** | The thing works end-to-end. Input → process → output. | Must ship |
| **Layer 2: Quality** | Error handling, input validation, basic tests, clean code | Must ship |
| **Layer 3: Polish** | Thorough README, design doc, evaluation metrics, extra tests | Should ship |
| **Layer 4: Wow** | Demo video, deployment config, performance benchmarks, architecture diagram | Ships if time allows |

4. **Set a time budget.** If they say 4 – 6 hours, spend a maximum of 8. Over-investing signals poor time management or that the task was too hard for you. Under-investing (spending 2 hours on a 6-hour task) signals low effort.

### Phase 2: Building (The Core Hours)

#### Project Structure

Start with a clean structure. Here's a template:

```
project-name/
├── README.md               # Setup, usage, design decisions
├── requirements.txt         # or pyproject.toml
├── .env.example            # Template for API keys (never commit real keys)
├── .gitignore
├── src/
│   ├── __init__.py
│   ├── main.py             # Entry point
│   ├── config.py           # Configuration management
│   ├── pipeline.py         # Core AI logic
│   ├── models.py           # Pydantic models / data structures
│   └── utils.py            # Helper functions
├── tests/
│   ├── __init__.py
│   ├── test_pipeline.py
│   └── test_utils.py
├── data/
│   └── sample/             # Sample data for testing
├── docs/
│   └── architecture.md     # Design decisions (optional)
└── Dockerfile              # (optional but impressive)
```

#### Coding Standards

**Do this and you're already in the top 20% of submissions:**

```python
# ✅ Type hints on every function
async def retrieve_chunks(
    query: str,
    vector_store: VectorStore,
    top_k: int = 5,
    min_score: float = 0.7,
) -> list[RetrievedChunk]:
    """Retrieve relevant document chunks for a given query.
    
    Args:
        query: The user's natural language question.
        vector_store: The vector store to search.
        top_k: Maximum number of chunks to return.
        min_score: Minimum similarity score threshold.
    
    Returns:
        List of retrieved chunks, sorted by relevance.
    
    Raises:
        RetrievalError: If the vector store query fails.
    """
    try:
        results = await vector_store.similarity_search(
            query=query,
            k=top_k,
        )
        return [
            RetrievedChunk(
                text=r.page_content,
                metadata=r.metadata,
                score=r.score,
            )
            for r in results
            if r.score >= min_score
        ]
    except Exception as e:
        logger.error(f"Retrieval failed for query: {query[:50]}... Error: {e}")
        raise RetrievalError(f"Vector store query failed: {e}") from e
```

```python
# ❌ What most candidates submit
def get_stuff(q, db, n=5):
    r = db.search(q, n)
    return r
```

#### Build Incrementally with Git

Your commit history tells a story. Make it a good one:

```
feat: project scaffold with config and main entry point
feat: implement document chunking with recursive text splitter
feat: add embedding and vector store indexing
feat: implement retrieval with hybrid search
feat: add generation with source citations
feat: add FastAPI endpoint for Q&A queries
test: add unit tests for chunking and retrieval
fix: handle empty retrieval results gracefully
docs: add comprehensive README with setup and design decisions
chore: add Dockerfile for containerized deployment
```

**Don't do this:**
```
initial commit
update
fix
fix 2
final
final final
ok now final for real
```

#### Error Handling

Handle failures gracefully. This is **the** thing that separates production engineers from prototype builders:

```python
# For LLM API calls
async def generate_answer(query: str, context: list[str]) -> GeneratedAnswer:
    try:
        response = await client.chat.completions.create(
            model=settings.model_name,
            messages=build_messages(query, context),
            temperature=settings.temperature,
            max_tokens=settings.max_tokens,
        )
        return parse_response(response)
    except openai.RateLimitError:
        logger.warning("Rate limited — retrying with backoff")
        await asyncio.sleep(2)
        return await generate_answer(query, context)  # Simple retry
    except openai.APIConnectionError as e:
        logger.error(f"API connection failed: {e}")
        raise ServiceUnavailableError("LLM service temporarily unavailable") from e
    except Exception as e:
        logger.error(f"Unexpected error in generation: {e}")
        raise
```

#### Testing

Include **at least 5 – 10 tests**:

```python
# tests/test_pipeline.py

def test_chunking_preserves_content():
    """Verify that chunked text can be reconstructed to original."""
    text = "This is a test document with multiple sentences."
    chunks = chunk_text(text, chunk_size=20, overlap=5)
    assert len(chunks) > 0
    assert all(len(c.text) <= 25 for c in chunks)  # With some tolerance

def test_chunking_handles_empty_input():
    """Chunking an empty string should return an empty list."""
    chunks = chunk_text("", chunk_size=100)
    assert chunks == []

def test_retrieval_returns_relevant_chunks(mock_vector_store):
    """Retrieval should return chunks relevant to the query."""
    results = retrieve_chunks("What is the refund policy?", mock_vector_store)
    assert len(results) > 0
    assert any("refund" in r.text.lower() for r in results)

def test_retrieval_handles_no_results(empty_vector_store):
    """When no relevant chunks exist, return empty list."""
    results = retrieve_chunks("quantum physics", empty_vector_store)
    assert results == []

def test_generation_includes_citations():
    """Generated answers should include source citations."""
    answer = generate_answer("What is X?", context=["X is Y. Source: doc1.pdf"])
    assert answer.citations is not None
    assert len(answer.citations) > 0
```

### Phase 3: Documentation (Critical)

The README is the **first thing the reviewer reads**. A great README can save a mediocre implementation. A missing README can sink a great one.

#### README Template

```markdown
# [Project Name]

[One sentence: what this project does.]

## Overview

[2 – 3 sentences explaining the problem, your approach, and the key result.]

## Architecture

[Diagram or description of the system components and data flow.]

```
User Query → API Endpoint → Retrieval (Vector Store) → Reranking → Generation (LLM) → Response with Citations
```

## Design Decisions

| Decision | Choice | Rationale |
|---|---|---|
| Embedding model | text-embedding-3-small | Best cost/quality ratio for this doc size |
| Vector store | ChromaDB | Lightweight, no external service needed for evaluation |
| Chunking strategy | Recursive with 512 tokens, 50-token overlap | Balances context preservation with retrieval precision |
| Generation model | GPT-4o-mini | Sufficient quality for this task at lower cost |
| Framework | FastAPI | Async support, automatic OpenAPI docs, Python native |

## Setup

### Prerequisites
- Python 3.11+
- OpenAI API key

### Installation
1. Clone this repo
2. `pip install -r requirements.txt`
3. Copy `.env.example` to `.env` and add your API key
4. Run: `python -m src.main`

### Running Tests
```
pytest tests/ -v
```

## Usage

[Show example API calls, curl commands, or screenshots.]

## Evaluation

[If applicable: how you measured quality and what the results were.]

| Metric | Value |
|---|---|
| Retrieval Precision@5 | 0.82 |
| Answer accuracy (human eval, n=20) | 85% |
| Average latency | 2.3s |

## What I Would Improve With More Time

- [ ] Add semantic caching to reduce redundant LLM calls
- [ ] Implement hybrid search (dense + BM25)
- [ ] Add a reranker for better retrieval precision
- [ ] More comprehensive test coverage
- [ ] Support for PDF and HTML input (currently text-only)
- [ ] Streaming responses for better UX
```

### Phase 4: Final Checks (30 min)

| Check | How |
|---|---|
| **Clone test** | Clone your repo to a new directory. Follow your own README. Does it work? |
| **Linting** | Run `ruff` or `flake8`. Fix any obvious issues. |
| **Type checking** | Run `mypy` if you have time. |
| **Tests pass** | `pytest tests/ -v` — all green? |
| **No secrets committed** | Check `.env` is in `.gitignore`. No API keys in code. |
| **Clean git history** | Meaningful commit messages? No "fix fix fix" chains? |
| **README complete** | Setup instructions work? Design decisions documented? |

### Phase 5: Submission

**Write a submission message (3 – 5 sentences):**

> "Hi [name], here's my submission for the take-home project. I focused on building a robust RAG pipeline with hybrid retrieval, source citations, and comprehensive error handling. The README has setup instructions, design decisions, and evaluation results. The main trade-off I made was using ChromaDB locally instead of a hosted solution — at scale, I'd switch to Pinecone or Weaviate. Happy to discuss any part of the design or walk through the code live."

**Optional but powerful: Record a 3 – 5 minute Loom demo:**
1. Show the project running (30 sec).
2. Walk through the architecture (60 sec).
3. Show one interesting design decision (60 sec).
4. Show the code structure briefly (30 sec).
5. Mention what you'd do with more time (30 sec).

---

# Part B: Presentation of Past Work

## What They're Evaluating

| Criteria | Weight | What They Want |
|---|---|---|
| **Technical depth** | 🔴 Critical | Can you explain a complex system and the decisions behind it? |
| **Communication clarity** | 🔴 Critical | Can you make a technical topic understandable and interesting? |
| **Handling Q&A** | 🔴 Critical | Can you think on your feet when probed with deep questions? |
| **Self-awareness** | 🟡 High | Do you acknowledge trade-offs, mistakes, and things you'd change? |
| **Impact orientation** | 🟡 High | Did the project have measurable outcomes? |
| **Storytelling** | 🟢 Differentiator | Can you make the audience care about the problem and your solution? |

## How to Choose What to Present

Pick the project that has:
- ✅ **The strongest relevance** to the role you're interviewing for.
- ✅ **Enough complexity** to sustain a 20 – 30 minute talk + 15 – 30 minutes of Q&A.
- ✅ **Clear, quantifiable results.**
- ✅ **Interesting trade-offs** you can discuss.
- ✅ **Your significant individual contribution** (not just "I was on the team").

If none of your projects tick all boxes, pick the strongest one and add context for the missing elements.

## Presentation Structure (30 – 45 min total)

### Slide Deck Template (10 – 15 slides)

| Slide # | Content | Time |
|---|---|---|
| **1** | Title: Project name + your name + one-line tagline | 15 sec |
| **2** | The Problem: What problem did you solve? Why did it matter? Who was affected? | 2 min |
| **3** | Context & Constraints: What were the constraints (time, budget, data, team)? | 1 – 2 min |
| **4** | Approach Overview: High-level architecture diagram. What components, what data flow. | 3 min |
| **5 – 8** | Technical Deep-Dive: 3 – 4 slides going deep on the most interesting technical decisions. One decision per slide. | 10 – 12 min |
| **9** | Evaluation & Results: How did you measure success? What were the numbers? | 2 – 3 min |
| **10** | Challenges & Failures: What went wrong? How did you handle it? | 2 – 3 min |
| **11** | Lessons Learned: What would you do differently? What would you carry forward? | 2 min |
| **12** | Future Work: If you continued the project, what's next? | 1 min |
| **13** | Q&A | 15 – 30 min |

### Deep-Dive Slides (Slides 5 – 8): How to Structure Them

Each deep-dive slide should cover **one decision**:

```
DECISION: [What choice you made]
CONTEXT: [What problem this decision solved]
OPTIONS: [What alternatives you considered]
CHOICE: [What you chose and why]
TRADE-OFF: [What you gave up]
RESULT: [What happened]
```

**Example:**

> **Decision**: Hybrid retrieval instead of pure dense search
>
> **Context**: Pure dense retrieval was missing documents that contained specific terminology (e.g., legal clause names) because the embedding model didn't capture exact keyword matches well.
>
> **Options**: (1) Fine-tune the embedding model, (2) Switch to BM25 only, (3) Hybrid dense + BM25 with reciprocal rank fusion.
>
> **Choice**: Option 3 — hybrid search with RRF scoring.
>
> **Trade-off**: Added complexity in the retrieval layer and slightly higher latency (+200ms). But retrieval recall improved from 72% to 91%.
>
> **Result**: End-to-end answer accuracy went from 68% to 87%.

### Presentation Tips

**Content:**
- Lead with the **problem and impact**, not the technology. Make the audience care before you explain how.
- Use **diagrams heavily**. A good architecture diagram is worth 500 words.
- Include **numbers everywhere**. Latency, accuracy, cost, user impact, data volume.
- Show **real examples**: "Here's an actual query and the system's response."
- Acknowledge **failures and mistakes** — this shows maturity and self-awareness.

**Delivery:**
- **Practice your talk 3 times** minimum. The first time is always rough.
- **Time yourself.** If you have 30 minutes, aim for 18 – 20 minutes of presentation to leave generous Q&A time.
- **Don't read slides.** The slides should be supporting visuals, not a script.
- **Look at the camera** (for video) or the audience (for in-person).
- **Slow down.** Nerves make you speed up. Deliberately pace yourself.
- **Pause after key points.** Give the audience time to absorb.

**Q&A:**
- **The Q&A is at least as important as the presentation.** This is where they test depth.
- **It's okay to pause before answering.** "That's a great question — let me think about that for a moment."
- **If you don't know, say so**: "I haven't considered that angle. My first instinct would be [X], but I'd want to test it before committing."
- **Redirect if needed**: "I don't have the exact numbers for that, but the general trend was [X]. I can follow up with specifics if helpful."

### Common Q&A Questions Across AI Roles

| Question | What They're Probing |
|---|---|
| "Why did you choose [tool/model] over alternatives?" | Trade-off awareness, breadth of knowledge |
| "What would break if you scaled this to 100x?" | Production and scaling awareness |
| "How would you evaluate this differently now?" | Growth and learning |
| "What was the hardest bug or failure?" | Problem-solving, resilience |
| "If you started over, what would you change?" | Self-awareness, technical judgment |
| "How did you handle [specific edge case]?" | Thoroughness |
| "What did the team think of this approach?" | Collaboration, communication |
| "What's the cost of running this?" | Business awareness |
| "How do you monitor this in production?" | Production maturity |
| "What are the security/privacy implications?" | Responsibility |

---

## Summary: What Separates Good From Great

| Level | Take-Home | Presentation |
|---|---|---|
| **Mediocre** | It works, barely. No README. No tests. Messy code. | Unfocused, too much on one slide, no numbers, can't answer follow-ups. |
| **Good** | Works well. Decent code. Has a README. Handles happy path. | Clear structure, good diagrams, solid answers to basic follow-ups. |
| **Great** | Clean code, thorough README, tests, error handling, evaluation metrics, design decisions documented. | Compelling story, deep technical decisions, acknowledges trade-offs, handles tough Q&A with ease, quantified impact. |
| **Outstanding** | All of the above + demo video, Dockerfile, comprehensive eval, going beyond the brief in a thoughtful way. | All of the above + the audience learns something new, presentation feels effortless, Q&A becomes a collaborative discussion. |

---

## Quick-Reference Checklist

### Take-Home — Before Submission
- [ ] Solution works end-to-end (tested from fresh clone)
- [ ] Code has type hints, docstrings, and meaningful names
- [ ] Error handling for critical paths
- [ ] At least 5 – 10 tests passing
- [ ] README with setup, usage, design decisions, and future improvements
- [ ] No secrets in code (API keys in .env, not hardcoded)
- [ ] Clean, meaningful git history
- [ ] .env.example file included
- [ ] (Bonus) Dockerfile
- [ ] (Bonus) Demo video
- [ ] (Bonus) Evaluation metrics

### Presentation — Before the Session
- [ ] 10 – 15 slides, 18 – 20 minutes of content
- [ ] Practiced at least 3 times
- [ ] Timed yourself
- [ ] Architecture diagram included
- [ ] Numbers and metrics on every relevant slide
- [ ] Anticipated 10 Q&A questions and prepared answers
- [ ] Screen sharing tested
- [ ] Backup plan if screen share fails (share slides link in chat)

---

## Key Takeaway

> This round is your **highest-leverage opportunity** to stand out. Most candidates submit something that works and call it done. The ones who get the offer submit something that works, is clean, is documented, and tells a story about how they think. Whether it's a take-home or a presentation, **treat it as a product, not a homework assignment.**
