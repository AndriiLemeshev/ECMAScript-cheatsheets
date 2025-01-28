```js
// Type Conversions (Type Coercion and Type Casting)

// Type Coercion (automatic conversion by JavaScript)

// String coercion
let value = 5;
let strValue = "The value is " + value; // value is coerced to a string
console.log(strValue); // Output: The value is 5

let sumString = "5" + 3; // 3 is coerced to a string
console.log(sumString); // Output: 53

let sumString2 = 5 + "3"; // 5 is coerced to a string
console.log(sumString2); // Output: 53

// Numeric coercion
let strNum = "10";
let numValue = strNum - 5; // strNum is coerced to a number
console.log(numValue); // Output: 5

let strNum2 = "10";
let numValue2 = strNum2 * 2; // strNum2 is coerced to a number
console.log(numValue2); // Output: 20

let strNum3 = "10";
let numValue3 = strNum3 / 2; // strNum3 is coerced to a number
console.log(numValue3); // Output: 5

let strNum4 = "10";
let numValue4 = strNum4 + 2; // strNum4 is NOT coerced to a number because of the + operator
console.log(numValue4); // Output: 102

// Boolean coercion (in conditional statements and logical operations)
if ("hello") { // "hello" is coerced to true (any non-empty string is truthy)
  console.log("String is truthy"); // Output: String is truthy
}

if (0) { // 0 is coerced to false
    console.log("This will not be printed");
}

if (1) { // 1 is coerced to true
    console.log("This will be printed"); // Output: This will be printed
}

if ("") { // empty string is coerced to false
    console.log("This will not be printed");
}

if (null) { // null is coerced to false
    console.log("This will not be printed");
}

if (undefined) { // undefined is coerced to false
    console.log("This will not be printed");
}

if (NaN) { // NaN is coerced to false
    console.log("This will not be printed");
}

// Type Casting (explicit conversion)

// String()
let numToString = String(123); // Converts a number to a string
console.log(typeof numToString); // Output: string
console.log(numToString); // Output: "123"

let boolToString = String(true); // Converts a boolean to a string
console.log(typeof boolToString); // Output: string
console.log(boolToString); // Output: "true"

// Number()
let strToNum = Number("456"); // Converts a string to a number
console.log(typeof strToNum); // Output: number
console.log(strToNum); // Output: 456

let boolToNum = Number(false); // Converts a boolean to a number (true is 1, false is 0)
console.log(typeof boolToNum); // Output: number
console.log(boolToNum); // Output: 0

let boolToNum2 = Number(true); // Converts a boolean to a number (true is 1, false is 0)
console.log(typeof boolToNum2); // Output: number
console.log(boolToNum2); // Output: 1

let strToNumNaN = Number("hello"); // If the string cannot be converted, it returns NaN
console.log(typeof strToNumNaN); // Output: number
console.log(isNaN(strToNumNaN)); // Output: true

// parseInt() and parseFloat() (for parsing strings to numbers)
let strToInt = parseInt("100px"); // Parses an integer from a string, stops at the first non-digit
console.log(strToInt); // Output: 100

let strToFloat = parseFloat("3.14meters"); // Parses a floating-point number
console.log(strToFloat); // Output: 3.14

// Boolean()
let strToBool = Boolean("hello"); // Converts a string to a boolean (empty string is false, any other string is true)
console.log(strToBool); // Output: true

let numToBool = Boolean(0); // Converts a number to a boolean (0 is false, any other number is true)
console.log(numToBool); // Output: false

let numToBool2 = Boolean(123); // Converts a number to a boolean (0 is false, any other number is true)
console.log(numToBool2); // Output: true

let nullToBool = Boolean(null); // null is coerced to false
console.log(nullToBool); // Output: false

let undefinedToBool = Boolean(undefined); // undefined is coerced to false
console.log(undefinedToBool); // Output: false
```
