# Interview Questions

###### 1. What are the different data types in JavaScript?

<details><summary><b>Answer</b></summary>
JavaScript provides different data types to hold different types of values. There are two types of data types in JavaScript:

1. Primitive data type.
- String.
- Number.
- Bigint.
- Boolean.
- Undefined.
- Null.
- Symbol.

2. Non-primitive (reference) data type.
- Array.
- Object.
</details>

---

###### 2. How do you delare a variable in JavaScript?

<details><summary><b>Answer</b></summary>
In JavaScript, we can declare a variable using the var, let, or const keywords. Here's how we can use each of them:
#### 1. Using `var`:
  
```javascript
var variableName;
```
Variables declared with `var` have function scope or global scope, but not block scope. They can be re-declared and updated within their scope.

#### 2. Using `let`:

```javascript
let variableName;
```
Variables declared with `let` have block scope. They can be updated within their scope but cannot be re-declared in the same scope.

#### 2. Using `const`:
```javascript
const variableName = value;
```
Variables declared with `const` are constants and cannot be reassigned after initialization. They have block scope like variables declared with `let`.

Here are some examples:

```javascript
// Using var
var age;

// Using let
let name;

// Using const
const PI = 3.14;
```
When you declare a variable using `let` or `const`, it's a good practice to initialize it with a value, although it's not mandatory.
</details>
