# Chain-of-Thought Prompting

## Learning Objective

Chain-of-Thought (CoT) prompting encourages the AI to reason through a problem step by step before providing the final answer. This improves accuracy, especially for logical reasoning and problem-solving tasks.

---

# Prompt 1 – Mathematics

## Objective
Solve a percentage problem.

### Before Prompt
A shirt costs ₹1200 and is sold at a 15% discount. What is the final price?

### Before Output
₹1,020

Here's the math:

Discount amount = 15% of ₹1,200 = ₹180
Final price = ₹1,200 − ₹180 = ₹1,020

### Improved Prompt
Solve the following problem step by step and explain each calculation before giving the final answer.

Problem:
A shirt costs ₹1200 and is sold at a 15% discount. What is the final price?

### After Output
Step 1: Understand the problem
The shirt's original price (marked price) is ₹1200. A discount of 15% is applied, and we need to find the final selling price after the discount.

Step 2: Calculate the discount amount
Discount = 15% of ₹1200
= (15/100) × 1200
= 0.15 × 1200
= ₹180

Step 3: Subtract the discount from the original price
Final Price = Original Price − Discount
= ₹1200 − ₹180
= ₹1020

Final Answer: ₹1020

### Why the Improved Prompt is Better
- Encourages logical reasoning.
- Shows intermediate calculations.
- Makes the solution easier to understand.

---

# Prompt 2 – Logical Puzzle

## Objective
Solve a reasoning puzzle.

### Before Prompt
If all roses are flowers and some flowers fade quickly, can we conclude that all roses fade quickly?

### Before Output
No — that conclusion doesn't follow.

Here's why: "all roses are flowers" tells us roses are a subset of flowers. "Some flowers fade quickly" only tells us that part of the flower category fades quickly — it doesn't say which part. The roses could be entirely within the "fade quickly" portion, entirely outside it, or split between the two. The premises are consistent with all of these possibilities, so we can't pin down which one is true.

A concrete way to see this: suppose "flowers" = {roses, tulips, orchids}, and the flowers that fade quickly are just {tulips}. Both premises hold (all roses are flowers; some flowers — the tulips — fade quickly), but no rose fades quickly.

This is a classic syllogism error. The valid version would need a premise directly linking roses to fading, such as "all roses fade quickly" (making the conclusion trivial) or "some roses are flowers that fade quickly" — but that's not what "some flowers fade quickly" says.

### Improved Prompt
Think through the logic step by step before answering.

Question:
If all roses are flowers and some flowers fade quickly, can we conclude that all roses fade quickly?

Explain your reasoning clearly.

### After Output
No, we can't conclude that.

Why:

"All roses are flowers" tells us roses are a subset of flowers.
"Some flowers fade quickly" tells us there's an overlap between flowers and things-that-fade-quickly — but it doesn't say which flowers.

The flowers that fade quickly might be, say, tulips or lilies, with no roses among them at all. Or they might include some roses but not others. Or, in the best case for the conclusion, all the fast-fading flowers could happen to be roses — but "some flowers fade quickly" alone doesn't guarantee that either.

A concrete counterexample:
Suppose flowers = {rose, tulip, lily, daisy}, and only tulip and lily fade quickly.

All roses are flowers ✓
Some flowers fade quickly ✓ (tulip, lily)
But roses don't fade quickly at all — so "all roses fade quickly" is false.

The general principle: This is a classic syllogistic fallacy. From "All A are B" and "Some B are C," you cannot validly derive "All A are C" (or even "Some A are C"). The "some" statement doesn't specify which members of B have property C, so there's no guaranteed connection back to A. To conclude anything about roses fading, you'd need a premise that directly relates roses to fading — e.g., "some roses are flowers that fade quickly" or "all fast-fading flowers are roses."

### Why the Improved Prompt is Better
- Breaks the reasoning into steps.
- Reduces incorrect assumptions.

---

# Prompt 3 – Coding Logic

## Objective
Find the bug.

### Before Prompt
Find the mistake in this Python code.

def add(a,b):
return a+b

### Before Output
The mistake is indentation: the return statement isn't indented, so Python will raise an IndentationError (it expects an indented block after the def line's colon).

Fix:

python
def add(a, b):
    return a + b

Every line inside a function body needs to be indented (typically 4 spaces) relative to the def line.

### Improved Prompt
Analyze the following Python code step by step.

Identify:
- Syntax errors
- Why the error occurs
- Corrected code

Code:

def add(a,b):
return a+b

### After Output
Analysis

Code:

