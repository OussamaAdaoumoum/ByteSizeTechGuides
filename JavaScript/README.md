# A Guide to JavaScript
## Introduction:
JavaScript is a versatile programming language commonly used in web development. It allows developers to create dynamic and interactive web pages. In this guide, we'll cover the fundamentals of JavaScript, starting from the basics and progressing to more advanced topics.

## Data Types 
### Primitive Data Types:

+ ***undefined***: The `undefined` data type represents a variable that has been declared but not assigned a value. It is often the default value of uninitialized variables.
```javascript
let x;
console.log(typeof x); // Output: undefined
```

+ ***null***: The `null` data type represents the intentional absence of any value or object. However, when checked with typeof, it returns "object", which is considered a historical quirk in JavaScript.
```javascript
let y = null;
console.log(typeof y); // Output: object
```

+ ***boolean***: The `boolean` data type represents a logical value indicating either true or false.
```javascript
let isTrue = true;
let isFalse = false;
console.log(typeof isTrue); // Output: boolean
console.log(typeof isFalse); // Output: boolean
```

+ ***string***: The `string` data type represents a sequence of characters enclosed within single ('') or double ("") quotes.

```javascript
let greeting = "Hello, world!";
console.log(typeof greeting); // Output: string
```

+ ***number***: The `number` data type represents numeric values, both integers and floating-point numbers.

```javascript
let integerNumber = 42;
let floatingPointNumber = 3.14;
console.log(typeof integerNumber); // Output: number
console.log(typeof floatingPointNumber); // Output: number
```

+ ***symbol***: The `symbol` data type represents a unique identifier. Symbols are often used as property keys in objects to avoid naming conflicts.

```javascript
let sym1 = Symbol('foo');
console.log(typeof sym1); // Output: symbol
```

+ ***bigint***: The `bigint` data type represents integers with arbitrary precision. It was introduced in ECMAScript 2020.
```javascript
const bigNumber = 1234567890123456789012345678901234567890n;
console.log(typeof bigNumber); // Output: bigint
```


### Composite Data Types:
+ ***object***: The `object` data type represents a collection of key-value pairs, where keys are strings (or symbols) and values can be any data type.

```javascript
let person = {
    name: 'John',
    age: 30,
    isStudent: false
};
console.log(typeof person); // Output: object
```

+ ***Array***: The `Array` data type represents an ordered collection of elements. Arrays can hold elements of any data type, including other arrays.
```javascript
let numbers = [1, 2, 3, 4, 5];
console.log(typeof numbers); // Output: object
```

### Special Data Types:
+ ***Function***: The `Function` data type represents a callable object that executes a block of code. Functions are first-class citizens in JavaScript, meaning they can be assigned to variables, passed as arguments to other functions, and returned from other functions.
```javascript
function greet(name) {
    console.log("Hello, " + name + "!");
}

console.log(typeof greet); // Output: function
```

+ ***Date***: The `Date` data type represents dates and times. It provides methods for creating, formatting, and manipulating dates.
```javascript
let currentDate = new Date();
console.log(typeof currentDate); // Output: object
```

+ ***RegExp***: The `RegExp` data type represents regular expressions, which are patterns used for matching strings in text. Regular expressions provide a powerful and flexible way to search, replace, and manipulate text.

```javascript
let pattern = /[a-z]+/;
console.log(typeof pattern); // Output: object
```

## Case Sensitivity in Variables

Case sensitivity in variables means that JavaScript distinguishes between uppercase and lowercase letters in variable names. This means that myVariable and MyVariable would be treated as different variables.

```javascript
let myVariable = 10;
let MyVariable = 20;

console.log(myVariable);  // Output: 10
console.log(MyVariable);  // Output: 20
```

## Global and Local Scope
In JavaScript, variable scope refers to the accessibility or visibility of variables within different parts of a program. Understanding global and local scope is crucial for writing clean and maintainable code.

+ ***Global Scope***: Variables declared outside of any function or block have global scope. They can be accessed from anywhere within the program, including inside functions and blocks.

