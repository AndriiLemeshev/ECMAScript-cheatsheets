```js
// Function binding: Controlling the 'this' context within functions

// The 'this' keyword:
// In regular functions, the value of 'this' is determined by how the function is called.

function regularFunction() {
  console.log('Regular function this:', this);
}

regularFunction(); // In non-strict mode, 'this' might refer to the global object (window in browsers) or undefined in strict mode.

const myObject = {
  name: 'My Object',
  myMethod: regularFunction,
};

myObject.myMethod(); // 'this' refers to myObject


// Arrow functions:
// Arrow functions do *not* have their own 'this' binding. They inherit the 'this' value from the surrounding (lexical) scope.

const arrowFunction = () => {
  console.log('Arrow function this:', this);
};

arrowFunction(); // 'this' will be the same as in the surrounding scope (often the global object or undefined).

myObject.arrowMethod = arrowFunction;
myObject.arrowMethod(); // Still refers to the surrounding scope, NOT myObject.

// Methods of Objects
const person = {
    name: "John",
    greet: function() {
        console.log("Hello, my name is " + this.name);
    },
    greetArrow: () => {
        console.log("Hello, my name is " + this.name); // 'this' will not refer to the person object
    }
};

person.greet(); // "Hello, my name is John"
person.greetArrow(); // "Hello, my name is undefined" or similar, depending on the environment.

// Binding 'this' explicitly:

// 1. .bind(): Creates a new function where 'this' is permanently bound to a specific value.

const boundFunction = regularFunction.bind(myObject);
boundFunction(); // 'this' will always be myObject, regardless of how boundFunction is called.

const anotherBoundFunction = regularFunction.bind({ value: "Another Value"});
anotherBoundFunction(); // 'this' will be { value: "Another Value" }

// 2. .call(): Calls a function directly, setting 'this' to the provided value.

regularFunction.call(myObject); // 'this' is myObject

// 3. .apply(): Similar to .call(), but accepts arguments as an array.

regularFunction.apply(myObject); // 'this' is myObject


// Example with event listeners:

const button = document.createElement('button');
button.textContent = 'Click me!';
document.body.appendChild(button);

const myClickHandler = function() {
  console.log('Button clicked!', this);  // 'this' will be the button element
    this.textContent = "Clicked!"; // Change the button text
}.bind(button); // Bind the button to 'this'

button.addEventListener('click', myClickHandler);

// Common Use Cases:

// - Event handlers: Ensuring 'this' refers to the element that triggered the event.
// - Class methods: Making sure 'this' refers to the class instance.
// - Asynchronous callbacks: Preserving the correct 'this' context within callbacks.
// - React event handlers: In React, using `.bind(this)` in class components is very common, or using arrow functions for implicit binding.
```
