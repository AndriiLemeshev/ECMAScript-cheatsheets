```js
// Ternary Operator

// Basic usage: condition ? valueIfTrue : valueIfFalse
let age = 20;
let message = age >= 18 ? "Adult" : "Minor"; // message will be "Adult"
console.log(message);

age = 15;
message = age >= 18 ? "Adult" : "Minor"; // message will be "Minor"
console.log(message);

// More complex example
let isMember = true;
let discount = isMember ? 0.1 : 0;
let finalPrice = 100 * (1 - discount);
console.log(`Final Price: ${finalPrice}`); // Output: Final Price: 90

// Chaining Ternary Operators (use with caution, can become hard to read)
let score = 75;
let grade = score >= 90 ? "A" : score >= 80 ? "B" : score >= 70 ? "C" : "D";
console.log(grade); // Output: C

score = 95;
grade = score >= 90 ? "A" : score >= 80 ? "B" : score >= 70 ? "C" : "D";
console.log(grade); // Output: A

// AVOID deeply nested ternary chains for readability. Use if/else if/else instead.
// Example of how to rewrite the above using if/else if/else for better readability:
/*
let grade;
if (score >= 90) {
    grade = "A";
} else if (score >= 80) {
    grade = "B";
} else if (score >= 70) {
    grade = "C";
} else {
    grade = "D";
}
*/

// Null and Logical Operators

// Nullish Coalescing Operator (??) (ES2020)
// Returns the right-hand side operand when the left-hand side is null or undefined. Otherwise, it returns the left-hand side operand.
let userName = null;
let displayName = userName ?? "Guest"; // displayName will be "Guest"

userName = "John";
displayName = userName ?? "Guest"; // displayName will be "John"

let userAge; // undefined
let displayAge = userAge ?? 25; // displayAge will be 25

let userScore = 0;
let finalUserScore = userScore ?? 100; // finalUserScore is 0 because 0 is not null or undefined

// Optional Chaining Operator (?.) (ES2020)
// Safely accesses nested object properties without throwing an error if an intermediate property is null or undefined.
const user = {
  address: {
    street: "123 Main St"
  }
};

// Without optional chaining, this would throw an error if user.address was null/undefined:
// console.log(user.address.city); // Error: Cannot read properties of undefined (reading 'city')

// With optional chaining:
console.log(user?.address?.city); // Output: undefined (no error)

const user2 = null;
console.log(user2?.address?.city); // Output: undefined (no error)

const user3 = {
  address: {
    city: "New York"
  }
};
console.log(user3?.address?.city); // Output: New York

// Logical OR (||) vs. Nullish Coalescing (??)
// The || operator returns the right-hand side operand when the left-hand side is *any* falsy value (0, "", NaN, null, undefined).
// The ?? operator *only* returns the right-hand side operand when the left-hand side is null or undefined.

let value = 0;
let resultOr = value || 10; // resultOr will be 10 (because 0 is falsy)
let resultNullish = value ?? 10; // resultNullish will be 0 (because 0 is neither null nor undefined)

value = "";
resultOr = value || "default"; // resultOr will be "default" (because "" is falsy)
resultNullish = value ?? "default"; // resultNullish will be "" (because "" is neither null nor undefined)
```