+ ***Local Scope***: Variables declared within a function or block have local scope. They are only accessible within the function or block in which they are declared.

When variables are declared without the let or const keywords, they are automatically created in the global scope. This can lead to unintended consequences, especially when working with functions, as it may result in variable name conflicts or unexpected behavior.

## Differences between `let`, `var` and `const`
+ ***var***: `var` was traditionally used for variable declarations in JavaScript. Variables declared with var are function-scoped or globally scoped. This means that they are accessible anywhere within the function in which they are declared or globally if declared outside of any function. Additionally, var variables can be redeclared and reassigned.
```javascript
var x = 10;
console.log(x);  // Output: 10

function exampleFunction() {
    var y = 20;
    console.log(y);  // Output: 20
}

console.log(y);  // Throws a ReferenceError: y is not defined
```

+ ***let***: `let` was introduced in ECMAScript 6 (ES6) and provides block-scoping for variables. Variables declared with let are only accessible within the block (enclosed by curly braces) in which they are declared. They cannot be redeclared within the same block, but they can be reassigned.
```javascript
let a = 30;
console.log(a);  // Output: 30

{
    let b = 40;
    console.log(b);  // Output: 40
}

console.log(b);  // Throws a ReferenceError: b is not defined
```

+ ***const***: `const` was also introduced in ECMAScript 6 (ES6) and behaves similarly to let regarding block-scoping. However, variables declared with const are immutable, meaning that their value cannot be changed once assigned. It's important to note that while the variable itself is immutable, if it holds an object or array, the properties or elements of that object or array can still be modified.

```javascript
const PI = 3.14;
console.log(PI);  // Output: 3.14

// PI = 3.14159;  // This would throw an error, cannot assign to const variable

const person = { name: 'John' };
person.age = 30;  // Valid, but person itself cannot be reassigned
console.log(person);  // Output: { name: 'John', age: 30 }
```
## Differences between `===` and `==`, as well as `!==` and `!=`
+ ***=== (Strict Equality Operator)***:
    - The === operator checks for strict equality without type coercion. It returns true if the operands are of the same type and have the same value.
    - If the operands are different types, === returns false without attempting to convert them to the same type.
```javascript
// Strict equality (===)
console.log(5 === 5);        // Output: true
console.log(5 === '5');      // Output: false (different types)
console.log(5 === 10);       // Output: false
console.log('hello' === 'hello');  // Output: true
```

+ ***== (Abstract Equality Operator)***:
    - The == operator checks for equality after type coercion. It converts the operands to the same type before comparing them.
    - If the operands are of different types, JavaScript attempts to convert them to the same type and then compare their values.
```javascript
// Abstract equality (==)
console.log(5 == 5);         // Output: true
console.log(5 == '5');       // Output: true (converted to the same type)
console.log(5 == 10);        // Output: false
console.log('hello' == 'hello');   // Output: true
```
+ ***!== (Strict Inequality Operator)***:
    - The !== operator checks for strict inequality without type coercion. It returns true if the operands are of different types or have different values.
    - If the operands are of the same type and have the same value, !== returns false.
```javascript
// Strict inequality (!==)
console.log(5 !== 5);        // Output: false
console.log(5 !== '5');      // Output: true (different types)
console.log(5 !== 10);       // Output: true
console.log('hello' !== 'hello');  // Output: false
```

+ ***!= (Abstract Inequality Operator)***:
    - The != operator checks for inequality after type coercion. It converts the operands to the same type before comparing them.
    - If the operands are of different types, JavaScript attempts to convert them to the same type and then compare their values.
```javascript
// Abstract inequality (!=)
console.log(5 != 5);         // Output: false
console.log(5 != '5');       // Output: false (converted to the same type)
console.log(5 != 10);        // Output: true
console.log('hello' != 'hello');   // Output: false
```


