# A Guide to JavaScript
## Introduction:
JavaScript is a versatile programming language commonly used in web development. It allows developers to create dynamic and interactive web pages. In this guide, we'll cover the fundamentals of JavaScript, starting from the basics and progressing to more advanced topics.

## Data Types 
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

+ ***number***: The `number` data type represents numeric values, both integers and floating-point numbers.

```javascript
let integerNumber = 42;
let floatingPointNumber = 3.14;
console.log(typeof integerNumber); // Output: number
console.log(typeof floatingPointNumber); // Output: number
```

+ ***object***: The `object` data type represents a collection of key-value pairs, where keys are strings (or symbols) and values can be any data type.

```javascript
let person = {
    name: 'John',
    age: 30,
    isStudent: false
};
console.log(typeof person); // Output: object

```