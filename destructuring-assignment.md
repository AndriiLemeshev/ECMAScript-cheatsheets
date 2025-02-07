```js
// Destructuring assignment: A concise way to extract values from objects and arrays

// Object destructuring:
const person = {
  name: 'Alice',
  age: 30,
  city: 'New York',
  address: {
    street: "123 Main St",
    zip: "10001"
  }
};

const { name, age, city } = person; // Extract name, age, and city
console.log(name, age, city); // Output: Alice 30 New York

// Aliasing:
const { name: personName, age: personAge } = person; // Rename the variables
console.log(personName, personAge); // Output: Alice 30

// Default values:
const { country = 'USA' } = person; // If 'country' is not defined, default to 'USA'
console.log(country); // Output: USA

// Nested object destructuring:
const { address: { street, zip } } = person;
console.log(street, zip); // Output: 123 Main St 10001

// Rest operator:
const { name, ...rest } = person; // Gather the remaining properties into 'rest'
console.log(name); // Output: Alice
console.log(rest); // Output: { age: 30, city: 'New York', address: {street: "123 Main St", zip: "10001"} }

// Array destructuring:
const numbers = [1, 2, 3, 4, 5];

const [first, second, , fourth] = numbers; // Extract the first, second, and fourth elements (skip the third)
console.log(first, second, fourth); // Output: 1 2 4

// Rest operator with arrays:
const [a, b, ...remaining] = numbers;
console.log(a, b); // Output: 1 2
console.log(remaining); // Output: [3, 4, 5]

// Combining object and array destructuring
const complexObject = {
    name: "Bob",
    details: {
        addresses: ["1st address", "2nd address"]
    }
};

const { name: bobName, details: {addresses: [firstAddress, secondAddress]}} = complexObject;
console.log(bobName, firstAddress, secondAddress); // Bob 1st address 2nd address

// Destructuring function arguments:
function greet({ name, age }) {
  console.log(`Hello, ${name}! You are ${age} years old.`);
}

greet(person); // Output: Hello, Alice! You are 30 years old.

// Destructuring in loops:
const people = [{ name: 'Charlie', age: 25 }, { name: 'David', age: 40 }];

for (const { name, age } of people) {
  console.log(`${name} is ${age}.`);
}
// Output:
// Charlie is 25.
// David is 40.
```
