# Round 2: Phone Screen / Technical Screen — How to Pass It Excellently

> **Format**: Video call with screen share (code editor or CoderPad/HackerRank) | **Duration**: 45 – 60 min | **Interviewer**: Engineer on the team (L5 – L6 typically)

---

## What This Round Actually Is

The phone screen is the **technical filter before the onsite loop**. Big Tech companies use this round to avoid wasting 4 – 5 hours of interviewer time on a candidate who can't pass a coding bar. Roughly **50 – 60% of candidates are eliminated here**.

This round is a **hybrid**: part algorithmic coding, part technical discussion. The balance depends on the company and role:

| Company | Phone Screen Format |
|---|---|
| **Google** | 1 Leetcode-style problem (medium-hard). 45 min in Google Docs or an internal tool. |
| **Meta** | 1 – 2 Leetcode problems (medium). 45 min in CoderPad. Focus on getting optimal solutions with clean code. |
| **Amazon** | 1 – 2 coding problems + some LP questions woven in. 60 min. Online assessment (OA) may precede this. |
| **Apple** | More team-specific. Could be Leetcode OR applied coding. 45 – 60 min. |
| **Microsoft** | 1 – 2 coding problems. 45 – 60 min. Sometimes includes a brief design component. |
| **OpenAI / Anthropic** | More applied than algorithmic. Might involve building something practical (API, pipeline, agent logic). 60 min. |
| **NVIDIA** | Systems-oriented coding. May include C++ or CUDA-style problems alongside Python. 60 min. |

### What They're Evaluating

| Criteria | Weight | What They Want to See |
|---|---|---|
| **Problem-solving** | 🔴 Critical | Can you decompose a problem, identify the approach, and work toward a solution systematically? |
| **Correct solution** | 🔴 Critical | Does your code produce the correct output? Does it handle edge cases? |
| **Optimal complexity** | 🔴 Critical (Big Tech) | At Big Tech, they expect the **optimal solution**, not just a working one. Know your complexities. |
| **Communication** | 🔴 Critical | Can you articulate your thinking? Can you explain your approach before coding? |
| **Code quality** | 🟡 High | Clean, readable, well-structured code. Meaningful variable names. |
| **Speed** | 🟡 High | You need to solve the problem within the time limit. Practice timed sessions. |
| **ML/AI awareness** | 🟢 Medium | For AI roles, the interviewer may ask 5 – 10 min of ML questions at the end. |

> **Key difference from mid-size**: Mid-size companies often give applied problems (build an API, design a pipeline). Big Tech phone screens are **almost always Leetcode-style algorithmic problems**. The exceptions are OpenAI, Anthropic, and some Apple teams that lean more applied.

---

## Before the Screen (3 – 7 Days of Focused Prep)

### 1. Know Your Coding Environment

The phone screen uses a **shared online editor** — not your local IDE. This means:
- **No autocomplete** (or very limited).
- **No import auto-suggestions** — you need to know `from collections import defaultdict, Counter, deque` by heart.
- **No local testing** — you may need to dry-run your code manually.
- **Limited debugging** — no breakpoints, no print-and-inspect cycles.

**Common platforms:**
| Platform | Companies That Use It |
|---|---|
| CoderPad | Meta, many others |
| HackerRank | Amazon OA, various |
| Google Docs | Google (yes, plain Google Docs — no syntax highlighting) |
| CodeSignal | Various, especially for OAs |
| Company-internal tool | Apple, some Microsoft teams |

**Practice tip**: Do at least 5 – 10 practice problems in the actual platform you'll use. If it's Google Docs, practice writing code without syntax highlighting. If it's CoderPad, familiarize yourself with the interface.

### 2. Master the Core Patterns

For a 45 – 60 minute phone screen, the interviewer will give you **1 – 2 problems**, typically medium difficulty (occasionally medium-hard). You need pattern recognition to solve them quickly.

**The 12 must-know patterns:**

