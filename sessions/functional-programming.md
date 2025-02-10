# Practical Functional Programming with ECMAScript
*by Andrii Lemeshev*

# What is Functional Programming (FP)?
- Pure Functions;
- Immutability;
- First-Class Functions;

# Pure Functions
```js
const pure = a => a + 1;

let b = 1;
const notPure = a => a + b;
console.log(notPure(1)); // Output: 2
b = 2;
console.log(notPure(1)); // Output: 3
```

# Pure Functions
 - depends only on arguments and immutable objects from its scope;

# Immutability
- primitives;
- constants;
- spread syntax;
- shallow freeze;

# Immutability (constants)
```js
const a = 1; // immutable
const b = {a: 1}; // object ointer is immutable
b.a = 2; // object fields are muttable;
```

# Immutability (spread syntax)
```js
// Spread syntax
const a = { x: 1 };
const b = { ...a, y: 2 };
const c = [ 1, 2 ];
const d = [ ...c, 3, 4 ];
```

# Immutability (shallow freeze)
```js
const frozenObj = Object.freeze({ name: "Alice" });
// frozenObj.name = "Bob"; // This will throw an error in strict mode.

const nestedObj = Object.freeze({ details: { city: "New York" } });
nestedObj.details.city = "London"; // This is still allowed because of shallow freeze!
```

# First-Class Functions
- assignment to variables;
- passing as arguments;
- returning from functions;
- storing in data structures;

# First-Class Functions (Assignment to Variables)
```js
const myFunction = function() {
    console.log("Hello!");
};

myFunction(); // Call the function
```

# First-Class Functions (Passing as Arguments)
```js
function greet(message, callback) {
    console.log(message);
    callback();
}

function sayHello() {
    console.log("Hello there!");
}

greet("Greetings", sayHello);  // Passing sayHello as an argument
```

# First-Class Functions (Returning from Functions)
```js
function createMultiplier(factor) {
    return function(x) {
        return x * factor;
    };
}

const double = createMultiplier(2);
console.log(double(5)); // Output: 10
```

# First-Class Functions (Storing in Data Structures)
```js
const myFunctions = [add, subtract, multiply]; // Assuming add, subtract, multiply are defined

const operations = {
    "+": add,
    "-": subtract,
    "*": multiply
};
```

# Benefits of FP
- readability
- maintainability;
- testability;
- reusability;

# Drawbacks of FP
- learning curve;
- performance;
- stack overflow issues;

# Patterns of FP
- higher-order functions (HOFs);
- composition;
- currying and partial application;
- recursion;
- referential transparency;
- monads;

# Higher-Order Functions (HOFs)
```js
// map: transforms each element of an array
const numbers = [1, 2, 3];
const doubled = numbers.map(x => x * 2); // [2, 4, 6]

// filter: creates a new array with elements that pass a test
const evens = numbers.filter(x => x % 2 === 0); // [2]

// reduce: combines elements into a single value
const sum = numbers.reduce((acc, curr) => acc + curr, 0); // 6
```

# Composition
```js
const addOne = x => x + 1;
const multiplyByTwo = x => x * 2;

// compose function (simplified)
const compose = (f, g) => x => f(g(x));

const addOneAndMultiplyByTwo = compose(multiplyByTwo, addOne);
console.log(addOneAndMultiplyByTwo(5)); // 12
```

# Currying and Partial Application
```js
const add = (a, b, c) => a + b + c;

// Currying (transforming into a chain of single-argument functions)
const curriedAdd = a => b => c => add(a, b, c); // Or more concise: a => b => c => a + b + c;

const add5 = curriedAdd(5); // Partial application (applying some arguments)
const add5and2 = add5(2);
console.log(add5and2(3)); // 10

// Partial application without full currying
const add5Partial = (a, b) => add(5, a, b);
console.log(add5Partial(2, 3)); // 10
```

# Recursion
```js
const factorial = n => {
  if (n === 0) {
    return 1;
  } else {
    return n * factorial(n - 1);
  }
};

console.log(factorial(5)); // 120
```


# Referential Transparency
```js
const addPure = (a, b) => a + b; // Pure function (referentially transparent)

const result1 = addPure(2, 3); // 5
const result2 = 5; // We can replace the function call with its result

console.log(result1 === result2); // true (The program's behavior doesn't change)
```


# Monads
```js
Promise.resolve(5)
  .then(x => x * 2)
  .then(y => {
      console.log("Result:", y); // Output: Result: 10
      return y + 1; // Return a value to be resolved
  })
  .then(z => console.log("Next Result", z)) // Output: Next Result 11
  .catch(error => console.error("Error:", error));
```

# Small tips
```js
const inc = x => x + 1;
class Test {
  increment(x) { return x + 1; }
}
const obj = new Test();

Promise.resolve(1)
  .then(inc) // pass function by pointer
  .then(x => obj.increment(x)); // wrap method in arrow function
```

# Q&A
