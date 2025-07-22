# 🧭 Chapter 1: Foundations Reforged

**Goal:** Strengthen your comfort with Python's foundational mechanics — especially the ones you’ve touched but aren’t fully confident with. Build fluency with idiomatic constructs like comprehensions, argument unpacking, and decorators.

---

## ✅ Week Plan Overview

| Day | Focus                            | Estimated Time |
|-----|----------------------------------|----------------|
| Mon | Comprehensions Deep Dive         | 15–20 min      |
| Tue | `*args` / `**kwargs` + unpacking | 15–20 min      |
| Wed | Intro to Decorators              | 15–20 min      |
| Thu | Docstring Styles & Best Practices | 15–20 min     |
| Fri | Refactor a real script           | 20+ min        |
| 🛠 Weekend | Stretch goals or mini-project | Optional    |

---

## ✅ Day 1: Comprehensions (List, Dict, Set)

- [ ] Revisit list comprehensions  
- [ ] Add filters (`if`) and transformations  
- [ ] Translate 3 nested `for` loops to comprehensions  
- [ ] Try dict and set comprehensions  
- [ ] Rewrite one function in your `bundle builder` using a comprehension

### Example

```python
# From this:
results = []
for item in items:
    if item.is_valid():
        results.append(item.value)

# To this:
results = [item.value for item in items if item.is_valid()]
```

### Notes:


---

## ✅ Day 2: `*args`, `**kwargs`, and unpacking

- [ ] Review the difference between `*args` and `**kwargs`
- [ ] Use unpacking in a real function
- [ ] Pass a list or dict to a function using unpacking
- [ ] Write a function wrapper that passes through all args

### Example

```python
def log_args(*args, **kwargs):
    print(f'Positional: {args}')
    print(f'Keyword: {kwargs}')

log_args(1, 2, 3, a='x', b='y')
```

### Notes:


---

## ✅ Day 3: Decorator Basics

- [ ] Learn how to define a decorator manually
- [ ] Apply a decorator to an existing function
- [ ] Use `functools.wraps` to preserve docstrings
- [ ] Stretch: Create a decorator that times function execution

### Example

```python
from functools import wraps
from time import time

def timing_decorator(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        start = time()
        result = func(*args, **kwargs)
        print(f'{func.__name__} took {time() - start:.4f}s')
        return result
    return wrapper
```

### Notes:


---

## ✅ Day 4: Docstrings & Documentation Style

- [ ] Compare PEP 257, Google style, and NumPy style
- [ ] Add docstrings to 3 functions in an existing tool
- [ ] Use `pydoc` or your IDE to preview formatting
- [ ] Decide on a preferred style for your projects

### Example (Google style)

```python
def send_message(msg: str, timeout: int = 5) -> bool:
    """Send a message over the network.

    Args:
        msg: Message to be sent.
        timeout: Timeout in seconds.

    Returns:
        True if successful, False otherwise.
    """
```

### Notes:


---

## ✅ Day 5: Refactor From Real Code

- [ ] Choose one function from your validator or simulator tool
- [ ] Refactor it using:
  - List/dict/set comprehensions
  - Unpacking
  - A decorator (if it fits)
- [ ] Rewrite docstrings to use your chosen style
- [ ] Add type hints if you already know how (otherwise skip for now)

### Notes:


---

## 🛠️ Mini-Project: TOML Formatter & Field Normalizer

Build a CLI tool that:

1. Accepts a path to a TOML file or folder of TOML files
2. Loads the file(s), formats them to a canonical structure
3. Applies field normalization logic (e.g., lowercasing keys, fixing `_id` suffixes, etc.)

### Suggested Structure

```
project_root/
├── main.py
├── formatter/
│   ├── __init__.py
│   ├── loader.py
│   ├── normalizer.py
│   └── cli.py
└── tests/
    └── test_normalizer.py
```

### Features to Include

- [ ] CLI using `argparse` or `click`
- [ ] At least one list/dict comprehension
- [ ] At least one custom decorator (e.g. for timing or logging)
- [ ] Docstrings in consistent format
- [ ] Test stub (unit test or CLI usage validator)

---

## 🌱 Stretch Goals

- [ ] Learn about `dataclass` and use it to wrap TOML content
- [ ] Benchmark your script with `timeit`
- [ ] Add support for recursive directory scanning

---

## 🔁 End-of-Week Retrospective

**What felt easiest?**  
...

**What felt unclear or still shaky?**  
...

**Did anything from your real-world code become easier?**  
...

**What would you like Chapter 2 to reinforce or build on?**  
...