| # | Pattern | When to Use It | Typical Problem |
|---|---|---|---|
| 1 | **Two Pointers** | Sorted arrays, pair finding, palindromes | Two Sum II, Container With Most Water |
| 2 | **Sliding Window** | Subarrays/substrings with constraints | Longest Substring Without Repeat, Min Window Substring |
| 3 | **Hash Map / Set** | Frequency counting, grouping, lookups | Two Sum, Group Anagrams, Subarray Sum Equals K |
| 4 | **Binary Search** | Sorted data, search on answer space | Search Rotated Array, Koko Eating Bananas |
| 5 | **BFS / DFS** | Trees, graphs, matrices | Number of Islands, Clone Graph, Binary Tree Level Order |
| 6 | **Stack** | Matching brackets, monotonic sequences | Valid Parentheses, Daily Temperatures, Next Greater Element |
| 7 | **Heap / Priority Queue** | Top-K, merge-K, streaming median | Kth Largest Element, Merge K Sorted Lists |
| 8 | **Dynamic Programming** | Optimization, counting, decision problems | Climbing Stairs, Coin Change, Longest Common Subsequence |
| 9 | **Backtracking** | Permutations, combinations, constraint satisfaction | Subsets, Combination Sum, N-Queens |
| 10 | **Linked List** | In-place modifications, cycle detection | Reverse Linked List, Linked List Cycle, Merge Two |
| 11 | **Tree Traversal** | BST operations, path problems | Validate BST, Lowest Common Ancestor, Max Path Sum |
| 12 | **Graph Algorithms** | Shortest path, topological sort, connectivity | Course Schedule, Dijkstra's, Union Find applications |

### 3. Prepare Your Common Imports and Templates

Have these in muscle memory (Python example):

```python
# Essential imports — know these by heart
from collections import defaultdict, Counter, deque, OrderedDict
from heapq import heappush, heappop, heapify
from typing import List, Optional, Dict, Tuple, Set
from itertools import combinations, permutations, product
from functools import lru_cache
from bisect import bisect_left, bisect_right
import math

# Common data structures
# Stack: use list -> append(), pop()
# Queue: use deque -> append(), popleft()
# Min-heap: use heapq (default is min-heap)
# Max-heap: negate values -> heappush(h, -val)

# TreeNode definition (know this by heart)
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

# ListNode definition
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

# Graph — adjacency list
graph = defaultdict(list)
for u, v in edges:
    graph[u].append(v)
    graph[v].append(u)  # undirected
```

### 4. Practice the 25-Minute Execution Framework

For a single problem in a 45-min slot (the most common format):

| Step | Time | What to Do | What to Say |
|---|---|---|---|
| **1. Understand** | 3 min | Read the problem. Repeat it back to the interviewer. Ask clarifying questions. | *"So to make sure I understand — we're given [X] and need to return [Y]. Can I assume [constraint]?"* |
| **2. Examples** | 2 min | Walk through 1 – 2 examples by hand on the scratchpad. | *"Let me trace through this example to make sure I understand..."* |
| **3. Approach** | 4 – 5 min | State your approach BEFORE coding. Discuss complexity. If you see brute force and optimal, mention both. | *"My first thought is [brute force] which would be O(n²). But I think we can do better with [optimal approach] using [data structure/technique], which would give us O(n)."* |
| **4. Confirm** | 1 min | Get the interviewer's buy-in before coding. | *"Does that approach sound reasonable? I'll go ahead and implement it."* |
| **5. Code** | 12 – 15 min | Write clean, readable code. Narrate as you go. | *"I'll start by initializing... then I'll iterate... here I'm checking the edge case..."* |
| **6. Test** | 3 – 5 min | Dry-run your code with the given example. Check an edge case. | *"Let me trace through with example 1... [step through]. Now let me check the empty input case..."* |
| **7. Optimize** | 2 – 3 min | Discuss final time/space complexity. Mention possible optimizations. | *"This runs in O(n log n) time and O(n) space. We could optimize space to O(1) by [method] if needed."* |

**For a two-problem format** (Meta-style, 45 min):
- Problem 1 (easier): 15 – 18 min. Move quickly. Get to optimal fast.
- Problem 2 (harder): 22 – 25 min. This is where they differentiate candidates.

