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

###### 2. How do you declare a variable in JavaScript?

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

- `var`: Variables declared with `var` **can be updated** and **reassigned** within their scope.
- `let`: Variables declared with let **can be updated** and **reassigned** within their scope, just like var.
- `const`: Variables declared with const **cannot be reassigned** after initialization. However, **if the variable holds a reference to an object, the properties of that object can be modified**.

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

- `var`: Variables declared with `var` **can be redeclared** within the same scope without any error.
- `let`: Variables declared with `let` **cannot be redeclared** in the same scope. Attempting to do so will result in a **syntax error**.
- `const`: Like `let`, variables declared with `const` **cannot be redeclared** in the same scope. Attempting to do so will also result in a **syntax error**.

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

###### 4.  How does hoisting work in JavaScript?

<details><summary><b>Answer</b></summary>

Hoisting in JavaScript is a mechanism where variable and function declarations are moved to the top of their containing scope during the compilation phase, before the code is executed. This means that regardless of where variables and functions are declared within their scope, they are treated as if they were declared at the top of the scope.

Here's how hoisting works for variables and functions:

#### 1. Variable Hoisting:

- When variables are declared with `var`, they are hoisted to the top of their containing function scope or global scope.
However, only the declaration is hoisted, not the initialization. This means that variables are initialized with `undefined` by default until their actual assignment is reached in the code.
- Variables declared with `let` or `const` are also hoisted to the top of their containing block scope, but they are not initialized until their actual declaration is reached in the code. This is called the `temporal dead zone` and attempting to access these variables before their declaration results in a `ReferenceError`.

Here's an example to illustrate variable hoisting:

```javascript
console.log(x); // undefined
var x = 5;
console.log(x); // 5
// This is equivalent to:

var x;
console.log(x); // undefined
x = 5;
console.log(x); // 5

console.log(y); // ReferenceError: Cannot access 'y' before initialization
let y = 5;

console.log(z); // ReferenceError: Cannot access 'z' before initialization
let z = 10;
```

#### 2. Function Hoisting:

- Function declarations are completely hoisted, including both the declaration and the function definition.
This means that we can call a function before it's declared in the code, and it will still work.

Here's an example to illustrate function hoisting:

```javascript
foo(); // "Hello, I am foo!"

function foo() {
    console.log("Hello, I am foo!");
}

// This is equivalent to:

function foo() {
    console.log("Hello, I am foo!");
}

foo(); // "Hello, I am foo!"
```

It's important to understand hoisting in JavaScript to avoid unexpected behavior and to write more readable and maintainable code.
</details>

---

###### 5. What are closures in JavaScript and how are they work?

<details><summary><b>Answer</b></summary>

#### 1. Definition: 

When an inner function is defined within an outer function, the inner function retains a reference to the variables in the outer function's scope, even after the outer function has completed execution. This combination of the inner function and the variables it has access to forms a `closure`.

#### 2. How closures work:

- ##### Access to Outer Scope Variables: 
The inner function can access the variables, parameters, and functions of the outer function, as well as the global scope. This is possible because the inner function retains a reference to the variables in its lexical scope.

- ##### Preservation of Scope: 
`Closures` allow functions to maintain references to variables from their containing scopes, preventing those variables from being garbage-collected when the outer function finishes executing. This enables powerful patterns such as data encapsulation and private variables.

Here's an example to illustrate closures:

```javascript
function outerFunction() {
    let outerVariable = 'I am outer';

    function innerFunction() {
        console.log(outerVariable); // Accesses outerVariable from the outer function's scope
    }

    return innerFunction;
}

const closure = outerFunction();
closure(); // Outputs: "I am outer"
```
In this example, `innerFunction` is defined within `outerFunction` and has access to `outerVariable`. Even after `outerFunction` has finished executing, the `closure` function (which is `innerFunction`) still has access to `outerVariable`, thanks to the `closure`. This allows `closure` to access and use `outerVariable` when it's invoked.
</details>

---

###### 6. How do you use callbacks in JavaScript?
<details><summary><b>Answer</b></summary>

In JavaScript, a callback is a function that we pass as an argument to another function and execute after the completion of a particular task or event. Callbacks are commonly used in asynchronous operations, such as handling events, making API requests, or dealing with timeouts.