## String Immutability
In JavaScript, `strings are immutable`, which means that once a string is created, its value cannot be changed. When you perform operations on strings such as concatenation or substring extraction, you're actually creating new strings rather than modifying the original string.
```javascript
let str = "Hello";
console.log(str);  // Output: Hello

// Attempting to change the string
str[0] = "J";  // This won't change the string

console.log(str);  // Output: Hello
```

## Manipulate Arrays
Arrays in JavaScript come with built-in methods to manipulate their contents dynamically. Four common methods for manipulating arrays are push, pop, shift, and unshift.

+ ***push()***: Adds one or more elements to the end of an array and returns the new length of the array.
+ ***pop()***: Removes the last element from an array and returns that element.
```javascript
let fruits = ['apple', 'banana', 'orange'];

fruits.push('grape');  // Add 'grape' to the end
console.log(fruits);  // Output: ['apple', 'banana', 'orange', 'grape']

let removedFruit = fruits.pop();  // Remove the last element ('grape')
console.log(removedFruit);  // Output: grape
console.log(fruits);  // Output: ['apple', 'banana', 'orange']
```

+ ***shift()***: Removes the first element from an array and returns that element, shifting all other elements one position to the left.
+ ***unshift()***: Adds one or more elements to the beginning of an array and returns the new length of the array.
```javascript
let fruits = ['apple', 'banana', 'orange'];

fruits.unshift('grape');  // Add 'grape' to the beginning
console.log(fruits);  // Output: ['grape', 'apple', 'banana', 'orange']

let removedFruit = fruits.shift();  // Remove the first element ('grape')
console.log(removedFruit);  // Output: grape
console.log(fruits);  // Output: ['apple', 'banana', 'orange']
```
Other methods like ***splice()***, ***slice()***, ***concat()***, ***reverse()***, ***sort()***, etc., are also available for array manipulation.
```javascript
let fruits = ['apple', 'banana', 'orange', 'grape'];

// Remove 1 element starting from index 1
fruits.splice(1, 1);
console.log(fruits);  // Output: ['apple', 'orange', 'grape']

// Insert 'kiwi' at index 1, without removing any elements
fruits.splice(1, 0, 'kiwi');
console.log(fruits);  // Output: ['apple', 'kiwi', 'orange', 'grape']

// Replace 1 element at index 2 with 'mango'
fruits.splice(2, 1, 'mango');
console.log(fruits);  // Output: ['apple', 'kiwi', 'mango', 'grape']
```


## ECMAScript Features OverView
ECMAScript is the standardized specification for the JavaScript language, providing consistency and interoperability across different implementations and environments. Understanding ECMAScript versions, features, and compatibility is essential for JavaScript developers to write modern, efficient, and maintainable code

### Arraw Functions 
Arrow functions are a concise way to write anonymous functions in JavaScript. They provide a more compact syntax compared to traditional function expressions, especially for short, one-liner functions. Arrow functions have become increasingly popular due to their simplicity and readability.

```javascript
// Traditional function expression
let add = function(x, y) {
    return x + y;
};

// Arrow function with return statement
let addArrow = (x, y) => {
    return x + y;
};

// Arrow function without return statement (implicit return)
let squareArrow = x => x * x;

// Arrow function with no parameters
let greetArrow = () => "Hello, world!";

// Arrow function with multiple lines
let multiplyArrow = (x, y) => {
    let result = x * y;
    return result;
};

console.log(add(3, 5));       // Output: 8
console.log(addArrow(3, 5));   // Output: 8
console.log(squareArrow(4));   // Output: 16
console.log(greetArrow());  // Output: Hello, world!
console.log(multiplyArrow(2, 3));  // Output: 6
```

