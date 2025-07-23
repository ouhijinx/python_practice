Excellent — let’s dig into **Day 2: `*args`, `**kwargs`, and Unpacking**. This day builds your fluency with one of the most Pythonic ways to write flexible, reusable code. These concepts are essential for decorators, higher-order functions, and clean CLI tools.

---

## ✅ **Day 2: `*args`, `**kwargs`, and Unpacking**

### 🔍 What You’ll Learn

* Understand what `*args` and `**kwargs` actually represent
* Use them to build functions that handle flexible inputs
* Use unpacking (`*`, `**`) when *calling* functions
* Real-world use cases like logging, delegation, and adapter functions

---

### 🧠 Key Concepts

| Syntax         | Meaning                                        |
| -------------- | ---------------------------------------------- |
| `*args`        | A tuple of extra positional arguments          |
| `**kwargs`     | A dict of extra keyword arguments              |
| `*` (in call)  | Unpacks a list/tuple into positional arguments |
| `**` (in call) | Unpacks a dict into keyword arguments          |

---

### 🔧 Practice Tasks

#### \[ ] **Define a function that accepts `*args` and prints each argument**

```python
def show_args(*args):
    for i, arg in enumerate(args):
        print(f'arg[{i}]: {arg}')
```

#### \[ ] **Define a function that accepts `**kwargs` and prints keys + values**

```python
def show_kwargs(**kwargs):
    for key, value in kwargs.items():
        print(f'{key} = {value}')
```

#### \[ ] **Write a function that logs and forwards arguments to another function**

```python
def traced(func):
    def wrapper(*args, **kwargs):
        print(f'Calling {func.__name__} with args={args}, kwargs={kwargs}')
        return func(*args, **kwargs)
    return wrapper
```

Then test:

```python
@traced
def greet(name, greeting='Hello'):
    print(f'{greeting}, {name}!')

greet('Alice')
greet('Bob', greeting='Hi')
```

#### \[ ] **Call a function with unpacked args and kwargs**

```python
def example(a, b, c=0):
    print(f'{a=}, {b=}, {c=}')

args = (1, 2)
kwargs = {'c': 99}
example(*args, **kwargs)
```

---

### 🧪 Real-World Task (Optional)

* Pick a function from your **simulator** or **validator**
* Modify it to accept `*args` and `**kwargs`, or:
* Add a wrapper function that logs args and forwards them

---

### 📝 Notes Section

```text
- What patterns felt useful or clean?
- Any part of the unpacking behavior that surprised you?
- Did any of this simplify a real function you’ve written?
```

---

Let me know when you finish or if you’d like to explore:

* Partial functions and argument pre-binding (`functools.partial`)
* Argument validation and type checking
* How this connects directly to decorators (which you’ll revisit in Chapter 3)

Once you're ready, we'll move to **Day 3: Intro to Decorators**.
