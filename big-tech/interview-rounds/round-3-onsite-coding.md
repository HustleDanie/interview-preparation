# Round 3: Onsite / Virtual Loop — Coding Sessions — How to Pass Them Excellently

> **Format**: Video call with shared editor or whiteboard (1 – 2 sessions back-to-back) | **Duration**: 45 – 60 min each | **Interviewer**: Senior engineers (L5 – L7), different interviewer per session

---

## What This Round Actually Is

The onsite coding round is the **highest-weight technical evaluation** in the Big Tech loop. If the phone screen checked that you can code, the onsite checks that you can **code excellently under pressure, at the bar expected for your target level, across multiple interviewers**.

Key differences from the phone screen:

| Dimension | Phone Screen | Onsite Coding |
|---|---|---|
| **Difficulty** | Medium | Medium-hard to Hard |
| **Number of problems** | 1 – 2 | 1 – 2 per session (2 – 4 total across sessions) |
| **Sessions** | 1 | 1 – 2 separate sessions, different interviewers |
| **Expectation** | Get to a working solution | Optimal solution + clean code + edge cases + follow-ups |
| **Follow-ups** | Rare | Very common ("Now modify this to handle X") |
| **Scoring** | Pass/Fail | Formal rubric: Strong No Hire → Strong Hire |
| **Level signals** | Basic | They're specifically evaluating against your target level's coding bar |

### What They're Evaluating (Formal Rubric)

Big Tech interviewers submit **structured scorecards** with ratings on:

| Criteria | Weight | L3 – L4 Bar | L5 Bar | L6+ Bar |
|---|---|---|---|---|
| **Problem-solving** | 🔴 Critical | Solves medium problems with minimal hints | Solves medium-hard independently, tackles hard with structure | Solves hard problems, navigates ambiguity |
| **Algorithm choice** | 🔴 Critical | Identifies the right approach | Compares approaches, explains trade-offs, picks optimal | Sees novel approaches, discusses lower bounds |
| **Code correctness** | 🔴 Critical | Working solution | Working optimal solution, handles edge cases | Handles all edge cases, considers concurrent/distributed concerns |
| **Code quality** | 🟡 High | Readable, reasonable structure | Clean abstractions, modular, well-named | Production-quality, extensible, defensive |
| **Communication** | 🟡 High | Explains approach before coding | Drives the conversation, teaches the interviewer | Articulates architectural thinking, trade-offs at scale |
| **Testing & validation** | 🟡 High | Tests with given examples | Proactively derives edge cases and tests them | Discusses testing strategy, property-based testing, invariants |
| **Follow-up handling** | 🟡 High | Adapts code with guidance | Modifies approach independently, refactors cleanly | Anticipates follow-ups, design is already extensible |

---

## The Problem Types You'll Face

### Category 1: Pure Algorithmic (Most Common at Google, Meta, Amazon)

These are classic Leetcode problems — the same patterns you practiced, but at higher difficulty.

**Frequency by topic (for AI roles):**

| Topic | Likelihood | Difficulty Level | Why It's Asked |
|---|---|---|---|
| **Arrays & Strings** | Very high | Medium → Hard | Foundation. Tests basic problem-solving. |
| **Trees & Graphs** | Very high | Medium → Hard | Models many AI data structures (dependency graphs, hierarchical data, DAGs) |
| **Dynamic Programming** | High | Medium-hard → Hard | Tests ability to decompose complex optimization problems |
| **Hash Maps** | High | Medium | Fast lookups, grouping, counting — core to data processing |
| **BFS / DFS** | High | Medium → Hard | Traversal = foundation of many AI systems (agent search, graph processing) |
| **Binary Search** | Medium-high | Medium | Search on answer space, optimization |
| **Heaps / Priority Queues** | Medium | Medium | Top-K, ranking, scheduling — relevant to ML pipelines |
| **Sliding Window** | Medium | Medium → Hard | Streaming data, time-series, sequence processing |
| **Backtracking** | Medium | Medium-hard → Hard | Constraint satisfaction — relevant to agent planning |
| **Tries** | Lower | Medium | Autocomplete, prefix matching |
| **Union Find** | Lower | Medium | Clustering, connected components |

### Category 2: Applied / Practical (More Common at OpenAI, Anthropic, Apple)

These test **real-world engineering skills** alongside algorithmic thinking.