For instance, let's say we want to fetch data from a server using an asynchronous HTTP request. We can define a callback function to handle the response data once it's available:

```javascript
function fetchData(url, callback) {
    fetch(url)
        .then(response => response.json())
        .then(data => callback(data))
        .catch(error => console.error(error));
}

function processResponse(data) {
    console.log(data);
}

fetchData('https://api.example.com/data', processResponse);
```

In this example, `fetchData` is a function that makes an asynchronous HTTP request to the specified URL. We pass a callback function (`processResponse`) as an argument. Once the data is fetched successfully, the `callback` function is invoked with the response data. This allows us to handle the response data in the `processResponse` function, which could involve rendering it on the UI or performing additional processing.

Another example involves handling events in a web application. Suppose we want to add a click event listener to a button element and execute a callback function when the button is clicked:

```javascript
const button = document.getElementById('myButton');

function handleClick() {
    console.log('Button clicked');
}

button.addEventListener('click', handleClick);
```
In this case, the `handleClick` function is passed as a `callback`to the `addEventListener` method. When the `button` is `clicked`, the `handleClick` function is executed, logging `Button clicked` to the console.

Here's another example showcasing the usage of callbacks for dealing with timeouts:

```javascript
function delayedMessage(message, delay, callback) {
    setTimeout(() => {
        console.log(message);
        callback();
    }, delay);
}

function afterDelay() {
    console.log('Callback executed after delay');
}

// Call delayedMessage function with a message, delay of 2 seconds, and a callback
delayedMessage('This message is delayed by 2 seconds', 2000, afterDelay);
```
In this example, we define a function called `delayedMessage` that takes three parameters: `message` (the message to be logged), `delay` (the delay time in milliseconds), and `callback` (the callback function to be executed after the delay). Inside `delayedMessage`, we use `setTimeout` to schedule the execution of a function after the specified delay. Once the delay is over, the provided `message` is logged to the console, and then the `callback` function is invoked.

We also define a `callback` function called `afterDelay`, which simply logs a `message` indicating that it has been executed. Finally, we call the `delayedMessage` function with the `message` to be displayed after the `delay`, a `delay` of 2000 milliseconds (2 seconds), and the `afterDelay` function as the `callback`. This demonstrates how we can use `callbacks` to perform actions after a specified delay, such as `animations`, `notifications`, or other `asynchronous` tasks.
</details>

---

###### 7. What are promises in JavaScript?
<details><summary><b>Answer</b></summary>
In JavaScript, promises are objects representing the eventual completion or failure of an asynchronous operation. We use them to handle asynchronous operations such as fetching data from a server, reading files, or executing animations, where the result may not be available immediately.

We can create a promise using the `Promise` constructor, passing a function with `resolve` and `reject` parameters. Inside this function, we perform an asynchronous operation, like using `setTimeout` to simulate a delay, and then resolve or reject the promise based on the result.

```javascript
// Creating a promise
const myPromise = new Promise((resolve, reject) => {
    // Simulating an asynchronous operation
    setTimeout(() => {
        const randomNumber = Math.random();
        if (randomNumber > 0.5) {
            resolve(randomNumber); // Resolve the promise with a value
        } else {
            reject(new Error('Random number is too small')); // Reject the promise with an error
        }
    }, 1000);
});

// Handling the promise
myPromise.then((result) => {
    console.log('Promise fulfilled with result:', result);
}).catch((error) => {
    console.log('Promise rejected with error:', error.message);
});
```
Here, we handle the `fulfilled` state (success) of the promise using the `then()` method and the `rejected` state (failure) using the `catch()` method. Promises provide a cleaner and more flexible way to work with asynchronous code compared to traditional callback-based approaches, allowing for better error handling and chaining of multiple asynchronous operations.
</details>

---

###### 8. What is async/await in JavaScript?
<details><summary><b>Answer</b></summary>

In JavaScript, `async/await` is a syntax used to work with asynchronous code in a more synchronous and readable manner. It provides a way to write asynchronous code that looks like synchronous code, making it easier to understand and maintain.

The `async` keyword is used to define a function as asynchronous. An asynchronous function returns a promise implicitly, allowing us to use `await` within it to pause the execution of the function until a promise is settled (resolved or rejected).

