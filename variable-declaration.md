```js
// Declaring Variables

// var (function-scoped, can be redeclared and reassigned - generally avoid in modern JavaScript)
var x = 10;
var x = 20; // Redeclaration allowed
x = 30; // Reassignment allowed

// let (block-scoped, can be reassigned but not redeclared in the same scope)
let y = 10;
// let y = 20; // SyntaxError: Identifier 'y' has already been declared
y = 30; // Reassignment allowed

// const (block-scoped, cannot be redeclared or reassigned - must be initialized)
const z = 10;
// const z = 20; // SyntaxError: Identifier 'z' has already been declared
// z = 30; // TypeError: Assignment to constant variable

// Example of block scope
{
  let blockVar = "I'm in a block";
  const blockConst = 123;
  var functionVar = "I'm function-scoped";
}
// console.log(blockVar); // ReferenceError: blockVar is not defined
// console.log(blockConst); // ReferenceError: blockConst is not defined
console.log(functionVar); // Output: I'm function-scoped (if this line is within the same function)

// Declaring multiple variables at once
let a = 1, b = 2, c = 3;

// Destructuring assignment (more on this later, but useful to see here)
const person = { name: "Alice", age: 25 };
const { name, age } = person; // name = "Alice", age = 25

// Default values in destructuring
const { city = "Unknown" } = person; // city = "Unknown" (since person doesn't have a city property)
```