### Use the Rest Parameter with Function Parameters
The rest parameter syntax in JavaScript allows a function to accept an indefinite number of arguments as an array. This provides flexibility when working with functions that need to handle varying numbers of parameters.
```javascript 
// Example 1: Calculating the sum of numbers using rest parameter

function sum(...numbers) {
    let result = 0;
    for (let number of numbers) {
        result += number;
    }
    return result;
}

console.log(sum(1, 2, 3));  // Output: 6
console.log(sum(1, 2, 3, 4, 5));  // Output: 15
console.log(sum(10));  // Output: 10
console.log(sum());  // Output: 0 (no arguments)
```
### Use the Spread Operator to Evaluate Arrays In-Place
The spread operator in JavaScript allows you to expand an iterable (like an array) into individual elements. It's often used to make shallow copies of arrays, concatenate arrays, or pass array elements as arguments to functions.
```javascript
// Example 1: Concatenating arrays
let arr1 = [1, 2, 3];
let arr2 = [4, 5, 6];

let concatenatedArray = [...arr1, ...arr2];
console.log(concatenatedArray); // Output: [1, 2, 3, 4, 5, 6]
```

### Destructuring assignment
+ 1. Extract Values from Objects:
Destructuring assignment in JavaScript allows you to extract values from arrays or properties from objects into individual variables. It provides a concise and expressive way to work with complex data structures.
```javascript 
const person = {
  name: 'John',
  age: 30,
  city: 'New York'
};

const { name, age, city } = person;

console.log(name, age, city); // Output: John 30 New York
```
In this example, the name, age, and city variables are created and assigned the corresponding values from the person object using destructuring assignment.

+ 2. Assign Variables from Objects:
```javascript
const user = {
  username: 'user123',
  email: 'user@example.com',
  password: 'password123'
};

const { username: myUsername, email: myEmail } = user;

console.log(myUsername, myEmail); // Output: user123 user@example.com
```
Here, the properties username and email from the user object are assigned to new variables myUsername and myEmail using destructuring assignment.

+ 3. Assign Variables from Nested Objects:
```javascript
const student = {
  name: 'Alice',
  info: {
    grade: 'A',
    school: 'High School'
  }
};

const { name: studentName, info: { grade, school } } = student;

console.log(studentName, grade, school); // Output: Alice
```
In this example, the nested properties grade and school inside the info object are extracted using destructuring assignment.

+ 4. Assign Variables from Arrays:
Destructuring assignment in JavaScript can also be used to extract values from arrays and assign them to variables. This feature provides a convenient way to unpack values from arrays into individual variables.
```javascript
const numbers = [1, 2, 3, 4, 5];

const [first, , third, ...rest] = numbers;

console.log(first); // Output: 1
console.log(third); // Output: 3
console.log(rest); // Output: [4,5]
```
+ 5. Use Destructuring Assignment to Pass an Object as a Function's Parameters:
 Destructuring assignment can be used to pass an object as a function's parameters, which allows for more readable and flexible function calls. Additionally, you can use rest elements with destructuring to gather remaining properties into a single variable.
 ```javascript 
 // Function definition with destructuring parameters and rest element
function printUserDetails({ name, age, ...rest }) {
    console.log(`Name: ${name}, Age: ${age}`);
    console.log('Additional details:', rest);
}

// Object containing user details
const user = {
    name: 'Alice',
    age: 30,
    city: 'New York',
    country: 'USA'
};

// Function call with object passed as parameter
printUserDetails(user); 
//output: 
// Name: Alice, Age: 30 
// Additional details: { city: 'New York', country: 'USA' }
```

### Create Strings using Template Literals
Template literals in JavaScript provide a convenient and concise way to create strings, allowing for easy interpolation of variables and expressions within the string. Template literals are enclosed by backticks (` `) instead of single or double quotes.
```javascript
// Expressions in Template Literals
const a = 10;
const b = 5;
const expressionResult = `The sum of ${a} and ${b} is ${a + b}.`;

console.log(expressionResult); // Output: The sum of 10 and 5 is 15.
```

### Write Concise Declarative Functions with ES6
In ES6, you can write concise declarative functions using arrow function syntax, especially when defining functions within objects or when returning functions from other functions. Here's how you can use arrow functions for concise declarative functions:

