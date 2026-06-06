## Questions 
- https://leetcode.com/problems/fruit-into-baskets?utm=codolio
- https://leetcode.com/problems/max-consecutive-ones-iii?utm=codolio
---
## Used For

- Longest subarray
    
- Shortest subarray
    
- Substring problems
    
- Continuous / consecutive elements
    

---

## Main Idea

Instead of checking all subarrays (`O(n²)`), maintain a moving window using two pointers.

---

## Window

```text
[i ............ j]
```

- `i` = left pointer
    
- `j` = right pointer
    

---

## General Pattern

1. Expand window using `j`
    
2. Add current element
    
3. Check if window becomes invalid
    
4. If invalid:
    
    - Shrink from left using `i`
        
5. Update answer
    

---

## Template

```python
i = 0

for j in range(n):

    # include nums[j]

    while invalid_condition:

        # remove nums[i]
        i += 1

    ans = max(ans, j - i + 1)
```

---

## Visualization

```text
nums = [1 2 3 4 5]
```

### Start

```text
i
j
1 2 3 4 5
```

### Expand j

```text
i     j
1 2 3 4 5
```

### Expand More

```text
i         j
1 2 3 4 5
```

### If Window Becomes Invalid

Move `i` forward.

```text
	 i     j
1 2 3 4 5
```

---

## Common Invalid Conditions

### 1. Max Consecutive Ones III

```python
zeros > k
```

### 2. Fruit Into Baskets

```python
distinct_elements > 2
```

### 3. Longest Substring Without Repeating Characters

```python
duplicate character exists
```

### 4. Minimum Size Subarray Sum

```python
sum >= target
```

---

## Types

### 1. Fixed Size Window

Window size always remains `k`.

**Example:**

- Maximum sum of subarray of size `k`
    

**Pattern:**

```python
while j - i + 1 > k:
    remove nums[i]
    i += 1
```

---

### 2. Dynamic Size Window

Window size changes dynamically.

**Examples:**

- Longest substring
    
- Fruit Into Baskets
    
- Max Consecutive Ones III
    

**Pattern:**

```python
while invalid:
    shrink window
```

---

## Key Observation

Sliding Window works when:

> If a window is invalid, making it larger will NOT fix it.

### Example

```python
zeros > k
```

Adding more elements will not reduce the number of zeros.

Therefore, we must shrink the window.

---

## Time Complexity

Both pointers move only forward.

```text
i -> moves at most n times
j -> moves at most n times
```

Total:

```text
O(n)
```

---

## Mental Model

```text
Expand -> Check -> Shrink
```

OR

```text
Grow Window

If Invalid:
    Reduce Window
```
---
### For Atmost and Atleast type of questions
[[Sliding Window atmost & atleast]]