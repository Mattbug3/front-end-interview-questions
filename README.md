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
  
In JavaScript, we can declare a variable using the `var`, `let`, or `const` keywords. Here's how we can use each of them:
  
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
When we declare a variable using `let` or `const`, it's a good practice to initialize it with a value, although it's not mandatory.
</details>

---

###### 3. What is the difference between var, let, and const?

<details><summary><b>Answer</b></summary>

  The main differences between `var`, `let`, and `const` in JavaScript lie in their **scoping rules** , **reassignment**, **and ability to be redeclared**. Here's a breakdown of the key differences:

#### 1. Scoping:

- `var`: Variables declared with `var` have function scope or global scope. They are function-scoped if declared inside a function, or globally scoped if declared outside any function.
- `let` and `const`: Variables declared with `let` and `const` have block scope. They are scoped to the nearest enclosing block, which can be a function, loop, or any other block statement.

```javascript
function exampleScope() {
    if (true) {
        var varVariable = 'I am var';
        let letVariable = 'I am let';
        const constVariable = 'I am const';
    }
    console.log(varVariable); // Works
    console.log(letVariable); // ReferenceError: letVariable is not defined
    console.log(constVariable); // ReferenceError: constVariable is not defined
}

exampleScope();
```
In this example, `varVariable` is accessible outside the block because it's declared with `var`, which has **function scope**. `letVariable` and `constVariable` are not accessible outside the block because they are declared with `let` and `const`, respectively, which have **block scope**.

#### 2. Reassignment:

`var`: Variables declared with `var` **can be updated** and **reassigned** within their scope.
`let`: Variables declared with let **can be updated** and **reassigned** within their scope, just like var.
`const`: Variables declared with const **cannot be reassigned** after initialization. However, **if the variable holds a reference to an object, the properties of that object can be modified**.

```javascript
var varValue = 10;
let letValue = 20;
const constValue = 30;

varValue = 11; // Works
letValue = 21; // Works
constValue = 31; // Error: Assignment to constant variable
```
In this example, we can see that `varValue` and `letValue` can be reassigned new values without any error. However, attempting to reassign a new value to `constValue` results in an error because it's declared with const, which **doesn't allow reassignment**.

#### 3. Redeclaration:

`var`: Variables declared with `var` **can be redeclared** within the same scope without any error.
`let`: Variables declared with `let` **cannot be redeclared** in the same scope. Attempting to do so will result in a **syntax error**.
`const`: Like `let`, variables declared with `const` **cannot be redeclared** in the same scope. Attempting to do so will also result in a **syntax error**.

```javascript
var varVariable = 'I am var';
let letVariable = 'I am let';
const constVariable = 'I am const';

var varVariable = 'I am redeclared var'; // Works
let letVariable = 'I am redeclared let'; // Error: Identifier 'letVariable' has already been declared
const constVariable = 'I am redeclared const'; // Error: Identifier 'constVariable' has already been declared
```

In this example, we can see that we can redeclare `varVariable` with `var`, but attempting to redeclare `letVariable` or `constVariable` with `let` or `const`, respectively, results in errors because they have already been declared in the same scope.

#### Here's a summary:

- Use `var` for variables that need to have *function* or *global scope* and might *need to be redeclared*.
- Use `let` for variables that have *block scope* and might *need to be reassigned, but not redeclared*.
- Use `const` for variables that have *block scope* and *whose value should not change after initialization*.
</details>

---

