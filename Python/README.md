# Python

**Contents**
- [File Name](#file-name)
- [Keywords](#keywords)
- [Variables](#variables)
- [Literals - Built-in Types](#literals)
  - [strings](#strings)
  - [integers](#integers)
  - [floating point numbers](#floating-point-numbers)
  - [boolean](#boolean)
  - [None](#none)
- [Conditionals](#conditionals)
  - [if](#if)
  - [elif](#elif)
  - [else](#else)
  - [in-line uses](#in-line-uses)
- [Loops](#loops)
  - [for](#for)
  - [while](#while)
- [Functions](#functions)
  - [Function](#function)
    - [Function Definition](#function-definition)
    - [Function Call](#function-call)
    - [Return](#return)
    - [Arguments](#arguments)
  - [Lambda](#lambda)

### File Name
Python file names end with `.py` extension.
- **Modules**
  - Module names are snake_case (e.g. `my_module.py`).
- **Packages**
  - Package names are snake_case as well (e.g. `my_package/`).
  - Packages have a `__init__.py` file in their root directory, which is used to initialize the package.
- **Type Files**
  - Type hint files end with `.pyi` extension (e.g. `my_module.pyi`).

---

### Keywords
There are **26** keywords in Python.
- `as`
- `assert`
- `break`
- `class`
- `continue`
- `def`
- `del`
- `else`
- `except`
- `False`
- `finally`
- `for`
- `from`
- `global`
- `if`
- `import`
- `lambda`
- `None`
- `nonlocal`
- `pass`
- `raise`
- `return`
- `True`
- `try`
- `while`
- `with`
- `yield`

---

### Variables
Variables are used to store values in Python. They are declared using the `=` operator.
```python
num: int = 42
name: str = "John"
```

---

### Literals

#### strings
type hint: `str`
A string literal is a sequence of characters enclosed in single (`'`) or double (`"`) quotes.
```python
word: str = "Hello!"
```

**triple quotes**: Triple quotes (`'''` or `"""`) allow you to use multi-line string literals.
```python
multi_line: str = """This is a
multi-line string."""
```

**f-strings**: The `f` prefix before the string literal allows you to use formatted string literals.
```python
name: str = "John"
age: int = 30
statement: str = f"My name is {name} and I am {age} years old."
```

**raw strings**: The `r` prefix before the string literal allows you to use raw string literals.
```python
path: str = r"C:\Users\John\Documents\file.txt"
```

#### integers
type hint: `int`
An integer literal is a whole number without a decimal point.
```python
num: int = 42
num_2: int = -75
zero: int = 0
```

#### floating-point numbers
type hint: `float`
A floating-point literal is a number with a decimal point.
```python
pi: float = 3.14
num: float = -2.5
zero: float = 0.0
```

#### boolean
type hint: `bool`
A boolean literal is `True` or `False`.
```python
is_true: bool = True
is_false: bool = False
```

#### None
A `None` literal represents the absence of a value.
```python
none_value: None = None
```

---

### Conditionals
#### if
The `if` statement is used to execute a block of code if a condition is `True`.
```python
if 5 == 2+3:
  print("True")
```

#### elif
The `elif` statement is used to execute a block of code if the condition is `True` and condition just before it is `False`.
```python
if 5 == 2+3:
  print("True")
elif 5 != 2+3:
  print("False")
elif 5 < 2+3:
  print("Less than")
```

#### else
The `else` statement is used to execute a block of code if all previous conditions are `False`.
```python
if 5 == 2+3:
  print("True")
else:
  print("False")
```

#### inline uses
When assigning a value based on a condition, you can use an `if`-`else` expression.
```python
true: bool = True
value: int = 10 if true else 5
```
When returning a value based on a condition, you can use an `if`-`else` expression.
```python
def is_even(num: int) -> bool:
  return True if num % 2 == 0 else False
```

---

### Loops
#### for
The `for` loop is used to iterate over a sequence.
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
The `while` loop is used to execute a block of code while a condition is `True`.
```python
while 5 > 2:
  print("True")
```

---

### Callables

#### Function

##### function definition
- The `def` statement is used to define a function.
```python
def greet() -> None:
  print("Hello, World!")
```

##### function call
- A function is called by its name followed by parentheses `()`.
- Arguments are passed to a function by position or by name.
```python
greet()
```

##### return
- The `return` statement is used to return a value from a function.
```python
def greet() -> str:
  return "Hello, World!"
```

##### Arguments
Arguments are variables that are passed to a function.

- **Positional arguments**
  - Arguments are passed to a function in the order they are defined.
  - Omitting an argument raises a `TypeError`.
```python
def greet(name: str, message: str) -> str:
  return f"{message}, {name}!"

greet("Alice", "Hello")
```

- **Keyword arguments**
  - Arguments are passed to a function by name.
  - Omitting a keyword argument raises a `TypeError`.
```python
def greet(name: str, message: str) -> str:
  return f"{message}, {name}!"

greet(message="Hello", name="Alice")
```

- **Default arguments**
  - Arguments that have a default value and can be omitted when calling the function.
  - Default arguments are defined by assigning a value to a parameter in the function definition.
  - Default arguments must be defined after non-default arguments.
```python
def greet(name: str, message: str = "World") -> str:
  return f"{message}, {name}!"

greet("Alice")
```

- **Variable-length arguments**
  - Arguments that are passed to a function as a tuple of values.
  - Variable-length arguments are defined by using `*` before the parameter name in the function definition.
```python
def greet(*names: str) -> str:
  return f"Hello, {', '.join(names)}!"

greet("Alice", "Bob", "Charlie")
```

- **Keyword-only arguments**
  - Arguments that must be passed by keyword and cannot be passed by position.
  - Keyword-only arguments are defined by using `*` before the parameter name in the function definition.
```python
def greet(*, name: str) -> str:
  return f"Hello, {name}!"

greet(name="Alice")
```

#### lambda
The `lambda` statement is used to define an anonymous, single-expression function.

##### definition

A `lambda` function is defined using the `lambda` keyword followed by a comma-separated list of parameters and a colon `:` followed by an expression.

```python
add: Callable[[int, int], int] = lambda x, y: x + y
```

##### call

A `lambda` function is called by its name followed by parentheses `()` with the arguments passed to it.

```python
result = add(3, 5)
```

---
