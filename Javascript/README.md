# JavaScript

**Contents**
- [File Name](#file-name)
- [Syntax](#syntax)
- [Keywords](#keywords)
- [Variables](#variables)
  - [var](#var)
  - [let](#let)
  - [const](#const)
- [Primitive Data Types](#primitive-data-types)
  - [String](#string)
  - [Number](#number)
  - [BigInt](#bigint)
  - [Boolean](#boolean)
  - [Null](#null)
  - [Undefined](#undefined)
  - [Symbol](#symbol)
- [Data Structures](#data-structures)
  - [Arrays](#arrays)
  - [Objects](#objects)
  - [Maps](#maps)
  - [Sets](#sets)
- [Conditionals](#conditionals)
  - [if](#if)
  - [else if](#else-if)
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
  - [Arrow Functions](#arrow-functions)
- [JavaScript-Specific Features](#javascript-specific-features)
  - [Template Literals](#template-literals)
  - [Optional Chaining](#optional-chaining)

---

### File Name
JavaScript source files typically use the `.js` extension.

---

### Syntax
JavaScript uses curly braces (`{}`) to define blocks and parentheses (`()`) for function calls and conditions. Indentation improves readability, but it does not define scope.

Semicolons are optional because of automatic semicolon insertion, but many codebases use them consistently.

```javascript
if (isReady) {
    console.log("Ready");
}
```

---

### Keywords
JavaScript has reserved keywords that cannot be used as identifiers in many contexts.

Common keywords include:
- `async`
- `await`
- `break`
- `case`
- `catch`
- `class`
- `const`
- `continue`
- `debugger`
- `default`
- `delete`
- `do`
- `else`
- `export`
- `extends`
- `finally`
- `for`
- `function`
- `if`
- `import`
- `in`
- `instanceof`
- `let`
- `new`
- `return`
- `super`
- `switch`
- `this`
- `throw`
- `try`
- `typeof`
- `var`
- `void`
- `while`
- `with`
- `yield`

---

### Variables
#### var
Variables declared with `var` are function-scoped or globally scoped.
```javascript
/** @type {number} */
var num = 34;
```

#### let
Variables declared with `let` are block-scoped.
```javascript
/** @type {string} */
let str = "";
```

#### const
Variables declared with `const` are block-scoped and cannot be reassigned.
```javascript
/** @type {number} */
const pi = 3.14;
```

---

### Primitive Data Types
#### String
Strings are used to store text.
```javascript
/** @type {string} */
const str = "Hello";
```

#### Number
Numbers are used to store numeric values.
```javascript
/** @type {number} */
const num = 3.14;
const negative = -76;
```

#### BigInt
`bigint` is used to store large integer values.
```javascript
/** @type {bigint} */
const bigInt = 12345678901234567890n;
```

#### Boolean
Booleans store `true` or `false` values.
```javascript
/** @type {boolean} */
const isReady = true;
```

#### Null
`null` represents the intentional absence of a value.
```javascript
/** @type {null} */
const nullValue = null;
```

#### Undefined
`undefined` represents a value that has not been assigned.
```javascript
/** @type {undefined} */
const undefinedValue = undefined;
```

#### Symbol
`symbol` is used to create unique identifiers.
```javascript
/** @type {symbol} */
const id = Symbol("id");
```

---

### Data Structures
#### Arrays
Arrays are ordered collections and can contain values of any type.
```javascript
/** @type {string[]} */
const fruits = ["apple", "banana", "cherry"];
```

#### Objects
Objects store key-value pairs.
```javascript
/** @type {{ name: string; age: number; city: string }} */
const person = {
    name: "John",
    age: 30,
    city: "New York"
};
```

#### Maps
Maps store key-value pairs and can use values of any type as keys.
```javascript
/** @type {Map<string, number>} */
const ages = new Map([
    ["Alice", 30],
    ["Bob", 25]
]);
```

#### Sets
Sets store unique values.
```javascript
/** @type {Set<string>} */
const set = new Set(["apple", "banana"]);
```

---

### Conditionals
#### if
`if` statements execute code when a condition is true.
```javascript
if (score >= 90) {
    console.log("Excellent");
}
```

#### else if
`else if` adds another condition when the first one is false.
```javascript
if (score >= 90) {
    console.log("Excellent");
} else if (score >= 75) {
    console.log("Pass");
}
```

#### else
`else` executes code when all previous conditions are false.
```javascript
if (score >= 90) {
    console.log("Excellent");
} else {
    console.log("Keep trying");
}
```

#### Inline Usage
Use the ternary operator for short conditional expressions.
```javascript
const result = score >= 75 ? "Pass" : "Fail";
```

Use the nullish coalescing operator to provide a default value for `null` or `undefined`.
```javascript
const name = null;
const displayName = name ?? "Anonymous";
```

---

### Loops
#### for
`for` loops are useful when you know how many times to iterate.
```javascript
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

#### while
`while` loops continue as long as a condition is true.
```javascript
let count = 0;
while (count < 5) {
    console.log(count);
    count += 1;
}
```

---

### Functions
#### Function Definition
Functions are declared using the `function` keyword.
```javascript
function add(a, b) {
    return a + b;
}
```

Functions can also be defined as expressions.
```javascript
const subtract = function(a, b) {
    return a - b;
};
```

#### Function Call
Functions are called by appending `()` to the function name.
```javascript
add(3, 4);
```

#### Return
Functions return a value using the `return` keyword.
```javascript
function multiply(a, b) {
    return a * b;
}
```

#### Arguments
Arguments are passed to functions when they are called.

**Positional arguments**
```javascript
function add(a, b) {
    return a + b;
}

add(3, 4);
```

**Default values**
```javascript
function greet(name = "World") {
    return `Hello, ${name}!`;
}

greet();
```

**Rest parameters**
```javascript
function total(...numbers) {
    return numbers.reduce((sum, number) => sum + number, 0);
}

total(1, 2, 3, 4);
```

#### Arrow Functions
Arrow functions provide a shorter syntax for writing functions.
```javascript
const add = (a, b) => a + b;
```

Arrow functions are called the same way as other functions.
```javascript
add(3, 4);
```

---

### JavaScript-Specific Features
#### Template Literals
Template literals use backticks and support interpolation with `${...}`.
```javascript
const name = "John";
const message = `Hello, ${name}!`;
```

#### Optional Chaining
Optional chaining (`?.`) safely accesses nested properties.
```javascript
const city = user?.address?.city;
```