+ 1. Object Method Declaration:
```javascript 
// ES5
const person = {
  name: 'Alice',
  sayHello: function() {
    console.log('Hello, ' + this.name + '!');
  }
};

// ES6
const person = {
  name: 'Alice',
  sayHello() {
    console.log(`Hello, ${this.name}!`);
  }
};
```
In ES6, you can omit the `function` keyword and the colon (':') when defining methods in objects. This results in a more concise syntax for declaring object methods.

+ 2. Returning Functions:
```javascript 
// ES5
function greet() {
  return function(name) {
    console.log('Hello, ' + name + '!');
  };
}

// ES6
const greet = () => (name) => {
  console.log(`Hello, ${name}!`);
};
```
In ES6, arrow functions provide a concise syntax, especially when returning functions from other functions. You can use arrow function expressions to define functions more succinctly.

+ 3. Higher-Order Functions:
```javascript
// ES5
const numbers = [1, 2, 3, 4, 5];
const squared = numbers.map(function(x) {
  return x * x;
});

// ES6
const squared = numbers.map(x => x * x);
```
Arrow functions are particularly useful in higher-order functions like `map`, `filter`, and `reduce`. They allow you to write shorter and more readable code when performing operations on arrays.

### Use ES6 modules to organize and share code across different files
ES6 modules provide a standardized way to work with modules in JavaScript, allowing you to export and import functionality between files.

```javascript
// myModule.js
// Exporting a function as the default export
export default function greet(name) {
    return `Hello, ${name}!`;
}

// Exporting a constant
export const PI = 3.14159;

// Exporting a function
export function square(x) {
    return x * x;
}
```

```javascript
// Importing the default export
import greet from './myModule.js';

console.log(greet('Alice')); // Output: Hello, Alice!

// Importing named exports
import { PI, square } from './myModule.js';

console.log(PI); // Output: 3.14159
console.log(square(5)); // Output: 25
```
+ We have a module script called myModule.js which exports a default function greet, a constant PI, and a function square.
+ In another script, we import the default export greet using import greet from './myModule.js';. Since it's the default export, we can import it without using curly braces {}.
+ We also import named exports PI and square using import { PI, square } from './myModule.js';. Since they are named exports, we need to use curly braces {} to specify which exports we want to import.


## Javascript Promises
JavaScript Promises provide a way to work with asynchronous operations in a more structured and manageable manner. Promises have three states: pending, fulfilled, and rejected.

+ ***Pending***: The initial state of a promise. It represents the state of a promise when it's created but hasn't been fulfilled or rejected yet.
+ ***Fulfilled***: The state of a promise when the asynchronous operation associated with it is `successfully` completed. If the promise is fulfilled, it means that the operation it represents was successful.
+ ***Rejected***: The state of a promise when the asynchronous operation associated with it encounters an error or fails. If the promise is `rejected`, it means that the operation it represents encountered an error.


### Handling Fulfilled Promises with then:
You can handle `fulfilled` promises using the `then` method. The then method takes two optional callback functions as arguments: onFulfilled and onRejected.

+ ***onFulfilled***: This callback function is called when the promise is fulfilled. It receives the resolved value of the promise as its argument.
+ ***onRejected***: This callback function is called when the promise is rejected. It receives the rejection reason as its argument.

```javascript
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve('Operation successful'); // Fulfill the promise after a timeout
  }, 2000);
});

promise.then(
  (result) => {
    console.log('Fulfilled:', result); // Output: Fulfilled: Operation successful
  },
  (error) => {
    console.error('Rejected:', error);
  }
);
```

### Handling Rejected Promises with catch:

You can handle rejected promises using the catch method. The catch method is called when the promise is rejected. It takes a single callback function as its argument, which receives the rejection reason as its argument.

```javascript
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    reject('Error: Operation failed'); // Reject the promise after a timeout
  }, 2000);
});

promise.catch((error) => {
  console.error('Caught error:', error); // Output: Caught error: Error: Operation failed
});
```

