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

## The differences between `let`, `var` and `const`
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
## The differences between `===` and `==`, as well as `!==` and `!=`
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