| Problem Type | Example | What It Tests |
|---|---|---|
| **Data processing** | Parse a log file, extract structured data, compute aggregates | Python fluency, data manipulation, file I/O |
| **API design** | Design and implement a class/interface for a caching system | OOP, abstraction, API design thinking |
| **Pipeline implementation** | Build a mini data pipeline (ingest → transform → output) | Systems thinking, error handling, modularity |
| **Agent-related** | Implement a retry mechanism, tool dispatcher, state machine | Practical AI engineering, error recovery patterns |
| **Evaluation** | Write a function to compute metrics (precision, recall, BLEU, etc.) | ML knowledge + coding ability |
| **Concurrency (rare)** | Producer-consumer, rate limiter, thread-safe cache | Systems depth, especially for AI Systems Engineer roles |

### Category 3: Follow-Up Extensions (The Level Differentiator)

After you solve the initial problem, expect 1 – 2 follow-ups that change the constraints:

| Follow-Up Type | Example | What It Tests |
|---|---|---|
| **Scale** | "What if the input doesn't fit in memory?" | Distributed/streaming thinking |
| **Constraint change** | "Now the data is unsorted" or "Now allow duplicates" | Adaptability, algorithmic flexibility |
| **Optimization** | "Can you do this in O(1) space?" | Deep algorithmic knowledge |
| **Generalization** | "Extend this to K dimensions" or "Handle N types" | Abstraction, generalization ability |
| **Production** | "How would you handle errors?" or "What if the input is malformed?" | Engineering maturity |

> **Key insight**: Follow-ups are where L5+ candidates differentiate themselves. Your initial code should be **modular enough** that extending it doesn't require a rewrite.

---

## The Execution Framework: 45-Minute Session

### For a Single Problem (Common at Google)

| Step | Time | What to Do | What to Say |
|---|---|---|---|
| **1. Understand** | 3 min | Read carefully. Repeat back. Ask clarifying questions. | *"Let me make sure I understand. We're given [X]. We need to return [Y]. Can I assume [constraint]? What about [edge case]?"* |
| **2. Examples** | 2 min | Trace through the given examples. Add your own if helpful. | *"Tracing through example 1: [walkthrough]. This makes sense. Let me also consider [edge case example]."* |
| **3. Approach discussion** | 5 – 7 min | **This is the most important step.** Discuss 2 approaches: brute force → optimal. Explain the key insight. State complexity. | *"Brute force would be [X] at O(n²). But I notice [key insight], which lets us use [technique] for O(n). The trade-off is O(n) extra space."* |
| **4. Get confirmation** | 30 sec | Explicitly ask the interviewer to confirm. | *"I'll go ahead and implement the [optimal approach]. Sound good?"* |
| **5. Code** | 15 – 18 min | Write clean, well-structured code. Narrate every decision. | *"I'll start with [setup]. Here I'm handling [case]. This helper function encapsulates [logic]..."* |
| **6. Dry-run** | 4 – 5 min | Trace through your code with Example 1 step by step. Then trace an edge case. | *"Let me trace through: i=0, value=3, so we... result becomes... Final output: [X]. Matches expected. ✓"* |
| **7. Edge cases** | 2 – 3 min | List and handle edge cases proactively. | *"Edge cases to consider: empty input → returns [X]. Single element → [Y]. All duplicates → [Z]. Let me verify..."* |
| **8. Complexity** | 1 min | State time and space complexity with reasoning. | *"Time: O(n log n) — dominated by the sort. Space: O(n) for the auxiliary array. Best possible is Ω(n) since we must read all input, so this is near-optimal."* |
| **9. Follow-up** | remaining | Handle the follow-up if given. | *"Interesting. If the data is streaming, I'd switch to [modified approach] because..."* |

### For Two Problems (Common at Meta)

| Problem | Time | Strategy |
|---|---|---|
| **Problem 1** (easier) | 18 – 20 min | Move fast. Skip detailed brute-force discussion — go to optimal quickly. Test briefly. Leave time. |
| **Transition** | 1 min | Interviewer introduces problem 2. |
| **Problem 2** (harder) | 22 – 25 min | This is where your score is differentiated. Take more time on approach discussion. |

> **Pro tip for two-problem sessions**: If you finish Problem 1 in 15 min, don't milk it. Say: *"I'm confident this is correct and optimal. Happy to move on."* The interviewer will appreciate your efficiency.

---

## What to Do When You're Stuck (Advanced Strategies)

### The Structured Recovery Protocol

Below, follow a deliberate protocol. Do NOT stare at the screen.

**Phase 1 — Reframe (0 – 90 seconds):**
1. Re-read the problem statement. You may have missed a constraint.
2. Look at the examples again. The answer often hints at the approach.
3. Ask yourself: "What is this problem REALLY asking?" Strip away the story and identify the core algorithmic problem.