---

## During the Screen

### The Typical 45 – 60 Minute Flow

| Time | Phase | What Happens |
|---|---|---|
| 0 – 3 min | **Introduction** | Interviewer introduces themselves, brief pleasantries. |
| 3 – 5 min | **Context** | Interviewer may ask "Tell me briefly what you're working on" or jump straight to the problem. |
| 5 – 40 min | **Coding** | 1 – 2 algorithmic problems. This is the core of the round. |
| 40 – 50 min | **ML/AI questions** (role-dependent) | For AI roles, the interviewer may spend the last 10 min asking ML/AI questions. |
| 50 – 55 min | **Your questions** | 1 – 2 questions about the team or role. |
| 55 – 60 min | **Wrap-up** | Interviewer explains next steps. |

### Coding: What to Do When You're Stuck

Getting stuck is normal — even expected on harder problems. What matters is **how you handle it**.

**Tier 1 — Pause and think out loud (0 – 2 min stuck):**
> *"Let me step back and think about this differently. The constraint is [X], and I need [Y]. What data structures would help me get [Y] efficiently?"*

**Tier 2 — Simplify the problem (2 – 4 min stuck):**
> *"Let me think about a simpler version of this problem first. If the input were sorted / if there were no duplicates / if n were small, I would..."*

**Tier 3 — Verbalize and engage the interviewer (4+ min stuck):**
> *"I'm seeing the challenge here is [specific issue]. My instinct is to try [approach], but I'm not sure it handles [case]. Could you confirm whether [assumption] is correct?"*

**Rules when stuck:**
- **NEVER go silent.** The interviewer cannot give you a hint if they don't know where you're stuck.
- **Start with brute force.** A working O(n²) solution scores far higher than no solution.
- **Ask for one small hint.** It's better to solve the problem with a hint than to not solve it. Most rubrics docked only slightly for hints.
- **Show your thinking.** Even if you can't solve it, demonstrating structured thinking earns partial credit.

### ML/AI Questions at the End

For AI roles, many Big Tech phone screens include **5 – 10 minutes of ML questions** after the coding problem. These are not deep-dive questions — they're **breadth checks**.

**Common questions:**

| Category | Example Questions |
|---|---|
| **ML Basics** | "What's the difference between L1 and L2 regularization?" / "Explain bias-variance trade-off." |
| **Deep Learning** | "How does attention work in Transformers?" / "What's the vanishing gradient problem?" |
| **LLMs** | "How does pre-training differ from fine-tuning?" / "What is RLHF?" |
| **Applied** | "How would you evaluate a classification model?" / "Your model has high precision but low recall — what does that tell you?" |
| **Systems** | "How would you serve a model with low latency?" / "What's the difference between online and batch inference?" |

**How to answer:**
- Keep answers to **30 – 60 seconds** each. They're checking breadth, not depth.
- If asked something you're not sure about, say: *"I'm less familiar with that specific area, but my understanding is..."* — partial knowledge beats silence.
- For AI Engineer and AI Agentic Engineer roles, expect more LLM/applied questions.
- For AI Systems Engineer roles, expect more infrastructure/systems questions.

---

## Problem Walkthroughs: What Excellent Looks Like

### Example 1: Medium Array Problem

**Problem**: "Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`."

**Excellent response:**

> *"To clarify — can I assume there's exactly one solution, and I can't use the same element twice? Great."*
>
> *"My brute force would be checking all pairs — O(n²) time, O(1) space. But I can optimize this using a hash map: as I iterate, I store each number's index, and for each new number I check if `target - num` already exists in the map. That gives me O(n) time, O(n) space."*
>
> *"Shall I code the optimal approach? Okay."*

```python
def twoSum(nums: List[int], target: int) -> List[int]:
    seen = {}  # value -> index
    for i, num in enumerate(nums):
        complement = target - num
        if complement in seen:
            return [seen[complement], i]
        seen[num] = i
    return []  # problem guarantees a solution, but defensive
```

