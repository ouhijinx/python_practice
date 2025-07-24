# Chapter 2 - *args, **kwargs, and Unpacking

## Challenges

### 1. Build an Argument Logger

Write a function that accepts any number of positional and keyword arguments, and prints them in order.

```python
# Example call:
log_args(1, 'two', key='value', flag=True)

# Expected behavior:
# Positional: (1, 'two')
# Keyword: {'key': 'value', 'flag': True}
````

---

### 2. Forward Arguments to a Wrapped Function

Create a wrapper function `delegate` that takes another function and logs all `args` and `kwargs`, then calls the original function with the same arguments.

```python
# Example usage:
@delegate
def multiply(a, b=1):
    return a * b

# Call: multiply(4, b=3)
# Expected log: Calling multiply with args=(4,), kwargs={'b': 3}
# Should return: 12
```

---

### 3. Combine and Call with Unpacked Arguments

Define a function `merge_and_call(func, *args, **kwargs)` that calls `func` with unpacked `args` and `kwargs`.

```python
# Example target function:
def debug(a, b, c=0, verbose=False):
    print(a, b, c, verbose)

# Call:
args = [10, 20]
kw = {'c': 30, 'verbose': True}
merge_and_call(debug, *args, **kw)
```

---

### 4. Accept and Route Unknown Arguments

Define a function `adaptive_sum(*args, **kwargs)` that:

* Adds up all positional arguments
* Adds any keyword argument whose key starts with `'val'`

```python
adaptive_sum(1, 2, val1=3, val2=4, skip=100)
# Result should be: 1 + 2 + 3 + 4 = 10
```

---

## Hints

### 1: Build an Argument Logger

```python
def log_args(*args, **kwargs):
    print('Positional:', args)
    print('Keyword:', kwargs)
```

---

### 2: Forward Arguments to a Wrapped Function

Use a decorator pattern:

```python
def delegate(func):
    def wrapper(*args, **kwargs):
        print(f'Calling {func.__name__} with args={args}, kwargs={kwargs}')
        return func(*args, **kwargs)
    return wrapper
```

---

### 3: Combine and Call with Unpacked Arguments

Use unpacking syntax:

```python
def merge_and_call(func, *args, **kwargs):
    func(*args, **kwargs)
```

---

### 4: Accept and Route Unknown Arguments

Use filtering with `.startswith()`:

```python
total = sum(args) + sum(v for k, v in kwargs.items() if k.startswith('val'))
```

---

## Answers

### 1: Build an Argument Logger

```python
def log_args(*args, **kwargs):
    print(f'Positional: {args}')
    print(f'Keyword: {kwargs}')
```

---

### 2: Forward Arguments to a Wrapped Function

```python
# Paste your answer here
```

---

### 3: Combine and Call with Unpacked Arguments

```python
# Paste your answer here
```

---

### 4: Accept and Route Unknown Arguments

```python
# Paste your answer here
```