**Phase 2 — Pattern match (90 seconds – 3 min):**
Mentally run through the patterns:
- "Is this a graph problem?" (Things connected to other things → yes.)
- "Is there an ordering constraint?" (Topological sort.)
- "Am I looking for a subarray/substring?" (Sliding window.)
- "Am I making choices to maximize/minimize?" (DP or greedy.)
- "Do I need fast lookups?" (Hash map.)
- "Does sorting help?" (Two pointers after sort, binary search.)

**Phase 3 — Work a small example by hand (3 – 5 min):**
Take the smallest non-trivial example and solve it manually. Write out each step. Often, the algorithm **emerges from the manual process**.

> *"Let me work through a concrete example to find the pattern..."*

**Phase 4 — Ask for a hint (5+ min stuck):**
There is NO SHAME in asking for a hint. Interviewers expect it on hard problems. The scoring impact is small compared to not solving the problem.

> *"I can see that [what you understand]. I'm stuck on [specific issue]. Could you give me a nudge on the right direction for [specific part]?"*

### Common Misconceptions About Getting Stuck

| Misconception | Reality |
|---|---|
| "Asking for a hint means I failed" | Most rubrics dock very little for 1 hint. Not solving it docks a lot. |
| "I should try every approach silently" | Silent struggle for 10 min = Strong No Hire. Verbalized struggle for 5 min + hint = Lean Hire. |
| "I need to get the optimal on the first try" | Starting with brute force, then optimizing, is the EXPECTED path. |
| "If I can't solve it, I should keep trying until time runs out" | If you're 10+ min stuck, code SOMETHING — even brute force. A working suboptimal solution > no solution. |

---

## Code Quality Standards at Big Tech

Big Tech interviewers care about code quality — it's a separate rubric dimension.

### What "Clean Code" Looks Like in an Interview

```python
# ❌ BAD — This gets you a lower code quality score
def f(a, t):
    d = {}
    for i in range(len(a)):
        if t - a[i] in d:
            return [d[t - a[i]], i]
        d[a[i]] = i

# ✅ GOOD — This gets you a high code quality score
def two_sum(nums: List[int], target: int) -> List[int]:
    """Find two indices whose values sum to target."""
    seen = {}  # value -> index

    for index, num in enumerate(nums):
        complement = target - num
        if complement in seen:
            return [seen[complement], index]
        seen[num] = index

    return []  # No valid pair found
```

### Code Quality Checklist

| Aspect | What to Do |
|---|---|
| **Variable names** | `left`, `right`, `max_length`, `seen`, `queue` — NOT `l`, `r`, `m`, `s`, `q` |
| **Function names** | `find_shortest_path()`, `is_valid()` — descriptive of purpose |
| **Type hints** | Add them for the main function: `def solve(nums: List[int]) -> int` |
| **Brief comments** | One-liner for non-obvious logic: `# Expand window until constraint violated` |
| **Helper functions** | Extract repeated logic into small, named functions |
| **No dead code** | Don't leave commented-out attempts in your final solution |
| **Consistent style** | Pick snake_case for Python. Be consistent throughout. |
| **Edge case handling** | Add an early return for trivial cases: `if not nums: return 0` |

---

## Role-Specific Considerations

### AI Engineer
- Expect **more applied problems** in one session and more algorithmic in the other.
- Applied problems may involve: string/text processing, data transformation, token counting, building simple caches.
- The interviewer may ask: "How would this code integrate into a larger ML pipeline?" — think about data flow.

### AI Systems Engineer
- Expect **systems-oriented algorithmic problems**: LRU cache, rate limiter, thread-safe data structures.
- May get **concurrency questions**: producer-consumer, reader-writer locks, async patterns.
- Problems may involve: memory-efficient data structures, streaming algorithms, efficient I/O.
- The interviewer may ask about: "What happens at 10x scale?" or "How would you parallelize this?"

### AI Agentic Engineer
- May get **practical agent-style problems**: implement a simple state machine, dispatch tool calls based on a schema, parse structured outputs.
- Expect problems involving: recursive structures, tree/graph traversal (agents explore decision trees), error handling and retry logic.
- The interviewer may frame problems as: "Design a function that acts as [agent component]."

---

## Practice Problems (Curated for AI Roles at Big Tech)

### Must-Solve Before Interview (20 Problems)