> *"Let me trace through: nums = [2, 7, 11, 15], target = 9.*
> *i=0, num=2, complement=7, seen={} → not found, add {2:0}.*
> *i=1, num=7, complement=2, seen={2:0} → found! Return [0, 1]. ✓"*
>
> *"Edge cases: duplicate values like [3, 3], target 6 — this works because we check before adding. Empty array returns []. Time: O(n), space: O(n). This is optimal."*

### Example 2: Medium Graph Problem

**Problem**: "Given a list of course prerequisites, determine if it's possible to finish all courses." (Course Schedule — Leetcode 207)

**Excellent response:**

> *"This is a cycle detection problem in a directed graph. Each course is a node, each prerequisite is a directed edge. If there's a cycle, we can't finish all courses."*
>
> *"I can solve this with topological sort using Kahn's algorithm (BFS-based). Build an adjacency list and in-degree count. Start BFS from nodes with in-degree 0. If we process all nodes, no cycle exists."*
>
> *"Time: O(V + E) where V is courses and E is prerequisites. Space: O(V + E) for the graph."*

```python
def canFinish(numCourses: int, prerequisites: List[List[int]]) -> bool:
    graph = defaultdict(list)
    in_degree = [0] * numCourses

    for course, prereq in prerequisites:
        graph[prereq].append(course)
        in_degree[course] += 1

    # Start with courses that have no prerequisites
    queue = deque([i for i in range(numCourses) if in_degree[i] == 0])
    completed = 0

    while queue:
        node = queue.popleft()
        completed += 1
        for neighbor in graph[node]:
            in_degree[neighbor] -= 1
            if in_degree[neighbor] == 0:
                queue.append(neighbor)

    return completed == numCourses
```

> *"Tracing through: 4 courses, prereqs [[1,0],[2,0],[3,1],[3,2]]. Graph: 0→[1,2], 1→[3], 2→[3]. In-degree: [0,1,1,2]. Start with course 0. Process 0 → in-degree of 1 and 2 drop to 0 → process 1 → in-degree of 3 drops to 1 → process 2 → in-degree of 3 drops to 0 → process 3. Completed = 4 = numCourses → True. ✓"*

---

## What Separates Pass from Strong Pass

The phone screen score is typically: **Strong No Hire / No Hire / Lean Hire / Hire / Strong Hire**.

| Signal | Hire (Pass) | Strong Hire (Excellent) |
|---|---|---|
| **Approach** | Identifies a correct approach after some exploration | Immediately recognizes the pattern and converges on optimal |
| **Communication** | Explains approach before coding | Proactively discusses trade-offs, mentions alternatives, explains why one approach is better |
| **Code** | Correct, working solution | Clean, elegant, Pythonic/idiomatic code with meaningful names |
| **Complexity** | States time/space complexity | Explains complexity with reasoning, discusses lower bounds |
| **Edge cases** | Handles them when prompted | Proactively identifies and handles edge cases without prompting |
| **Speed** | Solves 1 problem comfortably within time | Solves 1 problem quickly, has time for follow-ups or optimizations |
| **Getting stuck** | Recovers with a hint | Rarely gets stuck; if so, articulates exactly where they're blocked |
| **ML questions** | Answers basics correctly | Shows depth beyond what's asked, connects concepts to practical experience |

---

## Common Mistakes That Kill Your Chances

| Mistake | Why It's Fatal | What to Do Instead |
|---|---|---|
| **Coding without discussing approach** | Interviewer can't help or course-correct. No credit for thinking. | Always explain your approach first. Get buy-in. |
| **Going silent while thinking** | Interviewer assumes you're totally stuck. Can't give hints. | Think out loud. Always narrate. |
| **Jumping to the optimal solution without discussing brute force** | Looks like pattern matching without understanding. Misses partial credit if you can't get to optimal. | Mention brute force first, then explain how to optimize. |
| **Ignoring edge cases** | Empty input, single element, duplicates, negative numbers — these are in the rubric. | Proactively test edge cases before declaring "done." |
| **Messy code with single-letter variables** | Hard to read, easy to bug, impossible for the interviewer to follow. | Use descriptive names. `seen`, `left_ptr`, `max_count` — not `x`, `i`, `d`. |
| **Not asking clarifying questions** | You might solve the wrong problem or miss a constraint. | Always ask: input size, types, constraints, expected output format. |
| **Running out of time** | You solved 80% but never got a complete solution. 80% = no pass. | Practice timed sessions. Know when to switch from perfect to done. |
| **Arguing with the interviewer** | Even if you're right, it creates a bad interpersonal signal. | If the interviewer suggests a direction, engage with it: "That's interesting, let me think about how that changes the approach..." |

