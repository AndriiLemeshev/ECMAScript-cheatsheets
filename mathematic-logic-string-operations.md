```js
// Mathematical Operators

// Addition
2 + 3; // = 5

// Subtraction
5 - 2; // = 3

// Multiplication
4 * 6; // = 24

// Division
10 / 2; // = 5

// Modulus (remainder)
10 % 3; // = 1

// Exponentiation (ES2016)
2 ** 3; // = 8 (2 * 2 * 2)

// Increment/Decrement
let x = 5;
x++; // x = 6 (post-increment)
++x; // x = 7 (pre-increment)
x--; // x = 6 (post-decrement)
--x; // x = 5 (pre-decrement)

// Assignment operators
let y = 10;
y += 5; // y = 15 (y = y + 5)
y -= 3; // y = 12 (y = y - 3)
y *= 2; // y = 24 (y = y * 2)
y /= 4; // y = 6 (y = y / 4)
y %= 5; // y = 1 (y = y % 5)

// Logical Operators

// AND (&&)
true && true; // = true
true && false; // = false

// OR (||)
true || false; // = true
false || false; // = false

// NOT (!)
!true; // = false
!false; // = true

// Comparison Operators

// Equality (==) (performs type coercion)
5 == "5"; // = true

// Strict Equality (===) (does not perform type coercion)
5 === "5"; // = false
5 === 5; // = true

// Inequality (!=) (performs type coercion)
5 != "6"; // = true

// Strict Inequality (!==) (does not perform type coercion)
5 !== "5"; // = true

// Greater than (>)
10 > 5; // = true

// Less than (<)
5 < 10; // = true

// Greater than or equal to (>=)
10 >= 10; // = true

// Less than or equal to (<=)
5 <= 5; // = true

// String Operations

// Concatenation
"Hello" + " " + "World"; // = "Hello World"

// Template literals (with string interpolation)
const name = "Alice";
`Hello, ${name}!`; // = "Hello, Alice!"

// String methods (examples)
"hello".toUpperCase(); // = "HELLO"
"WORLD".toLowerCase(); // = "world"
" hello ".trim(); // = "hello" (removes whitespace from both ends)
"hello world".replace("world", "JavaScript"); // = "hello JavaScript"
"hello".charAt(0); // = "h"
"hello".substring(0, 3); // = "hel"
"hello".length; // = 5
"hello".includes("ell"); // = true
"hello".startsWith("he"); // = true
"hello".endsWith("lo"); // = true
```
