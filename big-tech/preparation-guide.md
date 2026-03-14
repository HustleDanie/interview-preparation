# Big Tech Interview Preparation Guide

> For **AI Engineers**, **AI Systems Engineers**, and **AI Agentic Engineers**

---

## 1. What Is a Big Tech Company?

Big Tech refers to **large, established technology companies** with thousands of employees, billions in revenue, and highly structured hiring processes. These companies have industrialized their interview pipelines — every round has a rubric, every interviewer submits a scorecard, and a hiring committee (not a single person) decides your fate.

### Characteristics

| Signal | What to Look For |
|---|---|
| **Team size** | 1,000 – 300,000+ employees |
| **Revenue** | $1B+ ARR, usually public companies or late-stage private unicorns |
| **Product maturity** | Mature, globally scaled products with millions or billions of users |
| **Brand recognition** | Household name or widely recognized in the tech industry |
| **Engineering org** | Highly structured — levels (L3 – L8+), promotion committees, calibration processes |
| **Hiring process** | Standardized, 5 – 7 rounds, hiring committee, recruiter-managed pipeline |
| **Role scope** | Highly specialized — you own a narrow slice of a massive system |
| **Compensation** | Top-of-market: base + RSU/stock + bonus + sign-on. Bands well-defined by level. |
| **Interview style** | Algorithmic coding (Leetcode), system design, behavioural (leadership principles), ML-specific rounds |

### Who Falls Into This Category

**Tier 1 — FAANG / MAANG and equivalents:**
- Google / Alphabet (DeepMind, Google Brain, Google Cloud AI)
- Meta (FAIR, GenAI)
- Amazon (AWS AI, Alexa, AGI team)
- Apple (Siri, ML platform, Apple Intelligence)
- Microsoft (Azure AI, Copilot, OpenAI partnership)
- Netflix (Recommendation, Search)

**Tier 2 — Large tech companies with major AI orgs:**
- NVIDIA (AI research, inference, GPU ecosystem)
- Tesla (Autopilot, Optimus, AI infra)
- Salesforce (Einstein AI)
- Adobe (Sensei, Firefly)
- IBM (watsonx)
- Oracle (Cloud AI)
- Intel, AMD, Qualcomm (AI silicon and frameworks)

**Tier 3 — Large AI-native companies at scale:**
- OpenAI (1,000+ employees, billions in revenue)
- Anthropic (growing rapidly, Series D+)
- Databricks (AI + data at enterprise scale)
- Snowflake (AI/ML features on data cloud)
- Palantir (AIP, large enterprise AI)
- Stripe, Uber, Airbnb, Spotify, LinkedIn (massive AI/ML teams within large platforms)

> **Note**: The line between "large AI-native" (Tier 3) and "mid-size" can blur. The test is: **Does the company have a standardized, multi-round interview process with a hiring committee?** If yes, prepare with this guide.

---

## 2. How to Identify a Big Tech Company From a Job Vacancy

### Quick Identification Checklist

- [ ] **Employee count**: 1,000+ on LinkedIn.
- [ ] **Public or late-stage private**: Publicly traded, or private with $500M+ total funding.
- [ ] **Levels in the job title**: The posting mentions levels (L4, IC5, E5, SDE II, etc.) or specific seniority bands.
- [ ] **Structured JD language**: Phrases like *"design and implement scalable ML systems"*, *"drive cross-org alignment"*, *"influence technical direction"*, *"mentor junior engineers"* — language calibrated to a leveling rubric.
- [ ] **Team specificity**: You're joining a named team within a named org (e.g., "Search Quality team within Google Cloud AI").
- [ ] **Benefits section is detailed**: Comprehensive healthcare, RSU, 401(k) match, parental leave, relocation — all spelled out.
- [ ] **Interview process is documented**: Some big companies publish their interview process publicly or the recruiter sends a detailed prep guide.
- [ ] **Recruiter outreach**: A dedicated recruiter manages your process end-to-end.
- [ ] **Glassdoor has 100+ interview reviews** for this role type.

> **Rule of thumb**: If the company has **formal engineering levels**, a **hiring committee**, and **more than 5 interview rounds**, prepare with this guide.

---

## 3. How Big Tech Companies Interview (and Why)

Big Tech interviews are **standardized talent pipelines**. They're designed to:

1. **Minimize false positives** at scale (they'd rather reject 10 good candidates than hire 1 bad one).
2. **Calibrate candidates against a universal bar** (so an "L5 at Google" means something consistent).
3. **Evaluate across multiple dimensions** independently (each interviewer scores one area, reducing individual bias).

### What They ARE Testing

| Dimension | What It Means |
|---|---|
| **Algorithmic thinking** | Can you solve structured problems efficiently? Do you understand time/space complexity? |
| **System design** | Can you architect large-scale systems? Do you think about trade-offs at massive scale? |
| **ML/AI depth** | Do you deeply understand the models, techniques, and systems behind AI? |
| **Coding proficiency** | Can you write clean, correct, efficient code under time pressure? |
| **Behavioural / Leadership** | Do you demonstrate the company's leadership principles through real examples? |
| **Communication** | Can you explain complex ideas clearly, ask good questions, and collaborate effectively? |
| **Leveling signals** | Does your scope of impact, autonomy, and technical influence match the target level? |

### What They Are NOT Testing (But Candidates Assume)

- ❌ Whether you can memorize 500 Leetcode solutions.
- ❌ Whether you know every ML paper published this year.
- ❌ Whether you can design a system exactly like theirs.
- ❌ Whether you're the "smartest person in the room."

They ARE testing: **Can you think clearly, communicate well, and operate at the scope expected for your level?**

### Typical Interview Flow

| Round | Format | Duration | Purpose |
|---|---|---|---|
| 1 | Recruiter screen | 30 min | Qualification, level calibration, logistics, salary range |
| 2 | Phone screen / Technical screen | 45 – 60 min | Coding + basic ML/AI questions to filter before onsite |
| 3 | Onsite / Virtual loop — Coding (1 – 2 sessions) | 45 – 60 min each | Algorithmic problems + practical coding (often Leetcode-style + applied) |
| 4 | Onsite — System design | 45 – 60 min | Design a large-scale AI system end-to-end |
| 5 | Onsite — ML/AI deep-dive | 45 – 60 min | ML fundamentals, model design, AI-specific problem-solving |
| 6 | Onsite — Behavioural / Leadership | 45 – 60 min | Leadership principles, past experience, collaboration, conflict |
| 7 (some companies) | Hiring committee review | N/A (you're not present) | Committee reviews all scorecards and makes a hire/no-hire decision |

**Total timeline**: 3 – 8 weeks from first contact to offer.

**Company-specific variations:**

| Company | Notable Differences |
|---|---|
| **Google** | Hiring committee is very powerful; individual interviewers don't know the final decision. "Googleyness" round. |
| **Meta** | Typically 2 coding + 1 system design + 1 behavioural. "Move Fast" and "Be Bold" are real evaluation criteria. |
| **Amazon** | 14 Leadership Principles dominate the behavioural round (often 2 behavioural rounds). Bar raiser interviewer. |
| **Apple** | More team-specific; the hiring manager has strong influence. Less standardized than Google/Meta. |
| **Microsoft** | "As appropriate" interview with a senior decision-maker. Level-specific bar. |
| **OpenAI / Anthropic** | More applied/practical than pure Leetcode. Strong emphasis on AI-specific depth and research taste. |
| **NVIDIA** | Heavy focus on systems, GPU, inference optimization. Expect CUDA / systems-level questions. |

---

## 4. General Preparation Strategy

Big Tech preparation requires **structured, sustained effort**. You cannot cram for these interviews in a week. Plan for **4 – 8 weeks** of preparation, depending on your baseline.

### Step A: Determine Your Target Level

Before you start preparing, understand **what level you're targeting**. The level determines the bar for every round.

| Level (Google-ish) | Equivalent | Scope Expected |
|---|---|---|
| **L3 / Junior** | SDE I, IC3 | Completes well-defined tasks. Writes clean code. Learning the domain. |
| **L4 / Mid** | SDE II, IC4 | Owns features end-to-end. Makes good technical decisions within a team. |
| **L5 / Senior** | Senior SDE, IC5 | Owns projects across a team. Influences technical direction. Mentors others. |
| **L6 / Staff** | Staff, IC6 | Drives technical strategy across multiple teams. Recognized expert. |
| **L7+ / Principal** | Principal+, IC7+ | Org-wide or company-wide technical influence. Sets the direction. |

**Why this matters:**
- At **L3 – L4**, the coding round is weighted heavily. You need to nail Leetcode.
- At **L5**, system design becomes equally important. You need to demonstrate ownership and technical leadership.
- At **L6+**, the behavioural / leadership round is critical. You need to show cross-team influence and strategic thinking.

### Step B: Research the Specific Company and Team

Even within Big Tech, teams are different. Spend **2 – 3 hours** on targeted research.

1. **Study the team's product area.** If you're interviewing for Google Search AI, understand how search works. If it's Meta's GenAI team, understand their AI products.
2. **Read the company's AI blog / research page:**
   - Google AI Blog
   - Meta AI Research
   - Amazon Science
   - Microsoft Research
   - OpenAI Blog
   - Anthropic Research
3. **Read Glassdoor interview reviews** for your specific role. People literally share the questions they were asked.
4. **Understand the company's leadership principles or values.** These are used as evaluation rubrics:
   - Amazon: 16 Leadership Principles
   - Google: "Googleyness" + General Cognitive Ability
   - Meta: "Move Fast", "Be Bold", "Build Social Value", "Focus on Long-term Impact", "Be Open"
   - Microsoft: "Growth Mindset"
5. **Find the team on LinkedIn.** What are the backgrounds of current team members? What tools and frameworks do they mention?
6. **Talk to people who've interviewed there.** Blind, TeamBlind, and specific interview prep communities (e.g., interviewing.io) are goldmines.

### Step C: Prepare for Coding Rounds (The Leetcode Grind)

This is the most time-consuming part of Big Tech prep — and the one that differs most from startup/mid-size preparation.

#### The Reality

Big Tech coding rounds are **Leetcode-style problems** with varying degrees of AI/ML flavour depending on the role:

- **AI Engineer**: Mostly standard Leetcode (arrays, strings, trees, graphs, DP) + some applied problems (data processing, API design).
- **AI Systems Engineer**: Leetcode + systems-oriented problems (concurrency, distributed systems, caching).
- **AI Agentic Engineer**: Leetcode + applied agent/pipeline problems. Some companies (OpenAI, Anthropic) lean more applied than algorithmic.

#### What to Study

| Topic | Priority | What to Know |
|---|---|---|
| **Arrays & Strings** | 🔴 Must | Two pointers, sliding window, prefix sums, sorting |
| **Hash Maps & Sets** | 🔴 Must | Frequency counting, grouping, two-sum patterns |
| **Trees & Graphs** | 🔴 Must | BFS, DFS, traversals, shortest path, topological sort |
| **Dynamic Programming** | 🔴 Must | 1D/2D DP, memoization, common patterns (knapsack, LCS, intervals) |
| **Binary Search** | 🟡 High | Search on answer, rotated arrays, bisect patterns |
| **Linked Lists** | 🟡 High | Reversal, cycle detection, merge operations |
| **Stacks & Queues** | 🟡 High | Monotonic stack, BFS with queue, parentheses problems |
| **Heaps / Priority Queues** | 🟡 High | Top-K, merge K sorted, median stream |
| **Recursion & Backtracking** | 🟡 High | Permutations, combinations, constraint satisfaction |
| **Tries** | 🟢 Medium | Autocomplete, word search |
| **Union Find** | 🟢 Medium | Connected components, grouping |
| **Bit Manipulation** | 🟢 Lower | XOR tricks, bit counting |

#### Study Plan

| Phase | Duration | Focus | Daily Commitment |
|---|---|---|---|
| **Phase 1: Foundations** | Week 1 – 2 | Easy problems. 1 topic per day. Focus on understanding patterns, not memorizing solutions. | 2 – 3 problems/day (1.5 – 2 hrs) |
| **Phase 2: Pattern Mastery** | Week 3 – 4 | Medium problems. Mix topics. Practice recognizing which pattern applies. | 2 – 3 problems/day (2 hrs) |
| **Phase 3: Hard + Timed** | Week 5 – 6 | Hard problems + timed practice (45 min per problem). Simulate interview conditions. | 1 – 2 problems/day (2 hrs) |
| **Phase 4: Mock + Review** | Week 7 – 8 | Mock interviews (Pramp, interviewing.io, or with a friend). Review weak areas. | 1 mock + 1 – 2 problems/day |

**Total**: ~150 – 200 problems over 6 – 8 weeks. Focus on **Blind 75** or **Neetcode 150** as curated lists.

#### Coding Round Execution Framework

During the actual interview, follow this **25-minute framework** (for a 45-min round):

| Step | Time | What to Do |
|---|---|---|
| **1. Understand** | 3 min | Read the problem. Repeat it back. Ask clarifying questions (input size, edge cases, constraints). |
| **2. Examples** | 2 min | Walk through 1 – 2 examples by hand. Confirm expected output. |
| **3. Approach** | 5 min | State your approach **before coding**. Discuss time/space complexity. If you see multiple approaches, mention the brute force first, then the optimal. |
| **4. Code** | 12 – 15 min | Write clean, readable code. Use descriptive variable names. Talk as you code. |
| **5. Test** | 3 – 5 min | Walk through your code with the given example (dry run). Test an edge case. |
| **6. Optimize** | 2 – 3 min | Discuss: Can this be optimized? What's the time/space complexity? |

**Critical rules:**
- **Always state complexity.** Time and space. For every approach.
- **Always handle edge cases.** Empty input, single element, duplicates, negative numbers.
- **Always narrate.** The interviewer scores your thinking as much as your code.
- **If stuck**: Try a brute force approach first. Then optimize. A working O(n²) solution beats a broken O(n) solution.

### Step D: Prepare for System Design (AI-Focused)

Big Tech system design is **different from mid-size**. The scale is 100 – 1000x larger, and interviewers expect you to reason about distributed systems, massive data pipelines, and global infrastructure.

#### What They Expect by Level

| Level | System Design Expectation |
|---|---|
| **L3 – L4** | May not have a full system design round. If present, expect a simpler, focused design. |
| **L5** | Design a complete system. Drive the discussion. Make and justify trade-offs. |
| **L6+** | Design a complex, multi-service system. Show cross-team thinking. Discuss organizational trade-offs. |

#### Common AI System Design Prompts at Big Tech

- "Design a recommendation system for YouTube/Instagram/TikTok."
- "Design a search ranking system with ML."
- "Design a real-time content moderation system."
- "Design a large-scale document processing pipeline."
- "Design a conversational AI platform (like ChatGPT / Alexa)."
- "Design a feature store for ML models."
- "Design an ML model training and serving platform."
- "Design a real-time fraud detection system."
- "Design an AI-powered ad targeting system."
- "Design a multi-modal AI system (text + image)."

#### The 7-Step Framework for Big Tech System Design

| Step | Time | What to Do |
|---|---|---|
| **1. Clarify requirements** | 3 – 5 min | Functional (what does it do?) and non-functional (scale, latency, availability, cost). Ask about users, QPS, data size, SLAs. |
| **2. Define scope** | 2 min | "For this discussion, I'll focus on [core flow]. I'll touch on [secondary concerns] if time permits." |
| **3. High-level design** | 8 – 10 min | Draw the major components: clients, API gateway, services, ML pipeline, data stores, cache, queue. Show data flow. |
| **4. Data model & storage** | 5 – 7 min | What data is stored where? Schema design. SQL vs. NoSQL. Feature store. Vector DB. Object storage for embeddings/models. |
| **5. ML/AI deep-dive** | 10 – 15 min | This is YOUR section. Model architecture, training pipeline, serving infrastructure, feature engineering, evaluation. Go deep. |
| **6. Scale & production** | 5 – 8 min | Scaling strategies, caching, partitioning, replication, failure handling, monitoring, A/B testing. |
| **7. Trade-offs & evolution** | 3 – 5 min | What would you change at 10x/100x scale? What are the key bottlenecks? What's the V2 roadmap? |

#### AI/ML Deep-Dive Topics to Cover in System Design

| Topic | What to Discuss |
|---|---|
| **Data pipeline** | Collection, cleaning, labeling, feature engineering, storage, versioning |
| **Model training** | Architecture choice, training infrastructure, hyperparameter tuning, distributed training |
| **Model serving** | Online vs. batch inference, model format, serving framework, latency requirements |
| **Feature store** | Online (low-latency) vs. offline (batch) features, consistency |
| **Evaluation** | Offline metrics, online metrics (A/B tests), shadow mode, interleaving experiments |
| **Feedback loops** | How user signals feed back into training data. Cold start problem. |
| **Model lifecycle** | Versioning, rollback, canary deployment, champion-challenger patterns |
| **Monitoring** | Data drift, model drift, prediction quality, feature importance tracking |

### Step E: Prepare for ML/AI Deep-Dive Round

Some Big Tech companies have a **dedicated ML round** separate from system design. This tests your depth on ML fundamentals and AI-specific knowledge.

#### For All AI Roles (ML Fundamentals)

| Topic | What to Know | Depth |
|---|---|---|
| **ML basics** | Supervised vs. unsupervised, bias-variance, overfitting, regularization, cross-validation | Can explain clearly and apply to real problems |
| **Evaluation metrics** | Precision, recall, F1, AUC-ROC, AUC-PR, confusion matrix, calibration | Know when to use which and why |
| **Feature engineering** | Numerical, categorical, text, temporal features; scaling, encoding, selection | Can discuss feature design for a specific problem |
| **Training & optimization** | SGD, Adam, learning rate schedules, batch size effects, early stopping | Understand the intuition, not just the formulas |
| **Neural network fundamentals** | Architectures (FFN, CNN, RNN, Transformer), attention mechanism, positional encoding | Can explain how Transformers work from first principles |
| **NLP fundamentals** | Tokenization, embeddings (Word2Vec, BERT, sentence embeddings), language modeling | Solid understanding of the evolution from TF-IDF to LLMs |
| **LLM internals** | Pre-training, fine-tuning (SFT, RLHF, DPO), inference (KV cache, speculative decoding), scaling laws | Can discuss how modern LLMs work under the hood |
| **Embeddings & similarity** | Vector spaces, cosine similarity, ANN search (HNSW, IVF), dimensionality reduction | Can design and debug a similarity search system |
| **RAG systems** | Chunking, retrieval strategies, reranking, generation, evaluation | Production-level understanding |
| **Evaluation for generative AI** | Human eval, LLM-as-judge, reference-based metrics (BLEU, ROUGE), task-specific eval | Can design an eval framework for any generative task |
| **ML system trade-offs** | Latency vs. quality, cost vs. accuracy, real-time vs. batch, simple model vs. complex model | Can discuss trade-offs with nuance |

#### Additional for AI Systems Engineers

| Topic | What to Know |
|---|---|
| **Distributed training** | Data parallelism, model parallelism, pipeline parallelism, FSDP, DeepSpeed |
| **Model serving at scale** | vLLM, TGI, Triton, TensorRT-LLM; batching strategies, KV cache management |
| **GPU infrastructure** | A100/H100 specs, multi-GPU, NVLink, InfiniBand, GPU memory management |
| **ML platform design** | Feature store, experiment tracking (MLflow, W&B), model registry, deployment pipelines |
| **Data infrastructure** | Data lakes, data warehouses, streaming (Kafka), batch processing (Spark) |
| **Reliability at scale** | SLOs for ML services, graceful degradation, fallback models, circuit breakers |

#### Additional for AI Agentic Engineers

| Topic | What to Know |
|---|---|
| **Agent architectures at scale** | ReAct, Plan-and-Execute, Tree of Thought, multi-agent orchestration patterns |
| **Tool use & function calling** | Robust tool design, schema evolution, authentication, error handling at scale |
| **Memory systems** | Hierarchical memory, knowledge graphs, retrieval-augmented memory |
| **Evaluation for agents** | Task completion benchmarks, tool call accuracy, cost-per-task, safety evaluation |
| **Safety & alignment** | Jailbreak prevention, output validation, RLHF, constitutional AI, red-teaming |
| **Orchestration at scale** | Concurrent agents, resource management, observability, cost management |

#### Common ML Deep-Dive Questions

**Theoretical:**
- "Explain how the Transformer architecture works."
- "What is the attention mechanism? Why is it important?"
- "Explain the difference between pre-training, fine-tuning, and RLHF."
- "What are the trade-offs between fine-tuning and prompt engineering?"
- "How does a vector database work? What are the indexing strategies?"

**Applied:**
- "You have a classification model with 95% accuracy but the business says it's not working. What do you investigate?"
- "Your LLM is hallucinating on 10% of queries. How do you diagnose and fix this?"
- "You need to reduce inference latency from 2 seconds to 200ms. What are your options?"
- "Design an evaluation framework for a new RAG system."
- "Your training data has significant label noise. How do you handle it?"

**Open-ended:**
- "What are the biggest challenges with deploying LLMs in production?"
- "When would you build your own model vs. use an API?"
- "How do you think about the cost-quality trade-off in AI systems?"
- "What's the most interesting AI paper or technique you've seen recently?"

### Step F: Prepare for Behavioural / Leadership Rounds

Big Tech behavioural rounds are **the most structured** of any company type. They map directly to published (or internal) leadership principles, and interviewers use rubrics to score your responses.

#### Company-Specific Preparation

**Amazon (16 Leadership Principles — the gold standard):**

The most critical principles for AI roles:

| Principle | What to Demonstrate | Example Question |
|---|---|---|
| **Customer Obsession** | You start with the customer and work backward | "Tell me about a time you went above and beyond for a customer or user." |
| **Ownership** | You think long-term and don't sacrifice long-term for short-term | "Tell me about a time you took on something outside your area of responsibility." |
| **Invent and Simplify** | You innovate and find simpler solutions | "Tell me about a time you found a simple solution to a complex problem." |
| **Are Right, A Lot** | You have good judgment and strong instincts | "Tell me about a time you made a difficult decision with limited data." |
| **Learn and Be Curious** | You're never done learning | "Tell me about something you recently taught yourself." |
| **Bias for Action** | You value speed and recognize that many decisions are reversible | "Tell me about a time you took action without waiting for permission." |
| **Dive Deep** | You operate at all levels and stay connected to the details | "Tell me about a time you had to dig deep into the details to solve a problem." |
| **Have Backbone; Disagree and Commit** | You respectfully challenge decisions, then commit fully | "Tell me about a time you disagreed with your manager or team." |
| **Deliver Results** | You focus on the key inputs and deliver them with the right quality and timely fashion | "Tell me about a time you delivered a project under tight constraints." |

**Google:**
| Dimension | What to Demonstrate |
|---|---|
| **General Cognitive Ability** | Can you learn new things quickly? Can you solve novel problems? |
| **Leadership** | Do you step up when needed, even without a title? |
| **Googleyness** | Are you comfortable with ambiguity? Do you collaborate well? Are you humble? |
| **Role-Related Knowledge** | Do you have the technical depth for this specific role? |

**Meta:**
| Value | What to Demonstrate |
|---|---|
| **Move Fast** | You ship quickly, iterate, and aren't paralyzed by uncertainty |
| **Be Bold** | You take calculated risks and aren't afraid to challenge the status quo |
| **Focus on Long-Term Impact** | You think about sustainable solutions, not just quick wins |
| **Build Social Value** | Your work benefits users and society |
| **Be Open** | You're transparent, give and receive feedback, and collaborate openly |

#### Prepare 12 – 15 STAR-L Stories

For Big Tech, you need **more stories** than for mid-size because:
- There are more behavioural questions (often an entire 45 – 60 min round).
- Interviewers may ask for **2 – 3 examples** for the same principle.
- You need to match stories to specific leadership principles.

**Map each story to 2 – 3 principles it can serve:**

| Story Title | Primary Principle | Also Covers |
|---|---|---|
| "Rebuilt the RAG pipeline from scratch" | Ownership, Dive Deep | Deliver Results, Invent & Simplify |
| "Disagreed with tech lead on fine-tuning vs. prompting" | Backbone / Disagree & Commit | Are Right A Lot, Bias for Action |
| "Caught and fixed API cost spike" | Ownership, Customer Obsession | Dive Deep, Deliver Results |
| "Pivoted mid-project when priorities changed" | Bias for Action | Learn & Be Curious, Deliver Results |
| "Mentored junior engineer on vector databases" | Learn & Hire the Best | Leadership, Collaboration |

**For each story, calibrate to your target level:**

| Level | Story Should Show... |
|---|---|
| **L3 – L4** | Individual contribution, learning, and growth. Working well within a team. |
| **L5** | Owning a project end-to-end, influencing team decisions, mentoring, cross-functional collaboration. |
| **L6+** | Driving strategy across teams, organizational impact, technical vision, raising the bar for others. |

#### Answering Framework for Big Tech

Use **STAR-L** but add **metrics and scope signals**:

```
SITUATION (2 sentences): Set the context. Mention team size, company context, stakeholders.
TASK (1 sentence): YOUR specific responsibility. Make scope clear.
ACTION (3 – 5 sentences): Step-by-step, what YOU did. Use "I", not "we."
         For senior+ levels, include: decisions you made, people you influenced, trade-offs.
RESULT (1 – 2 sentences): Quantified outcome. Business impact. User impact.
LEARNING (1 sentence): What did you take away? How did it change your approach?
```

**Time target**: 2 – 3 minutes per answer (slightly longer than mid-size because they expect more structure and depth).

### Step G: During the Interview Loop

The Big Tech "onsite" (often virtual now) is a **marathon**. 4 – 6 back-to-back sessions in one day.

#### Day-of Strategy

1. **Energy management**: Eat well, sleep well the night before. Bring water and snacks. You'll need sustained focus for 4 – 5 hours.
2. **Treat each round independently**: A bad round doesn't mean you've failed. The hiring committee weighs all signals. One "Strong Hire" can offset one "Lean No Hire."
3. **Ask every interviewer's name and role**: This helps you tailor your communication and makes the interaction more personal.
4. **Narrate everything in coding rounds**: The interviewer can help you if they can follow your thinking. Silent coding gets you no credit for good thinking.
5. **Drive the system design**: At L5+, you should be **leading** the design discussion, not waiting for the interviewer to guide you.
6. **Be specific in behavioural rounds**: Names, dates, metrics. "About 18 months ago, when I was on the Search team..." is 10x more credible than "One time, at my old job..."
7. **Ask genuine questions**: At the end of each round, ask 1 – 2 questions that show thoughtfulness:
   - "What's the biggest technical challenge the team is working on?"
   - "What does the path from prototype to production look like on your team?"
   - "What's something you wish you'd known before joining?"

---

## 5. Preparation Timeline: 6 – 8 Week Plan

| Week | Focus | Daily Time | Details |
|---|---|---|---|
| **1** | Assessment + Foundation | 2 hrs | Take a practice coding test. Identify weak areas. Research target company and role. Start easy Leetcode problems (arrays, strings, hash maps). |
| **2** | Coding — Core Patterns | 2 – 3 hrs | Trees, graphs, BFS/DFS, binary search. 2 – 3 problems/day. Focus on pattern recognition. |
| **3** | Coding — Advanced Patterns | 2 – 3 hrs | DP, heaps, sliding window, monotonic stack. 2 – 3 problems/day. Start timing yourself. |
| **4** | System Design + ML Fundamentals | 2 – 3 hrs | Study 2 system design problems. Review ML fundamentals. Read company AI blog posts. |
| **5** | System Design + AI Deep-Dive | 2 – 3 hrs | Practice 2 more system design problems (AI-focused). Prepare ML deep-dive topics. Practice explaining Transformer architecture, RAG, embedding spaces, eval frameworks. |
| **6** | Behavioural + Story Preparation | 2 hrs | Write 12 – 15 STAR-L stories. Map to company principles. Practice out loud. |
| **7** | Mock Interviews + Integration | 2 – 3 hrs | 1 mock coding + 1 mock system design + 1 mock behavioural. Use Pramp, interviewing.io, or friends. Fix weak spots. |
| **8** | Polish + Rest | 1 – 2 hrs | Light review. Re-read notes. Revisit weak areas. Rest well before interview day. |

**Total investment**: ~120 – 160 hours over 8 weeks.

---

## 6. Key Differences: Big Tech vs. Mid-Size vs. Startup

| Dimension | Small Startup | Mid-Size Company | Big Tech |
|---|---|---|---|
| **Interview rounds** | 1 – 3 | 3 – 5 | 5 – 7 |
| **Coding bar** | Can you build? | Can you build well? | Can you solve algorithmic problems optimally under time pressure? |
| **System design** | Rare | Practical, product-focused | Large-scale, distributed, theory-heavy |
| **ML depth** | Applied | Applied + some fundamentals | Fundamentals + applied + research awareness |
| **Behavioural** | Light, culture-fit | Moderate, collaboration-focused | Heavy, leadership-principle-mapped, rubric-scored |
| **Preparation time** | 1 week | 2 weeks | 6 – 8 weeks |
| **Decision-maker** | Founder / CTO | Hiring manager | Hiring committee |
| **Compensation** | Variable, equity-heavy | Competitive, structured | Top-of-market, well-defined bands |
| **What they optimize for** | Delivery speed | Quality + growth potential | Scalable talent pipeline with a universal bar |
| **Your strategy** | Show you can ship | Show depth and collaboration | Pass a standardized bar across multiple dimensions |

---

## 7. Resources

### Coding
- **Neetcode 150** (neetcode.io) — The best curated problem list
- **Blind 75** — The original "essential problems" list
- **Leetcode Premium** — Frequency lists by company are valuable
- **Pramp / interviewing.io** — Free and paid mock interviews

### System Design
- **"Designing Machine Learning Systems"** by Chip Huyen — Essential reading
- **"System Design Interview"** by Alex Xu (Volume 1 & 2) — General system design bible
- **ML System Design Interview** by Khang Pham — ML-focused system design
- **ByteByteGo** (blog + YouTube) — Visual system design explanations

### ML / AI
- **Stanford CS229** (Machine Learning basics) — Free, comprehensive
- **Stanford CS224N** (NLP) — Free, great for Transformer understanding
- **Andrej Karpathy's YouTube** — Best explanations of LLMs and GPT
- **Hugging Face documentation** — Practical reference for models, tokenizers, and transformers
- **LangChain / LangGraph documentation** — Essential for agentic AI roles

### Behavioural
- **Amazon's 16 Leadership Principles** — Even if you're not interviewing at Amazon, these are the best framework for structuring behavioural stories
- **"Cracking the Coding Interview"** by Gayle McDowell — The behavioural section is underrated
- **Exponent** (YouTube + paid) — Mock interviews with real interviewers

---

## 8. Red Flags to Watch For

Even at Big Tech, evaluate whether the role is right for **you**:

- **Ice cream stand team**: A tiny team within a giant company that gets no resources or attention. You'll have the brand on your resume but limited scope.
- **Reorg risk**: The team was recently formed, or there are rumours of reorganization. Your role could disappear.
- **Misaligned level**: They want to down-level you to justify compensation. If you're clearly L5, don't accept L4 for "growth."
- **PIP culture**: Some orgs within Big Tech have aggressive performance management. Check Blind and Glassdoor for signals.
- **AI cosplay**: The team claims to do AI but is really just integrating APIs or running dashboards. Ask what the team actually builds.
- **Unrealistic expectations**: "Make our model 10x better in 6 months" with no data infrastructure.
- **Golden handcuffs**: The comp is incredible but the work is soul-crushing. Know what you're trading.

---

## 9. Negotiation Tips for Big Tech

Big Tech compensation is structured but **very negotiable**, especially for senior roles.

### Know the Components

| Component | What It Is | Negotiability |
|---|---|---|
| **Base salary** | Fixed cash compensation | Low — usually within a band for the level |
| **RSU / Stock** | Equity grant vesting over 4 years | High — this is the biggest lever |
| **Signing bonus** | One-time cash at start | High — used to bridge between current comp and first vest |
| **Annual bonus** | Performance-based cash (10 – 25% of base) | Low — formula-driven |
| **Level** | Your engineering level (L4, L5, etc.) | Medium — this is the highest-leverage negotiation if you have evidence |

### Tactics

1. **Never give a number first.** "I'm focused on finding the right role. I'd love to see your best offer first and we can go from there."
2. **Use competing offers.** This is the #1 lever. Even a smaller company's offer creates urgency.
3. **Negotiate the level, not just comp.** 1 level up means 30 – 50% more comp and compounds for your entire tenure.
4. **Focus on RSU.** "I'm excited about the role and the base works for me. Could we discuss the equity component? I'd ideally like to see [target]."
5. **Use signing bonus to bridge.** "I understand the RSU vests over 4 years. Could we add a Year 1 signing bonus to bridge the gap?"
6. **Get it in writing.** Verbal offers are not offers. Always get the full written offer with all components.
7. **Don't be afraid to push back.** Big Tech expects negotiation. The recruiter's first offer is almost never the best they can do.

---

## Key Takeaway

> Big Tech interviews test you across **multiple independent dimensions** with a **standardized bar**. You cannot wing it. Each round (coding, system design, ML depth, behavioural) requires dedicated, structured preparation. The bar is high, but it's also **learnable** — these are skill tests, not intelligence tests. The candidates who get offers are not the smartest in the room; they're the ones who prepared most deliberately.
>
> Your job is to prove: *"I meet the bar for this level across every dimension, and I'll raise the bar for the team once I'm there."*
