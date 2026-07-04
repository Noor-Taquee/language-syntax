## File Name
Python file names end with `.py` extension.

## Basic Syntax

### Keywords
There are 26 keywords in Python.
<details>
  <summary>Click to expand</summary>
  - `as`
  - `assert`
  - `break`
  - `continue`
  - `class`
  - `def`
  - `del`
  - `else`
  - `False`
  - `finally`
  - `for`
  - `from`
  - `global`
  - `if`
  - `import`
  - `while`
  - `lambda`
  - `None`
  - `nonlocal`
  - `pass`
  - `raise`
  - `return`
  - `True`
  - `try`
  - `except`
  - `with`
  - `yield`
</details>

### Literals

#### str
A string literal is a sequence of characters enclosed in single (`'`) or double (`"`) quotes.
  ```python
  word: str = "Hello!"
  ```

#### int
An integer literal is a whole number without a decimal point.
  ```python
  num: int = 42
  num_2: int = -75
  zero: int = 0
  ```

#### float
A floating-point literal is a number with a decimal point.
  ```python
  pi: float = 3.14
  num: float = -2.5
  zero: float = 0.0
  ```

#### bool
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

### Conditionals
#### if
The `if` statement is used to execute a block of code if a condition is `True`.
  ```python
  if 5 == 2+3:
    print("True")
  ```

#### `elif`
The `elif` statement is used to execute a block of code if the condition is `False` and another condition is `True`.
  ```python
  if 5 == 2+3:
    print("True")

  elif 5 != 2+3:
    print("False")
  ```

#### `else`
The `else` statement is used to execute a block of code if all previous conditions are `False`.
  ```python
  if 5 == 2+3:
    print("True")
  else:
    print("False")
  ```

#### `if` expression
The `if` expression is used to evaluate a condition and return a value based on whether the condition is `True` or `False`.
  ```python
  true: bool = True
  value: int = 10 if true else 5
  ```


### Functions
#### `def`
The `def` statement is used to define a function.
  ```python
  def greet(name: str) -> str:
    return f"Hello, {name}!"
  ```

#### `return`
The `return` statement is used to return a value from a function.
  ```python
  def greet(name: str) -> str:
    return f"Hello, {name}!"
  ```

#### `lambda`
The `lambda` statement is used to define an anonymous function.
  ```python
  add: Callable[[int, int], int] = lambda x, y: x + y
  ```
