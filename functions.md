```js
// Function Declarations (hoisted)

function greet(name) {
  return "Hello, " + name + "!";
}

console.log(greet("Alice")); // Output: Hello, Alice!

// Function Expressions (not hoisted)

const sayHello = function(name) {
  return "Hello, " + name + "!";
};

console.log(sayHello("Bob")); // Output: Hello, Bob!

// Arrow Functions (concise syntax)

const greetArrow = (name) => {
  return "Hello, " + name + "!";
};

console.log(greetArrow("Charlie")); // Output: Hello, Charlie!

// More concise arrow function (implicit return if only one expression)
const greetConcise = name => "Hello, " + name + "!";

console.log(greetConcise("David")); // Output: Hello, David!

// Arrow function with no arguments
const sayHi = () => "Hi there!";
console.log(sayHi()); // Output: Hi there!

// Function Parameters and Arguments

function add(a, b) { // a and b are parameters
  return a + b;
}

let sum = add(5, 3); // 5 and 3 are arguments
console.log(sum); // Output: 8

// Default Parameters (ES6)

function multiply(a, b = 1) { // b has a default value of 1
  return a * b;
}

console.log(multiply(5)); // Output: 5 (b defaults to 1)
console.log(multiply(5, 2)); // Output: 10

// Rest Parameter (ES6) (collects multiple arguments into an array)

function sumAll(...numbers) {
  let total = 0;
  for (let number of numbers) {
    total += number;
  }
  return total;
}

console.log(sumAll(1, 2, 3)); // Output: 6
console.log(sumAll(1, 2, 3, 4, 5)); // Output: 15

// The arguments object (available inside non-arrow functions, but rest parameter is preferred)
function showArguments() {
    console.log(arguments)
}

showArguments(1,2,3); // Output: Arguments(3) [1, 2, 3, callee: ƒ, Symbol(Symbol.iterator): ƒ]

// Immediately Invoked Function Expressions (IIFE)
(function() {
  console.log("This is an IIFE"); // Output: This is an IIFE
})();

// IIFE with arrow function
(() => {
    console.log("This is an IIFE with arrow function"); // Output: This is an IIFE with arrow function
})();

// Functions are first-class citizens (can be assigned to variables, passed as arguments, returned from other functions)
const myFunc = greet;
console.log(myFunc("Eve")); // Output: Hello, Eve!

function callFunction(func, arg) {
    return func(arg);
}
console.log(callFunction(greet, "Frank")); // Output: Hello, Frank!

function createMultiplier(multiplier) {
    return function(number) {
        return number * multiplier;
    }
}

const double = createMultiplier(2);
console.log(double(5)); // Output: 10

const triple = createMultiplier(3);
console.log(triple(5)); // Output: 15
```