## Functional programming 
Functional programming is a style of programming where solutions are simple, isolated functions, without any side effects outside of the function scope: `INPUT` -> `PROCESS` -> `OUTPUT`
+ Functional programming is about:
    - **Isolated functions** - there is no dependence on the state of the program, which includes global variables that are subject to change
    - ***Pure functions*** - the same input always gives the same output
    - ***Functions with limited side effects*** - any changes, or mutations, to the state of the program outside the function are carefully controlled


### Lambda functions
Lambda functions, also known as anonymous functions or arrow functions, are a concise way to write functions in many programming languages, including JavaScript. Lambda functions are typically used for short, simple functions where a full function declaration would be unnecessary or overly verbose.

```javascript
// Regular function declaration
function add(a, b) {
  return a + b;
}

// Lambda function (arrow function)
const addLambda = (a, b) => a + b;

console.log(add(2, 3)); // Output: 5
console.log(addLambda(2, 3)); // Output: 5
```

### Callback Functions

Callbacks in JavaScript are functions that are passed as arguments to other functions and are executed at a later time, often after an asynchronous operation has completed. Callbacks are commonly used to handle asynchronous code, such as fetching data from a server, reading files, or executing timed events.
```javascript
function fetchData(callback) {
  // Simulating asynchronous operation (e.g., fetching data from a server)
  setTimeout(() => {
    const data = 'Some data';
    callback(data); // Call the callback function with the fetched data
  }, 2000);
}

// Define a callback function
function processData(data) {
  console.log('Data received:', data);
}

// Call the fetchData function and pass the processData function as a callback
fetchData(processData);
```
When the asynchronous operation completes (after 2 seconds in this case), the callback function (processData) is invoked with the fetched data. This allows us to handle the data asynchronously, ensuring that our code continues to run without blocking while waiting for the operation to complete.


### First class functions
First-class functions are a concept in programming languages where functions are treated as first-class citizens, meaning they can be treated like any other variable. In languages with first-class functions, functions can be:

+ Assigned to variables.
+ Passed as arguments to other functions.
+ Returned from other functions.
+ Stored in data structures.

```javascript
// Assigned to Variables:
const add = function(a, b) {
  return a + b;
};
console.log(add(2, 3)); // Output: 5


// Passed as Arguments:
function greet(name) {
  console.log('Hello, ' + name + '!');
}
function processName(callback) {
  const name = 'Alice';
  callback(name);
}
processName(greet); // Output: Hello, Alice!

// Returned from Functions:
function createMultiplier(factor) {
  return function(x) {
    return x * factor;
  };
}
const double = createMultiplier(2);
console.log(double(5)); // Output: 10

// Stored in Data Structures:
const operations = {
  add: function(a, b) {
    return a + b;
  },
  subtract: function(a, b) {
    return a - b;
  }
};
console.log(operations.add(2, 3)); // Output: 5
console.log(operations.subtract(5, 2)); // Output: 3
```

### Higher-order function
A higher-order function is a function that either takes one or more functions as arguments or returns a function as its result. In other words, it's a function that operates on other functions by taking them as arguments or by returning them.

+ Functions as Arguments:

```javascript
function operationOnNumbers(numbers, operation) {
  let result = 0;
  for (let number of numbers) {
    result += operation(number);
  }
  return result;
}

function square(number) {
  return number * number;
}

const numbers = [1, 2, 3, 4, 5];
console.log(operationOnNumbers(numbers, square)); // Output: 55 (1^2 + 2^2 + 3^2 + 4^2 + 5^2)
```

+ Functions as Return Values:
```javascript
function createMultiplier(factor) {
  return function(number) {
    return number * factor;
  };
}

const double = createMultiplier(2);
console.log(double(5)); // Output: 10
```

### Array methods in JavaScript 

+ ***map***:
The `map` method creates a new array by applying a function to each element of the original array.
```javascript
const numbers = [1, 2, 3, 4, 5];

const squaredNumbers = numbers.map((number) => number * number);

console.log(squaredNumbers); // Output: [1, 4, 9, 16, 25]
```
The `map` method takes a callback function as an argument, which is applied to each element of the array. The callback function receives three arguments: the current element, the index of the current element, and the array being traversed.

