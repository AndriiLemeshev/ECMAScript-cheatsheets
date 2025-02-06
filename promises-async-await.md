```js
// Promises: Handling asynchronous operations

// Creating a Promise:
const myPromise = new Promise((resolve, reject) => {
  // Asynchronous operation (e.g., fetching data, timer)
  setTimeout(() => {
    const success = true; // Or false, depending on the outcome

    if (success) {
      resolve('Data received!'); // Fulfills the promise
    } else {
      reject('Error fetching data!'); // Rejects the promise
    }
  }, 1000); // Simulate a 1-second delay
});

// Chaining Promises (using .then()):
myPromise
  .then(result => {
    console.log('First .then:', result); // Output: Data received!
    return 'Processed data'; // Return a value to chain another .then
  })
  .then(processedData => {
    console.log('Second .then:', processedData); // Output: Processed data
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve("More data");
      }, 500);
    });
  })
  .then(moreData => {
      console.log("Third then: ", moreData); // Output: More data
  })
  .catch(error => {
    console.error('Error handler:', error); // Handles any errors in the chain
  })
  .finally(() => {
    console.log('Finally block: This always runs.'); // Code that always executes, regardless of success or failure
  });


// Example using fetch (which returns a Promise):
fetch('https://localhost:3000/todos/1') // Example API endpoint
  .then(response => {
    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`); // Throw error for non-2xx responses
    }
    return response.json(); // Parse the JSON response
  })
  .then(data => {
    console.log('Fetch data:', data);
  })
  .catch(error => {
    console.error('Fetch error:', error);
  });


// Promise.all(): Run multiple promises concurrently:
const promise1 = Promise.resolve(10);
const promise2 = new Promise((resolve) => setTimeout(resolve, 200, 'foo'));
const promise3 = 1337;

Promise.all([promise1, promise2, promise3]).then((values) => {
  console.log(values); // [10, "foo", 1337]
});

// Promise.race(): Returns the result/error of the first settled promise
Promise.race([promise1, promise2]).then(value => {
    console.log("Race result: ", value); // 10
});


// Async/await (syntactic sugar for Promises):
async function fetchData() {
  try {
    const response = await fetch('https://localhost:3000/todos/1');
    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`);
    }
    const data = await response.json();
    console.log('Async/await data:', data);
    return data; // You can return values from an async function
  } catch (error) {
    console.error('Async/await error:', error);
    // Important: You can re-throw the error to propagate it up:
    throw error; // Or handle it appropriately.
  } finally {
      console.log("Async/await finally");
  }
}

fetchData().then(data => console.log("Data from async function: ", data)).catch(e => console.error("Error caught outside async function: ", e));
```
