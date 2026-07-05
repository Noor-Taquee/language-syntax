# Python

**Contents**
- [File Name](#file-name)
- [Syntax](#syntax)
- [Keywords](#keywords)
- [Variables](#variables)
- [Primitive Data Types](#primitive-data-types)
  - [String](#string)
  - [Integer](#integer)
  - [Float](#float)
  - [Boolean](#boolean)
  - [None](#none)
- [Data Structures](#data-structures)
  - [Lists](#lists)
  - [Tuples](#tuples)
  - [Dictionaries](#dictionaries)
  - [Sets](#sets)
- [Conditionals](#conditionals)
  - [if](#if)
  - [elif](#elif)
  - [else](#else)
  - [Inline Usage](#inline-usage)
- [Loops](#loops)
  - [for](#for)
  - [while](#while)
- [Functions](#functions)
  - [Function Definition](#function-definition)
  - [Function Call](#function-call)
  - [Return](#return)
  - [Arguments](#arguments)
  - [Lambda](#lambda)
- [Python-Specific Features](#python-specific-features)
  - [F-Strings](#f-strings)
  - [Comprehensions](#comprehensions)

---

### File Name
Python source files typically use the `.py` extension.

- **Modules**
  - Module names are usually snake_case (for example, `my_module.py`).
- **Packages**
  - Package names are usually snake_case as well (for example, `my_package/`).
  - Traditional packages usually include an `__init__.py` file.
- **Type Files**
  - Type hint stub files typically use the `.pyi` extension.

---

### Syntax
Python uses indentation to define blocks instead of curly braces. A colon (`:`) starts a new block after statements such as `if`, `for`, `while`, `def`, and `class`.

Consistent indentation is required, and 4 spaces is the standard style.

```python
if is_ready:
    print("Ready")
```

---

### Keywords
Python has reserved keywords that cannot be used as identifiers.

Common keywords include:
- `False`
- `None`
- `True`
- `and`
- `as`
- `assert`
- `async`
- `await`
- `break`
- `class`
- `continue`
- `def`
- `del`
- `elif`
- `else`
- `except`
- `finally`
- `for`
- `from`
- `global`
- `if`
- `import`
- `in`
- `is`
- `lambda`
- `nonlocal`
- `not`
- `or`
- `pass`
- `raise`
- `return`
- `try`
- `while`
- `with`
- `yield`

---

### Variables
Variables are assigned using the `=` operator.
```python
num: int = 42
name: str = "John"
```

---

### Primitive Data Types
#### String
Type hint: `str`

Strings store text.
```python
word: str = "Hello!"
```

See also:
- [Strings](strings/README.md)

#### Integer
Type hint: `int`

Ints store Integers.
```python
num: int = 42
negative: int = -75
zero: int = 0
```

#### Float
Type hint: `float`

Floats store numbers with a decimal point.
```python
pi: float = 3.14
value: float = -2.5
zero: float = 0.0
```

#### Boolean
Type hint: `bool`

Booleans store `True` or `False`.
```python
is_true: bool = True
is_false: bool = False
```

#### None
`None` represents the absence of a value.
```python
none_value: None = None
```

---

### Data Structures
#### Lists
Lists are ordered, mutable collections.
```python
fruits: list[str] = ["apple", "banana", "cherry"]
```

#### Tuples
Tuples are ordered, immutable collections.
```python
point: tuple[int, int] = (10, 20)
```

#### Dictionaries
Dictionaries store key-value pairs.
```python
person: dict[str, str | int] = {
    "name": "John",
    "age": 30,
    "city": "New York",
}
```

#### Sets
Sets store unique values.
```python
unique_numbers: set[int] = {1, 2, 3}
```

---

### Conditionals
#### if
The `if` statement executes a block of code when a condition is `True`.
```python
if score >= 90:
    print("Excellent")
```

#### elif
The `elif` statement checks another condition if the previous one was `False`.
```python
if score >= 90:
    print("Excellent")
elif score >= 75:
    print("Pass")
```

#### else
The `else` statement executes when all previous conditions are `False`.
```python
if score >= 90:
    print("Excellent")
else:
    print("Keep trying")
```

#### Inline Usage
You can use an inline conditional expression when assigning or returning a value.
```python
result: str = "Pass" if score >= 75 else "Fail"
```

```python
def is_even(num: int) -> bool:
    return True if num % 2 == 0 else False
```

---

### Loops
#### for
`for` loops iterate over a sequence or iterable.
```python
for i in range(5):
    print(i)
```

```python
numbers: list[int] = [1, 2, 3, 4, 5]
for number in numbers:
    print(number)
```

#### while
`while` loops continue as long as a condition is `True`.
```python
count: int = 0
while count < 5:
    print(count)
    count += 1
```

---

### Functions
#### Function Definition
Use the `def` statement to define a function.
```python
def greet() -> None:
    print("Hello, World!")
```

#### Function Call
A function is called by its name followed by parentheses `()`.
```python
greet()
```

#### Return
Use `return` to return a value from a function.
```python
def greet() -> str:
    return "Hello, World!"
```

#### Arguments
Arguments are values passed to a function.

**Positional arguments**
```python
def greet(name: str, message: str) -> str:
    return f"{message}, {name}!"

greet("Alice", "Hello")
```

**Keyword arguments**
```python
def greet(name: str, message: str) -> str:
    return f"{message}, {name}!"

greet(message="Hello", name="Alice")
```

**Default arguments**
```python
def greet(name: str, message: str = "Hello") -> str:
    return f"{message}, {name}!"

greet("Alice")
```

**Variable-length arguments**
```python
def greet(*names: str) -> str:
    return f"Hello, {', '.join(names)}!"

greet("Alice", "Bob", "Charlie")
```

**Keyword-only arguments**
```python
def greet(*, name: str) -> str:
    return f"Hello, {name}!"

greet(name="Alice")
```

#### Lambda
A `lambda` expression defines an anonymous, single-expression function.
```python
from collections.abc import Callable

add: Callable[[int, int], int] = lambda x, y: x + y
```

```python
result = add(3, 5)
```

---

### Python-Specific Features
#### F-Strings
F-strings provide a concise way to embed expressions inside strings.
```python
name: str = "John"
age: int = 30
statement: str = f"My name is {name} and I am {age} years old."
```

#### Comprehensions
Comprehensions provide a compact way to build collections.
```python
squares: list[int] = [number * number for number in range(5)]
```
