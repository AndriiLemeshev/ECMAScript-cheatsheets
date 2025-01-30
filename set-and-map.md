```js
// Set (ES6)

// A Set is a collection of unique values.

// Creating a Set
const mySet = new Set();

// Adding values
mySet.add(1);
mySet.add(2);
mySet.add(2); // Adding a duplicate has no effect
mySet.add("hello");
mySet.add({a: 1, b: 2});
const obj = {c: 3};
mySet.add(obj);
mySet.add(obj); // Adding the same object reference has no effect
mySet.add({c: 3}); // This is a different object, so it will be added

console.log(mySet); // Output: Set(5) {1, 2, "hello", {…}, {…}}

// Checking size
console.log(mySet.size); // Output: 5

// Checking if a value exists
console.log(mySet.has(2)); // Output: true
console.log(mySet.has(3)); // Output: false
console.log(mySet.has({a: 1, b: 2})); // Output: false because it's a different object with same content
console.log(mySet.has(obj)); // Output: true because it is the same object reference

// Deleting a value
mySet.delete(2);
console.log(mySet); // Output: Set(4) {1, "hello", {…}, {…}}

// Iterating over a Set
for (let item of mySet) {
  console.log(item); // Output: 1, "hello", {…}, {…}
}

// Converting a Set to an array
const myArrayFromSet = Array.from(mySet);
console.log(myArrayFromSet);

const mySetFromArray = new Set([1, 2, 2, 3, 3, 3]);
console.log(mySetFromArray); // Output: Set(3) {1, 2, 3}

// Clearing a Set
mySet.clear();
console.log(mySet); // Output: Set(0) {}

// Map (ES6)

// A Map is a collection of key-value pairs, where each key is unique.

// Creating a Map
const myMap = new Map();

// Setting key-value pairs
myMap.set("name", "John");
myMap.set(1, "Number one");
myMap.set(true, "A boolean");
const objMapKey = {key: "myKey"};
myMap.set(objMapKey, "object value");

console.log(myMap); // Output: Map(4) {"name" => "John", 1 => "Number one", true => "A boolean", {…} => "object value"}

// Getting a value by key
console.log(myMap.get("name")); // Output: John
console.log(myMap.get(1)); // Output: Number one
console.log(myMap.get(objMapKey)); // Output: object value
console.log(myMap.get({key: "myKey"})); // Output: undefined because it's a different object

// Checking size
console.log(myMap.size); // Output: 4

// Checking if a key exists
console.log(myMap.has("name")); // Output: true
console.log(myMap.has("age")); // Output: false

// Deleting a key-value pair
myMap.delete(1);
console.log(myMap); // Output: Map(3) {"name" => "John", true => "A boolean", {…} => "object value"}

// Iterating over a Map
// Iterating over keys
for (let key of myMap.keys()) {
    console.log("Key:", key);
}
// Iterating over values
for (let value of myMap.values()) {
    console.log("Value:", value);
}
// Iterating over entries (key-value pairs)
for (let [key, value] of myMap.entries()) {
  console.log("Key:", key, "Value:", value);
}
// Or using destructuring directly in the loop
for (const [key, value] of myMap) {
    console.log(`Key: ${key}, Value: ${value}`);
}

// Converting a Map to an array of entries
const myArrayFromMap = Array.from(myMap);
console.log(myArrayFromMap);

const myMapFromArray = new Map([["name", "John"], [1, "Number one"]]);
console.log(myMapFromArray); // Output: Map(2) {"name" => "John", 1 => "Number one"}

// Clearing a Map
myMap.clear();
console.log(myMap); // Output: Map(0) {}
```
