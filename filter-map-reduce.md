```js
// Array Methods: filter, map, reduce, join

const numbers = [1, 2, 3, 4, 5, 6];

// filter(): Creates a new array with all elements that pass the test implemented by the provided function.

const evenNumbers = numbers.filter(number => number % 2 === 0);
console.log(evenNumbers); // Output: [2, 4, 6]

const oddNumbers = numbers.filter(number => number % 2 !== 0);
console.log(oddNumbers); // Output: [1, 3, 5]

const greaterThanThree = numbers.filter(number => number > 3);
console.log(greaterThanThree); // Output: [4, 5, 6]

// map(): Creates a new array populated with the results of calling a provided function on every element in the calling array.

const doubledNumbers = numbers.map(number => number * 2);
console.log(doubledNumbers); // Output: [2, 4, 6, 8, 10, 12]

const stringifiedNumbers = numbers.map(number => String(number));
console.log(stringifiedNumbers); // Output: ['1', '2', '3', '4', '5', '6']

const numbersPlusOne = numbers.map(number => number + 1);
console.log(numbersPlusOne); // Output: [2, 3, 4, 5, 6, 7]

// reduce(): Executes a reducer function (that you provide) on each element of the array, resulting in a single output value.

const sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0); // 0 is the initial value of the accumulator
console.log(sum); // Output: 21 (1+2+3+4+5+6)

const product = numbers.reduce((accumulator, currentValue) => accumulator * currentValue, 1); // 1 is the initial value of the accumulator
console.log(product); // Output: 720 (1*2*3*4*5*6)

const max = numbers.reduce((accumulator, currentValue) => Math.max(accumulator, currentValue));
console.log(max); // Output: 6

const min = numbers.reduce((accumulator, currentValue) => Math.min(accumulator, currentValue));
console.log(min); // Output: 1

// Example with an empty array. If no initial value is provided reduce will throw an error
// const emptyArray = [];
// const sumEmpty = emptyArray.reduce((accumulator, currentValue) => accumulator + currentValue); // Error: Reduce of empty array with no initial value
const sumEmptyWithInitialValue = [].reduce((accumulator, currentValue) => accumulator + currentValue, 0); // Correct way to handle empty arrays
console.log(sumEmptyWithInitialValue); // Output: 0

// join(): Creates and returns a new string by concatenating all of the elements in an array (or an array-like object), separated by commas or a specified separator string.

const joinedNumbers = numbers.join(); // Default separator is a comma
console.log(joinedNumbers); // Output: "1,2,3,4,5,6"
console.log(typeof joinedNumbers); // Output: string

const joinedNumbersWithSeparator = numbers.join("-");
console.log(joinedNumbersWithSeparator); // Output: "1-2-3-4-5-6"

const joinedNumbersWithEmptySeparator = numbers.join("");
console.log(joinedNumbersWithEmptySeparator); // Output: "123456"

const words = ["Hello", "World", "!"];
const joinedWords = words.join(" ");
console.log(joinedWords); // Output: "Hello World !"
```
