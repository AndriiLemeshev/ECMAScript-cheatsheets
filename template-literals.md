```js
// Template Literal Tagged Functions

// Template literal tagged functions allow you to intercept and process template literals before they are converted to strings.

// Basic example: a tag function that converts all strings to uppercase
function toUpper(strings, ...values) {
    let result = "";
    for (let i = 0; i < strings.length; i++) {
        result += strings[i].toUpperCase();
        if (i < values.length) {
            result += values[i];
        }
    }
    return result;
}

const name = "John";
const greeting = toUpper`Hello, ${name}!`;
console.log(greeting); // Output: HELLO, JOHN!

// Example with HTML escaping:
function htmlEscape(strings, ...values) {
    let result = "";
    for (let i = 0; i < strings.length; i++) {
        result += strings[i];
        if (i < values.length) {
            result += String(values[i])
                .replace(/&/g, "&amp;")
                .replace(/</g, "&lt;")
                .replace(/>/g, "&gt;")
                .replace(/"/g, "&quot;")
                .replace(/'/g, "&#039;");
        }
    }
    return result;
}

const unsafeInput = "<script>alert('XSS!');</script>";
const safeOutput = htmlEscape`<div>${unsafeInput}</div>`;
console.log(safeOutput); // Output: <div>&lt;script&gt;alert('XSS!');&lt;/script&gt;</div>

// Example with raw property:
function showRaw(strings, ...values) {
    console.log(strings.raw); // Shows the raw template string values (including escape sequences)
    return "Processed String"; // The function must return a string.
}

showRaw`This is a \n multiline \t string.`;
/* Output:
[
  'This is a \n multiline \t string.',
  raw: [ 'This is a \\n multiline \\t string.' ]
]
*/

// Example with formatting:
function formatCurrency(strings, ...values) {
    let result = "";
    for (let i = 0; i < strings.length; i++) {
        result += strings[i];
        if (i < values.length) {
            const value = values[i];
            if (typeof value === 'number') {
                result += value.toLocaleString("en-US", {style: "currency", currency: "USD"});
            } else {
                result += value; // Don't format non-numbers
            }
        }
    }
    return result;
}

const price = 1234.56;
const message = formatCurrency`The price is ${price}.`;
console.log(message); // Output: The price is $1,234.56.

const name2 = "Bob";
const message2 = formatCurrency`Hello ${name2}, the price is ${price}.`;
console.log(message2); // Output: Hello Bob, the price is $1,234.56.

// Key points:
// - The first argument to a tagged function is an array of the string parts of the template literal.
// - Subsequent arguments are the values of the expressions.
// - The function must return a string.
// - The `strings.raw` property gives access to the raw string values (without processing escape sequences).
```