+ ***filter***:
The `filter` method creates a new array with all elements that pass the test implemented by the provided function.

```javascript
const numbers = [1, 2, 3, 4, 5];

const evenNumbers = numbers.filter((number) => number % 2 === 0);

console.log(evenNumbers); // Output: [2, 4]
```
The `filter` method also takes a callback function as an argument, which returns true to keep the element, or false otherwise.

+ ***slice***:
The `slice` method returns a shallow copy of a portion of an array into a new array object.
```javascript
const numbers = [1, 2, 3, 4, 5];

const slicedNumbers = numbers.slice(1, 3);

console.log(slicedNumbers); // Output: [2, 3]
```
The slice method takes two arguments: the starting index (inclusive) and the ending index (exclusive) of the portion to be sliced.


+ ***splice***: 
The `splice` method changes the contents of an array by removing or replacing existing elements and/or adding new elements in place.
```javascript
const numbers = [1, 2, 3, 4, 5];

const removedNumbers = numbers.splice(1, 2);

console.log(removedNumbers); // Output: [2, 3]
console.log(numbers); // Output: [1, 4, 5]
```
The `splice` method takes three arguments: the starting index, the number of elements to remove, and optional new elements to add.

+ ***concat***: 
The `concat` method is used to merge two or more arrays, returning a new array without modifying the existing arrays.
```javascript
const numbers1 = [1, 2];
const numbers2 = [3, 4];
const numbers3 = [5, 6];

const mergedNumbers = numbers1.concat(numbers2, numbers3);

console.log(mergedNumbers); // Output: [1, 2, 3, 4, 5, 6]
```
The `concat` method can accept any number of arrays or values as arguments.


+ ***join***:
The `join` method joins all elements of an array into a string.
```javascript
const fruits = ['Apple', 'Banana', 'Orange'];

const joinedFruits = fruits.join(', ');

console.log(joinedFruits); // Output: "Apple, Banana, Orange"
```
The `join` method takes an optional separator string as an argument, which specifies how to separate the elements in the resulting string.

+ ***every***:
The `every` method tests whether all elements in the array pass the provided function.

```javascript
const numbers = [2, 4, 6, 8, 10];

const allEven = numbers.every((number) => number % 2 === 0);

console.log(allEven); // Output: true
```
The `every` method takes a callback function as an argument, which tests each element in the array. It returns true if all elements pass the test, or false otherwise.

+ ***some***:
The `some` method tests whether at least one element in the array passes the provided function.

```javascript
const numbers = [1, 3, 5, 7, 8];

const hasEvenNumber = numbers.some((number) => number % 2 === 0);

console.log(hasEvenNumber); // Output: true
```
The `some` method also takes a callback function as an argument and returns true if at least one element passes the test, or false otherwise.

+ ***split***:
The `split` method is used to split a string into an array of substrings based on a specified separator and returns a new array.
```javascript
const sentence = 'The quick brown fox jumps over the lazy dog';

const words = sentence.split(' ');

console.log(words);
// Output: ['The', 'quick', 'brown', 'fox', 'jumps', 'over', 'the', 'lazy', 'dog']
```
In this example, the `split` method splits the sentence string into an array of words based on the space character (' ') separator.

+ ***sort***:
The `sort` method is used to sort the elements of an array in place and returns the sorted array.
```javascript
const numbers = [3, 1, 4, 1, 5, 9, 2, 6, 5];

const sortedNumbers = numbers.slice().sort((a, b) => a - b);

console.log(sortedNumbers); // Output: [1, 1, 2, 3, 4, 5, 5, 6, 9]
```
In this example, the `slice` method is used to create a shallow copy of the original numbers array to avoid modifying it directly. Then, the `sort` method is called on the copied array to sort its elements in ascending order. The sort method takes an optional comparison function as an argument to specify the sorting order.











































