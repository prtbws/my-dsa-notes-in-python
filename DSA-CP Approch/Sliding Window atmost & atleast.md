## Questions
- https://leetcode.com/problems/binary-subarrays-with-sum?utm=codolio
- https://leetcode.com/problems/number-of-substrings-containing-all-three-characters?utm=codolio
---
## At Most K

After making the window valid, every subarray inside the window is valid.

### Valid Starts

```text
i, i+1, ..., j
```

### Count

```python
ans += j - i + 1
```

### Examples

- At most K distinct elements
    
- At most K odd numbers
    
- Binary subarrays with sum ≤ K
    
- Nice subarrays (At Most version)
    

---

## Contains All / At Least

Shrink the window until it becomes invalid.

Now `i` points to the first invalid start.

### Valid Starts

```text
0, 1, 2, ..., i-1
```

### Count

```python
ans += i
```

### Examples

- Substrings containing `a`, `b`, and `c`
    
- Substrings containing all vowels
    
- Minimum window style problems
    

---

## Exactly K

Cannot be counted directly with a normal sliding window.

### Formula

```python
Exactly(K) = AtMost(K) - AtMost(K - 1)
```

### Examples

- Exactly K odd numbers
    
- Exactly K distinct elements
    
- Binary subarrays with sum = K
    
- Count Number of Nice Subarrays
    

---

## Summary Table

|Type|Count Formula|
|---|---|
|At Most K|`ans += j - i + 1`|
|Contains All / At Least|`ans += i`|
|Exactly K|`AtMost(K) - AtMost(K - 1)`|

---

## Recognition Pattern

### At Most K

- Constraint says **at most**
    
- Window remains valid after shrinking
    

```python
while condition > k:
    shrink()

ans += right - left + 1
```

### Contains All / At Least

- Need all required characters/elements
    
- Shrink until invalid
    

```python
while valid:
    shrink()

ans += left
```

### Exactly K

```python
return atMost(k) - atMost(k - 1)
```