| # | Problem | Difficulty | Pattern | Why It Matters |
|---|---|---|---|---|
| 1 | Two Sum | Easy | Hash Map | Warm-up, but you need to solve it in 3 min |
| 2 | Best Time to Buy and Sell Stock | Easy | Sliding Window / Greedy | Pattern recognition |
| 3 | Valid Parentheses | Easy | Stack | Basic but expected to be instant |
| 4 | Merge Intervals | Medium | Sorting + Sweep | Very common in system/data pipeline contexts |
| 5 | Group Anagrams | Medium | Hash Map | String manipulation + grouping |
| 6 | 3Sum | Medium | Two Pointers | Classic, tests duplicate handling |
| 7 | Longest Substring Without Repeating Characters | Medium | Sliding Window | String + set |
| 8 | Course Schedule | Medium | Graph (Topological Sort) | Dependency resolution — core to ML pipelines |
| 9 | Number of Islands | Medium | BFS/DFS on Grid | Fundamental graph traversal |
| 10 | Binary Tree Level Order Traversal | Medium | BFS | Tree fundamentals |
| 11 | LRU Cache | Medium | Hash Map + DLL | Must-know for Systems Engineer |
| 12 | Word Search | Medium | Backtracking | Constraint exploration |
| 13 | Coin Change | Medium | DP | Classic DP pattern |
| 14 | Kth Largest Element | Medium | Heap / Quickselect | Top-K is everywhere in ML ranking |
| 15 | Word Break | Medium | DP | Tokenization / segmentation analogy |
| 16 | Serialize and Deserialize Binary Tree | Hard | Tree + Design | Data serialization skill |
| 17 | Trapping Rain Water | Hard | Two Pointers / Stack | Classic hard, tests insight |
| 18 | Median from Data Stream | Hard | Two Heaps | Streaming statistics — relevant to ML monitoring |
| 19 | Alien Dictionary | Hard | Graph (Topological Sort) | Ordering / dependency inference |
| 20 | Design an Iterator for Nested Lists | Medium | Stack + Design | Iterator pattern — common in data pipelines |

### Company-Specific Practice

| Company | Extra Focus | Practice List |
|---|---|---|
| **Google** | Graph problems, DP, string manipulation | Neetcode 150 + Google-tagged problems on Leetcode |
| **Meta** | Arrays, trees, graphs — speed is key | Blind 75 + Meta-tagged problems. Practice 2-problem sessions. |
| **Amazon** | String/array manipulation, OOP-style problems | Amazon OA practice + Leetcode Amazon-tagged |
| **Apple** | Applied + algorithmic mix | Focus on clean design patterns + medium problems |
| **Microsoft** | Medium-level problems, possibly with design component | Leetcode Microsoft-tagged + system design basics |

---

## Day-of Strategy: Surviving Multiple Coding Sessions

If your onsite includes **2 coding sessions** back-to-back (common at Google, Meta, Amazon):

### Energy Management
- Sessions are typically separated by 5 – 15 min breaks. **USE THEM.** Stand up, drink water, clear your mind.
- Don't dwell on the previous session. You don't know how you scored — interviewers submit independent scorecards.
- Each session has a fresh interviewer who knows nothing about how your other sessions went.

### Mental Resets Between Sessions
1. **3 deep breaths.** Physiologically calms the nervous system.
2. **Recall your execution framework.** Understand → Examples → Approach → Confirm → Code → Test → Complexity.
3. **Remind yourself**: "I've practiced this. I know the patterns. I just need to think out loud and stay structured."

### If Session 1 Went Badly
- It doesn't mean you've failed. Big Tech hiring committees review **all scorecards holistically**.
- One "Strong Hire" on coding can outweigh one "Lean No Hire" on coding.
- Mentally reset. Session 2 is a **fresh opportunity**.

---

## Quick Reference: What Outstanding Looks Like

| Dimension | Outstanding Performance |
|---|---|
| **Speed** | Identifies the key insight within 2 min. Starts coding within 5 min. Finishes with 10+ min to spare. |
| **Communication** | The interviewer feels like they're watching a masterclass. Every step is narrated with reasoning. |
| **Code** | Production-quality: type hints, docstring, helper functions, defensive checks. Could be committed to a real repo. |
| **Edge cases** | Lists 3 – 5 edge cases proactively. Handles all of them. Explains why each matters. |
| **Follow-ups** | Anticipates the follow-up. Code was already designed to be extensible. Modifies with minimal changes. |
| **Complexity analysis** | States complexity, explains it, discusses lower bounds, mentions amortized analysis when relevant. |
| **Composure** | Even when faced with a problem they haven't seen, they stay calm, structured, and methodical. The interviewer notes: "Excellent problem-solving process." |