Here's a simple example:

```javascript
async function fetchData() {
    try {
        const response = await fetch('https://api.example.com/data');
        const data = await response.json();
        console.log(data);
    } catch (error) {
        console.error('Error fetching data:', error);
    }
}

fetchData();
```

In this example:

- We define an asynchronous function `fetchData()` using the `async` keyword.
Inside the function, we use `await` to pause the execution of the function until the fetch operation completes and resolves the promise returned by `fetch()`.
- We then use `await` again to pause the execution until the `response.json()` operation completes and resolves the promise.
- If any error occurs during the execution of the asynchronous operations, it is caught and handled using a `try...catch` block.

`async/await` simplifies the process of working with promises, making asynchronous code easier to read and write compared to using raw promises or callback-based approaches.
</details>

---

###### 9. How do you handle errors in JavaScript?
<details><summary><b>Answer</b></summary>

In JavaScript, we handle errors using` try...catch` blocks and error objects. Here's how we do it:

```javascript
try {
    // Code that might throw an error
    throw new Error('An error occurred');
} catch (error) {
    // Code to handle the error
    console.error('Error:', error.message);
}
```
In this example:

- We wrap the code that might throw an error inside a try block.
- If an error occurs within the try block, it's caught by the catch block.
- The error object contains information about the error, such as its message, name, and stack trace.
- We can then handle the error appropriately, such as logging it or displaying a message to the user.

Additionally, we can also use the `finally` block to execute code regardless of whether an error occurred or not:

```javascript
try {
    // Code that might throw an error
} catch (error) {
    // Code to handle the error
} finally {
    // Code to execute regardless of errors
}
```
This allows us to clean up resources or perform cleanup tasks that need to be done regardless of the outcome of the `try...catch` block.
</details>

---

###### 10. How do you create and manipulate objects in JavaScript?
<details><summary><b>Answer</b></summary>

In JavaScript, we create and manipulate objects using `object literals`, `constructor functions`, and `classes`. Here's how we do it:

#### 1. Object Literals:

```javascript
// Creating an object using object literal
const person = {
    name: 'John',
    age: 30,
    greet() {
        console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
};

// Accessing properties and methods
console.log(person.name); // Output: John
person.greet(); // Output: Hello, my name is John and I am 30 years old.
```
#### 2. Constructor Functions:

```javascript
// Defining a constructor function
function Person(name, age) {
    this.name = name;
    this.age = age;
    // Adding a method to the prototype
    this.greet = function() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
};
}


// Creating objects using the constructor function
const person1 = new Person('John', 30);
const person2 = new Person('Alice', 25);

// Accessing properties and methods
console.log(person1.name); // Output: John
person1.greet(); // Output: Hello, my name is John and I am 30 years old.

```

#### 3. Classes (ES6+):

```javascript
// Defining a class
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    greet() {
        console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
}

// Creating objects using the class
const person1 = new Person('John', 30);
const person2 = new Person('Alice', 25);

// Accessing properties and methods
console.log(person1.name); // Output: John
person1.greet(); // Output: Hello, my name is John and I am 30 years old.
```
These are the common ways to create and manipulate objects in JavaScript. Depending on the scenario and personal preference, we can choose the approach that best suits our needs.
</details>

---

###### 11. What is the difference between '==' and '===' in JavaScript?
<details><summary><b>Answer</b></summary>

In JavaScript, `==` and `===` are comparison operators used to compare values. However, they have different behaviors:

1. `==` (loose equality operator): It checks for equality of values after converting the operands to the same type. If the operands are of different types, JavaScript will attempt to convert them to a common type before making the comparison. For example:

  - `0 == '0'` evaluates to `true` because JavaScript converts the string '0' to a number before making the comparison.
  - `1 == true` evaluates to `true` because JavaScript treats true as 1 when making the comparison.

2. `===` (strict equality operator): It checks for equality of values without performing any type conversion. Both the value and the type of the operands must be the same for the comparison to return true. For example:

  - `0 === '0'` evaluates to `false` because the types of the operands are different.
  - `1 === true` evaluates to `false` because the types of the operands are different.

In general, it's considered a best practice to use `===` for comparisons in JavaScript because it avoids unexpected type conversions and leads to more predictable code behavior.
</details>

---