---

## Company-Specific Preparation Tips

### Google
- Uses **Google Docs** — practice coding without syntax highlighting.
- Often gives **one medium-hard problem**. Expects optimal solution with discussion of alternatives.
- May ask you to modify or extend the algorithm (follow-up questions).
- Interviewer typically stays silent and observes. You need to **drive the conversation**.

### Meta
- Uses **CoderPad**. Typically **2 problems in 45 min** (first easy-medium, second medium-hard).
- Speed matters more than at Google. Practice solving problems in 15 – 20 min each.
- Interviewer will often ask: "Can you optimize this?" — always be ready with the improvement.
- Common problem types: arrays, strings, trees, graphs.

### Amazon
- Often preceded by an **Online Assessment (OA)** — 2 problems, 90 min, on HackerRank/CodeSignal.
- Phone screen includes **LP-style questions** woven into the technical conversation.
- Common to hear: "Tell me about a time you solved an ambiguous problem" between coding questions.
- Interviewer evaluates both technical skill AND cultural fit simultaneously.

### Apple
- More **team-specific** than other FAANG. The problems may relate to the team's domain.
- May include **applied coding** rather than pure algorithms (e.g., implement a simple data pipeline, parse structured data).
- Interviewer is often the direct manager — this is more like a "working session" than an exam.

### Microsoft
- Typically **1 – 2 problems**, medium difficulty. Uses a shared editor.
- May include a brief **system design or architecture discussion** (5 – 10 min).
- Interviewers tend to be more collaborative — they'll guide you more than Google or Meta.
- The "as appropriate" format means one interviewer may have final say on proceed/no-proceed.

### OpenAI / Anthropic
- More **applied than algorithmic**. Expect problems like:
  - Build a function that processes LLM outputs.
  - Implement a retry mechanism with exponential backoff.
  - Design a simple evaluation harness.
  - Parse and transform structured/semi-structured data.
- May ask about **AI safety, alignment, or responsible development** — have thoughtful opinions.
- Code quality and practical engineering skills matter more than algorithms.

### NVIDIA
- Expect **systems-level coding**: memory management, concurrency, low-level optimization.
- May include **C++ alongside Python**.
- Common topics: parallel processing, GPU-aware algorithms, efficient data structures.
- May ask about performance optimization techniques (vectorization, memory hierarchy, cache behaviour).

---

## Quick Reference: Day-of Checklist

- [ ] Quiet space, good internet, camera on (if video).
- [ ] The coding platform is tested and working (log in early).
- [ ] Phone/laptop on "Do Not Disturb."
- [ ] Water and a clock visible.
- [ ] Scrap paper or a separate text file open for brainstorming.
- [ ] Common imports memorized (Python: `collections`, `heapq`, `typing`).
- [ ] Your 25-minute execution framework internalized.
- [ ] 1 – 2 questions ready for the interviewer.
- [ ] Mindset: "I will think out loud for the entire 45 minutes."

---

## Post-Screen: What Happens Next

| Outcome | What Happens | Timeline |
|---|---|---|
| **Pass** | Recruiter contacts you to schedule the onsite/virtual loop (3 – 6 rounds in one day). | 3 – 10 business days |
| **Borderline** | Recruiter may schedule an additional phone screen with a different interviewer. | 5 – 14 business days |
| **Fail** | Recruiter sends a rejection email. Some companies have a cooldown period (6 – 12 months). | 5 – 14 business days |

> **If you pass**: Immediately shift to **onsite preparation** — system design, ML deep-dive, and behavioural. The coding bar at the onsite is higher than the phone screen.
