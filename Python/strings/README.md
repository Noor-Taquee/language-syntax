# Python Strings

**Contents**
- [What a Python string is](#what-a-python-string-is)
- [String literal forms](#string-literal-forms)
  - [Single-quoted and double-quoted strings](#single-quoted-and-double-quoted-strings)
  - [Triple-quoted strings](#triple-quoted-strings)
  - [F-strings](#f-strings)
  - [Raw strings](#raw-strings)
  - [Raw f-strings](#raw-f-strings)
  - [Legacy unicode prefix](#legacy-unicode-prefix)
- [Escaping characters](#escaping-characters)
- [Indexing and slicing](#indexing-and-slicing)
- [Concatenation and repetition](#concatenation-and-repetition)
- [Useful string operations](#useful-string-operations)
- [String methods](#string-methods)
  - [Case conversion methods](#case-conversion-methods)
  - [Search and replace methods](#search-and-replace-methods)
  - [Split and join methods](#split-and-join-methods)
  - [Trim and removal methods](#trim-and-removal-methods)
  - [Alignment and padding methods](#alignment-and-padding-methods)
  - [Boolean test methods](#boolean-test-methods)
  - [Formatting, encoding, and translation methods](#formatting-encoding-and-translation-methods)
- [Notes](#notes)

---

## What a Python string is
Python has one built-in text string type: `str`.

```python
name: str = "Alice"
```

Even though people often say “string types”, Python text strings are all the same `str` type. What changes is the **literal form** used to write them.

`bytes` values such as `b"abc"` are **not** strings; they use the `bytes` type.

---

## String literal forms

### Single-quoted and double-quoted strings
These are the most common string literals.

```python
single: str = 'hello'
double: str = "world"
```

Use whichever quote style makes the string easier to read.

```python
text: str = "It's Python"
quote: str = 'She said "hi".'
```

### Triple-quoted strings
Triple quotes allow multi-line strings.

```python
message: str = """Hello,
This is a multi-line string.
Goodbye."""
```

You can also use triple single quotes.

```python
message: str = '''Line 1
Line 2'''
```

### F-strings
F-strings interpolate expressions inside `{}`.

```python
name: str = "Alice"
age: int = 30
statement: str = f"My name is {name} and I am {age} years old."
```

F-strings can evaluate expressions.

```python
result: str = f"2 + 3 = {2 + 3}"
```

### Raw strings
Raw strings treat backslashes literally in most cases.

```python
path: str = r"C:\Users\Alice\Documents\file.txt"
regex: str = r"\d+\.txt"
```

Raw strings are useful for file paths and regular expressions.

### Raw f-strings
You can combine raw strings and f-strings.

```python
name: str = "Alice"
path: str = fr"C:\Users\{name}\Documents"
```

### Legacy unicode prefix
In Python 3, `u` is accepted for compatibility, but it still creates a normal `str`.

```python
text: str = u"hello"
```

---

## Escaping characters
Escape sequences let you include special characters inside strings.

```python
newline: str = "Line 1\nLine 2"
tabbed: str = "Name\tAge"
quote: str = "She said \"hello\""
backslash: str = "C:\\temp\\file.txt"
```

Common escape sequences:
- `\n` newline
- `\t` tab
- `\\` backslash
- `\"` double quote
- `\'` single quote

---

## Indexing and slicing
Strings are sequences, so you can access characters by index.

```python
word: str = "Python"
first: str = word[0]
last: str = word[-1]
```

You can extract substrings using slicing.

```python
word: str = "Python"
part: str = word[1:4]
step: str = word[::2]
reverse: str = word[::-1]
```

---

## Concatenation and repetition
Use `+` to concatenate strings.

```python
first: str = "Py"
second: str = "thon"
combined: str = first + second
```

Use `*` to repeat strings.

```python
divider: str = "-" * 10
```

Adjacent string literals are also combined by Python.

```python
text: str = "Hello, " "world!"
```

For joining many strings, prefer `str.join()`.

```python
words: list[str] = ["Python", "is", "fun"]
sentence: str = " ".join(words)
```

---

## Useful string operations
Strings are immutable, which means methods return new strings instead of changing the original value.

```python
name: str = "python"
upper_name: str = name.upper()

print(name)       # python
print(upper_name) # PYTHON
```

Common operations:

```python
text: str = "Hello, World"

length: int = len(text)
contains: bool = "World" in text
starts: bool = text.startswith("Hello")
ends: bool = text.endswith("World")
replaced: str = text.replace("World", "Python")
```

---

## String methods
Below is a reference for the built-in `str` methods.

### Case conversion methods
| Method | Description | Example |
| --- | --- | --- |
| `capitalize()` | Capitalizes the first character | `"python".capitalize()` -> `"Python"` |
| `casefold()` | Aggressive lowercase for caseless comparisons | `"Straße".casefold()` -> `"strasse"` |
| `lower()` | Converts to lowercase | `"PyThOn".lower()` -> `"python"` |
| `swapcase()` | Swaps uppercase and lowercase letters | `"PyThOn".swapcase()` -> `"pYtHoN"` |
| `title()` | Converts to title case | `"hello world".title()` -> `"Hello World"` |
| `upper()` | Converts to uppercase | `"python".upper()` -> `"PYTHON"` |

### Search and replace methods
| Method | Description | Example |
| --- | --- | --- |
| `count(sub)` | Counts non-overlapping occurrences | `"banana".count("na")` -> `2` |
| `find(sub)` | Returns first index or `-1` | `"banana".find("na")` -> `2` |
| `index(sub)` | Returns first index or raises `ValueError` | `"banana".index("na")` -> `2` |
| `rfind(sub)` | Returns last index or `-1` | `"banana".rfind("na")` -> `4` |
| `rindex(sub)` | Returns last index or raises `ValueError` | `"banana".rindex("na")` -> `4` |
| `replace(old, new)` | Replaces occurrences of a substring | `"banana".replace("na", "NA")` -> `"baNANA"` |
| `startswith(prefix)` | Checks whether the string starts with a prefix | `"python".startswith("py")` -> `True` |
| `endswith(suffix)` | Checks whether the string ends with a suffix | `"python".endswith("on")` -> `True` |

### Split and join methods
| Method | Description | Example |
| --- | --- | --- |
| `join(iterable)` | Joins strings with a separator | `", ".join(["a", "b"])` -> `"a, b"` |
| `partition(sep)` | Splits into 3 parts at first separator | `"a=b".partition("=")` -> `("a", "=", "b")` |
| `rpartition(sep)` | Splits into 3 parts at last separator | `"a=b=c".rpartition("=")` -> `("a=b", "=", "c")` |
| `split(sep=None)` | Splits from the left | `"a,b,c".split(",")` -> `["a", "b", "c"]` |
| `rsplit(sep=None)` | Splits from the right | `"a,b,c".rsplit(",", 1)` -> `["a,b", "c"]` |
| `splitlines()` | Splits on line boundaries | `"a\nb".splitlines()` -> `["a", "b"]` |

### Trim and removal methods
| Method | Description | Example |
| --- | --- | --- |
| `strip(chars=None)` | Removes leading and trailing characters | `"  hi  ".strip()` -> `"hi"` |
| `lstrip(chars=None)` | Removes leading characters | `"  hi".lstrip()` -> `"hi"` |
| `rstrip(chars=None)` | Removes trailing characters | `"hi  ".rstrip()` -> `"hi"` |
| `removeprefix(prefix)` | Removes the given prefix if present | `"unhappy".removeprefix("un")` -> `"happy"` |
| `removesuffix(suffix)` | Removes the given suffix if present | `"file.txt".removesuffix(".txt")` -> `"file"` |

### Alignment and padding methods
| Method | Description | Example |
| --- | --- | --- |
| `center(width)` | Centers text in a field | `"cat".center(7, "-")` -> `"--cat--"` |
| `ljust(width)` | Left-aligns text in a field | `"cat".ljust(6, ".")` -> `"cat..."` |
| `rjust(width)` | Right-aligns text in a field | `"cat".rjust(6, ".")` -> `"...cat"` |
| `zfill(width)` | Pads numeric text with leading zeroes | `"42".zfill(5)` -> `"00042"` |

### Boolean test methods
| Method | Description | Example |
| --- | --- | --- |
| `isalnum()` | Checks for alphanumeric characters only | `"abc123".isalnum()` -> `True` |
| `isalpha()` | Checks for alphabetic characters only | `"abc".isalpha()` -> `True` |
| `isascii()` | Checks whether all characters are ASCII | `"abc".isascii()` -> `True` |
| `isdecimal()` | Checks for decimal characters | `"123".isdecimal()` -> `True` |
| `isdigit()` | Checks for digit characters | `"123".isdigit()` -> `True` |
| `isidentifier()` | Checks whether the string is a valid identifier | `"user_name".isidentifier()` -> `True` |
| `islower()` | Checks whether cased characters are lowercase | `"python".islower()` -> `True` |
| `isnumeric()` | Checks for numeric characters | `"123".isnumeric()` -> `True` |
| `isprintable()` | Checks whether all characters are printable | `"hello".isprintable()` -> `True` |
| `isspace()` | Checks for whitespace only | `"   ".isspace()` -> `True` |
| `istitle()` | Checks for title-cased text | `"Hello World".istitle()` -> `True` |
| `isupper()` | Checks whether cased characters are uppercase | `"PYTHON".isupper()` -> `True` |

### Formatting, encoding, and translation methods
| Method | Description | Example |
| --- | --- | --- |
| `encode()` | Encodes the string into bytes | `"hello".encode("utf-8")` -> `b"hello"` |
| `expandtabs()` | Replaces tabs with spaces | `"a\tb".expandtabs(4)` -> `"a   b"` |
| `format()` | Formats a string using placeholders | `"Hello, {}".format("Alice")` -> `"Hello, Alice"` |
| `format_map(mapping)` | Formats a string using a mapping object | `"{name}".format_map({"name": "Alice"})` -> `"Alice"` |
| `maketrans(...)` | Creates a translation table for `translate()` | `str.maketrans({"a": "@"})` |
| `translate(table)` | Replaces characters using a translation table | `"apple".translate(str.maketrans({"a": "@"}))` -> `"@pple"` |

---

## Notes
- Strings are **immutable**.
- Use `join()` instead of repeated `+` when combining many strings.
- Prefer **f-strings** for most modern string formatting.
- Raw strings cannot end with a single trailing backslash.
- `find()` returns `-1` when not found, while `index()` raises `ValueError`.
