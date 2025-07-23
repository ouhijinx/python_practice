# Chapter 1 - List Comprehension Exercises

## Challenges

### 1. Filter words that start with 'A'

Keep only the words from this list that start with the letter 'A':

```python
words = ['apple', 'banana', 'avocado', 'cherry', 'apricot']
# Your goal: ['apple', 'avocado', 'apricot']
````

---

### 2. Perfect Squares Only

Keep only the numbers that are perfect squares:

```python
nums = [1, 2, 3, 4, 5, 9, 16, 18]
# Your goal: [1, 4, 9, 16]
```

---

### 3. Replace Negatives with Zero

Replace any negative number with 0; otherwise, keep the number:

```python
nums = [4, -2, 7, -1, 0]
# Your goal: [4, 0, 7, 0, 0]
```

---

### 4. Label as 'even' or 'odd'

Label each number as either 'even' or 'odd':

```python
nums = [1, 2, 3, 4]
# Your goal: ['odd', 'even', 'odd', 'even']
```

---

### 5. Matrix Product Triples

Goal: Translate the following 3 nested for loops into a single list comprehension.

```python
result = []
for x in range(2):
    for y in range(3):
        for z in range(4):
            result.append((x, y, z, x * y * z))
```

Write this using a list comprehension that produces:

```python
[(0, 0, 0, 0), (0, 0, 1, 0), ..., (1, 2, 3, 6)]
```

Each tuple contains `(x, y, z, x * y * z)` for all combinations of:

* `x` in `range(2)`
* `y` in `range(3)`
* `z` in `range(4)`


## Challenges

### 6. Filter and Reformat Dictionary Pairs

Given a list of `(key, value)` pairs, keep only those keys that start with `'x'` and reformat them into a dictionary with the key uppercased and the value squared.

```python
pairs = [('xray', 2), ('alpha', 3), ('xeno', 4), ('bravo', 5)]
# Your goal: {'XRAY': 4, 'XENO': 16}
```

---

## Hints

### 1: Filter words that start with 'A'

Fill this in:

```python
result = [________ for word in words if ___________]
```

---

### 2: Perfect Squares Only

Use the modulo operator to check if the square root of a number has no decimal part.

```python
result = [________ for x in nums if x**0.5 % 1 == 0]
```

---

### 3: Replace Negatives with Zero

Use a ternary expression:

```python
result = [________ if __________ else 0 for x in nums]
```

---

### 4: Label as 'even' or 'odd'

Use the modulo operator inside a ternary:

```python
result = [________ if x % 2 == 0 else 'odd' for x in nums]
```

---

### 5: Matrix Product Triples

The loop nesting order in a comprehension mirrors the loop structure, like this:

```python
[expression for x in ... for y in ... for z in ...]
```

---

## 6: Filter and Reformat Dictionary Pairs

You will need:

- A for loop that unpacks each (k, v) in pairs
- An if filter on whether k starts with 'x'
- A key transformation using k.upper()
- A value transformation using v ** 2

```python
result = {________: ________ for k, v in pairs if __________}
```

---

## Answers

### 1: Filter words that start with 'A'

```python
result = [word for word in words if word.startswith('a')]
```

---

### 2. Perfect Squares Only

```python
result = [x for x in nums if x**0.5 % 1 == 0]
```

---

### 3. Replace Negatives with Zero

```python
result = [x if x >= 0 else 0 for x in nums]
```

---

### 4: Label as 'even' or 'odd'

```python
result = ['even' if x % 2 == 0 else 'odd' for x in nums]
```

---

### 5: Matrix Product Triples

```python
result = [(x, y, z, x * y * z) for x in range(2) for y in range(3) for z in range(4)]
```

### 6: Filter and Reformat Dictionary Pairs

```python
Paste answer here
```