python
def add(a,b):
return a+b
Syntax Error
IndentationError: expected an indented block after function definition on line 1
Why It Occurs

In Python, indentation isn't just style — it's how the language knows which statements belong inside a block (like a function, loop, or if-statement). After a def line ending in :, Python expects the next line to be indented to show it's part of the function body.

Here, return a+b starts at the same column as def add(a,b):, so Python has no way to tell that return belongs inside add. It looks like a statement floating outside the function, right after a header that demands a body — hence the error.

Corrected Code
python
def add(a, b):
    return a + b

Changes made:

Indented return a + b with 4 spaces (Python's conventional indent size) so it's recognized as the function body.
Added spaces around operators/commas (a, b and a + b) — not required to fix the error, but follows PEP 8 style conventions for readability.
Quick Test
python
def add(a, b):
    return a + b

print(add(3, 5))  # Output: 8

This now runs without errors and correctly returns the sum of a and b.

### Why the Improved Prompt is Better
- Encourages systematic debugging.
- Explains the reasoning instead of only giving the answer.

---

# Prompt 4 – Decision Making

## Objective
Choose the best laptop.

### Before Prompt
Which laptop should I buy?

### Before Output
Identified need for clarifying questions about budget and preferences
Identified need for clarifying questions about budget and preferences
Happy to help you figure this out! A few quick questions will narrow it down a lot.

### Improved Prompt
Think step by step before recommending a laptop.

Requirements:
- Budget: ₹60,000
- Purpose: Programming and AI/ML
- Good battery life
- Minimum 16 GB RAM

Finally recommend the best option with reasons.

### After Output
Evaluated laptop specifications and identified GPU limitations for ML tasks
Evaluated laptop specifications and identified GPU limitations for ML tasks
Here's my step-by-step reasoning, then the pick.

Step 1: What actually matters for programming + AI/ML at this budget

At ₹60,000, you won't get a discrete GPU worth using for training models — that's just physics of the price point. So the real requirements become:

A strong CPU (H-series, not weak U-series) for compiling code, running Docker containers, and local Jupyter/VS Code work
16GB RAM minimum, ideally DDR4/DDR5 dual-channel, since ML libraries (pandas, numpy, PyTorch on CPU) are memory-hungry
Fast NVMe SSD (512GB+) for datasets, virtual envs, Docker images
Good battery for a full day of class/work without hunting for outlets
For actual model training, you'll lean on Google Colab / Kaggle / cloud GPUs — the laptop's job is to run your editor, local testing, and lightweight inference smoothly
Step 2: Screening the current market (July 2026)

8GB RAM options (Acer Aspire 3 i3, Infinix XBOOK) — ruled out immediately, below your minimum
Gaming laptops with GPUs (Asus TUF, Acer Nitro, MSI Thin) — all sit at ₹65,000–86,000, over budget, and their GPUs (RTX 3050/4GB) are too weak for serious ML training anyway, so you'd be overpaying for a GPU you won't really use
U-series budget laptops (base Vivobook, base Aspire) — cheaper but noticeably slower at compiling/building
H-series options at ~₹55,000-58,000 — this is the sweet spot
Step 3: The best-fit candidates

Two stand out with the i5-13420H (H-series, genuinely faster for builds than typical budget chips):

Lenovo IdeaPad Slim 3 — metal body, 16GB RAM, 512GB SSD, WUXGA IPS (1920x1200) display, backlit keyboard, IR camera, ~1.6kg, fast charging (80% in ~60 min), 1-year accidental damage protection its metal body, IR camera for Windows Hello, accidental damage protection, and Lenovo's keyboard comfort make it a top pick for professionals, and the 16GB RAM + 512GB SSD combo handles everyday developer workflows smoothly, with rapid 80% charge in about 60 minutes. 
IP With Ease
IP With Ease
Acer Aspire Lite with the same i5-13420H — delivers faster compile times than most competitors in this range, since the H-series chip is a meaningful upgrade for developers running heavy build tools, but with a more plastic build. 
IP With Ease
Step 4: Verdict

Recommended: Lenovo IdeaPad Slim 3 (i5-13420H, 16GB RAM, 512GB SSD) — ~₹55,000–58,000
Why this one wins for you:

H-series CPU — noticeably faster than typical U-series budget chips for compiling, Docker, and running local Jupyter kernels
16GB RAM, 512GB NVMe SSD — comfortably handles VS Code + Docker + multiple browser tabs + virtual environments simultaneously
Battery + fast charging — 80% charge in ~60 minutes is genuinely useful if you're moving between library/class/hostel
1920x1200 (16:10) display — extra vertical space matters a lot for reading code and long terminal/Jupyter sessions
Metal build + 1-year accidental damage protection — better long-term durability than the typical plastic budget chassis
Leaves ~₹2,000–5,000 of your budget for a RAM/storage-friendly cloud subscription (Colab Pro) for the actual heavy ML training — a smarter use of money than an underpowered gaming GPU
One honest caveat: no laptop at ₹60,000 will meaningfully train deep learning models locally. Budget mentally for Colab/Kaggle notebooks (free GPU/TPU) for training runs — the laptop is for writing code, prototyping small models, and everything else.

Want me to pull up current live listings/prices for this model near you, or compare it side-by-side against the Acer Aspire Lite in more detail?

### Why the Improved Prompt is Better
- Includes decision criteria.
- Explains the recommendation logically.

---

# Prompt 5 – Study Planning

## Objective
Create a study plan.

### Before Prompt
Make a study plan.

### Before Output
Identified need for clarification on subject matter
What are you studying for? That'll help me build something useful.

### Improved Prompt
Think step by step before creating the schedule.

Prepare a 7-day study plan for a B.Tech student learning Data Structures and Algorithms.

Requirements:
- 2 hours daily
- Include revision
- Include coding practice
- Reserve the last day for mock tests

### After Output
Here's a structured 7-day DSA study plan, designed around 2 hours/day with steady progression, built-in revision, and a mock-test capstone.

Planning logic: Days 1–3 build core linear structures (the foundation everything else leans on), Day 4 shifts to non-linear structures (trees/graphs need the linear basics solidified first), Day 5 covers algorithmic techniques (recursion/DP/greedy — these need data structures already in place), Day 6 is dedicated revision + weak-area cleanup before testing, and Day 7 is pure mock-test simulation.

7-Day DSA Study Plan (2 hrs/day)
Day 1 – Arrays & Strings
45 min – Concepts: array operations, time/space complexity, two-pointer technique, sliding window
60 min – Coding practice: 4–5 problems (e.g., reverse array, max subarray sum, string reversal, two-sum)
15 min – Quick recap notes on patterns used
Day 2 – Linked Lists
40 min – Concepts: singly/doubly linked lists, insertion/deletion, cycle detection (Floyd's)
60 min – Coding practice: reverse a linked list, detect cycle, merge two sorted lists
20 min – Revision: skim Day 1 problems, redo one from memory
Day 3 – Stacks & Queues
40 min – Concepts: stack/queue operations, applications (balanced parentheses, monotonic stack)
60 min – Coding practice: valid parentheses, next greater element, implement queue using stacks
20 min – Revision: Day 2 linked list problems, timed redo
Day 4 – Trees & Graphs
50 min – Concepts: binary trees, BST, tree traversals (in/pre/post-order), graph representations, BFS/DFS
60 min – Coding practice: level-order traversal, height of tree, number of islands (BFS/DFS)
10 min – Revision: flashcard-style recall of Day 3 concepts
Day 5 – Recursion, Backtracking, DP & Greedy
50 min – Concepts: recursion tree, backtracking basics, DP fundamentals (memoization vs tabulation), greedy strategy
60 min – Coding practice: fibonacci (DP), subsets/permutations (backtracking), coin change, activity selection
10 min – Revision: Day 4 tree/graph traversal, quick redo
Day 6 – Full Revision Day
60 min – Revisit all topics (Day 1–5): review notes, redo 1 problem per topic without looking at solutions first
45 min – Solve 3–4 mixed/random problems (pick topics you're weakest in)
15 min – Prepare a personal cheat sheet: time complexities, common patterns, edge cases
Day 7 – Mock Test Day
90 min – Take a timed mock test (simulate real exam/interview conditions — 4–5 mixed problems across all topics)
30 min – Detailed review: analyze mistakes, note time-management issues, identify recurring gaps

Tips to get the most out of this:

Use a platform like LeetCode, GeeksforGeeks, or HackerRank consistently so you can track progress
Don't skip the daily revision blocks — spaced repetition is what makes this stick
On Day 7, treat it exactly like a real test: no peeking at solutions mid-attempt

Want me to turn this into a downloadable tracker (Word or Excel) with checkboxes for each day, or suggest specific problem sets from LeetCode/GfG for each topic?
### Why the Improved Prompt is Better 
- Considers multiple constraints.
- Produces a structured and practical plan.

---

## Conclusion

Chain-of-Thought prompting improves reasoning quality by encouraging the AI to solve problems in a logical, step-by-step manner before producing the final answer.
