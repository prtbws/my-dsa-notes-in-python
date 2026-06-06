# Understanding Problem Constraints in Competitive Programming

A guide inspired by the classic Codeforces blog by eanacra.

---

## Why Constraints Matter

One of the most important skills in Competitive Programming is identifying the expected algorithm simply by looking at the problem constraints.

Before writing any code, always check:

* Maximum value of `n`
* Number of test cases
* Time limit
* Memory limit

The constraints often reveal the intended time complexity of the solution.

---

## Common Constraint → Complexity Mapping

| Maximum N  | Typical Complexity   |
| ---------- | -------------------- |
| `n ≤ 12`   | `O(n!)`              |
| `n ≤ 25`   | `O(2^n)`             |
| `n ≤ 100`  | `O(n^4)`             |
| `n ≤ 500`  | `O(n^3)`             |
| `n ≤ 10^4` | `O(n^2)`             |
| `n ≤ 10^6` | `O(n log n)`         |
| `n ≤ 10^8` | `O(n)`               |
| `n > 10^8` | `O(log n)` or `O(1)` |

---

## Typical Algorithms for Each Complexity

### O(n!)

Used when:

* Generating all permutations
* Brute force over every arrangement

Example:

```python
from itertools import permutations

for p in permutations(arr):
    pass
```

---

### O(2^n)

Used when:

* Enumerating subsets
* Bitmask DP
* Meet-in-the-middle techniques

Example:

```python
for mask in range(1 << n):
    pass
```

---

### O(n³)

Used when:

* Floyd-Warshall
* Triple nested loops
* Small graph problems

Example:

```python
for i in range(n):
    for j in range(n):
        for k in range(n):
            pass
```

---

### O(n²)

Used when:

* Double loops
* Basic Dynamic Programming
* Brute force pair checking

Example:

```python
for i in range(n):
    for j in range(i + 1, n):
        pass
```

---

### O(n log n)

Used when:

* Sorting
* Binary Search
* Segment Trees
* Fenwick Trees

Example:

```python
arr.sort()
```

---

### O(n)

Used when:

* Prefix sums
* Sliding window
* Two pointers
* Linear scans

Example:

```python
mx = max(arr)
```

---

### O(log n)

Used when:

* Binary Search
* GCD
* Fast Exponentiation

Example:

```python
while l <= r:
    mid = (l + r) // 2
```

---

### O(1)

Used when:

* Mathematical formulas
* Direct computation
* Precomputed answers

Example:

```python
sum_n = n * (n + 1) // 2
```

---

## How to Use Constraints During Contests

### Step 1

Read the constraints before reading the entire statement.

### Step 2

Estimate the maximum operations allowed.

A rough rule:

```text
10^8 operations ≈ 1 second
```

### Step 3

Find the largest complexity that fits.

Example:

```text
n = 200000
```

Possible:

* O(n)
* O(n log n)

Impossible:

* O(n²)

---

## Examples

### Example 1

```text
n ≤ 10^9
```

Expected:

* Binary Search
* Mathematics
* Logarithmic solutions

---

### Example 2

```text
n ≤ 100000
```

Expected:

* Sorting
* Two Pointers
* Greedy
* O(n log n)

---

### Example 3

```text
n ≤ 20
```

Expected:

* Bitmasking
* Subset Enumeration
* Meet-in-the-Middle

---

## Important Warning

Constraint analysis is only a guideline.

Some problems intentionally have:

* Non-obvious solutions
* Hidden optimizations
* Mathematical tricks
* Special observations

Therefore:

> Constraints help narrow the search space, but they do not guarantee the exact solution.

Always combine:

* Constraint analysis
* Pattern recognition
* Algorithm knowledge
* Problem observations

---

## Competitive Programming Workflow

```text
Read Problem
      ↓
Check Constraints
      ↓
Estimate Complexity
      ↓
Identify Candidate Algorithms
      ↓
Observe Patterns
      ↓
Implement
      ↓
Test
```

---

## Credits

This note is heavily inspired by the classic Codeforces blog:

**"How to determine the solution of a problem by looking at its constraints?"** by eanacra on Codeforces. The original article explains how problem constraints can often be used to infer the expected algorithmic complexity of a solution.

Original article:

[Codeforces Blog by eanacra](https://codeforces.com/blog/eanacra?utm_source=chatgpt.com)

All credit for the core idea belongs to the original author.
