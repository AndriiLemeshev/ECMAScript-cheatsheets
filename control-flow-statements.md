```js
// Conditional Statements

// if statement
let age = 20;
if (age >= 18) {
  console.log("Adult");
}

// if...else statement
if (age >= 18) {
  console.log("Adult");
} else {
  console.log("Minor");
}

// if...else if...else statement
let score = 75;
if (score >= 90) {
  console.log("A");
} else if (score >= 80) {
  console.log("B");
} else if (score >= 70) {
  console.log("C");
} else {
  console.log("D");
}

// Ternary operator (shorthand for if...else)
let isMember = true;
let discount = isMember ? 0.1 : 0; // discount = 0.1 if isMember is true, 0 otherwise
console.log(`Discount: ${discount}`);

// switch statement
let day = "Monday";
switch (day) {
  case "Monday":
    console.log("Start of the week");
    break;
  case "Friday":
    console.log("Almost weekend");
    break;
  default:
    console.log("Another day");
}

// Loops

// for loop
for (let i = 0; i < 5; i++) {
  console.log(i); // Output: 0, 1, 2, 3, 4
}

// for...in loop (iterating over object properties)
const person = { name: "Bob", age: 30, city: "London" };
for (let key in person) {
  console.log(key + ": " + person[key]); // Output: name: Bob, age: 30, city: London
}

// for...of loop (iterating over iterable objects like arrays, strings, maps, sets, etc.)
const numbers = [10, 20, 30];
for (let number of numbers) {
  console.log(number); // Output: 10, 20, 30
}

const myString = "Hello";
for (const char of myString) {
    console.log(char); // Output: H, e, l, l, o
}

// Array forEach method (another way to iterate over arrays)
const colors = ["red", "green", "blue"];
colors.forEach(function(color) {
  console.log(color); // Output: red, green, blue
});

// forEach with arrow functions (more concise)
colors.forEach(color => console.log(color)); // Output: red, green, blue

// while loop
let counter = 0;
while (counter < 3) {
  console.log("While loop: " + counter); // Output: While loop: 0, While loop: 1, While loop: 2
  counter++;
}

// do...while loop (executes the code block at least once)
let count = 0;
do {
  console.log("Do...while loop: " + count); // Output: Do...while loop: 0, Do...while loop: 1, Do...while loop: 2
  count++;
} while (count < 3);
```
