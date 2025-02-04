```js
// LocalStorage and SessionStorage: Storing data in the browser

// LocalStorage: Data persists across browser sessions
localStorage.setItem('myKey', 'myValue'); // Store a key-value pair
const storedValue = localStorage.getItem('myKey'); // Retrieve the value
console.log(storedValue); // Output: myValue

localStorage.removeItem('myKey'); // Remove a specific item
// localStorage.clear(); // Clear all items in localStorage

// Example of storing an object (must be stringified):
const myObject = { name: 'John', age: 30 };
localStorage.setItem('myObject', JSON.stringify(myObject));
const retrievedObject = JSON.parse(localStorage.getItem('myObject'));
console.log(retrievedObject.name); // Output: John


// SessionStorage: Data is cleared when the browser tab or window is closed
sessionStorage.setItem('mySessionKey', 'mySessionValue');
const sessionValue = sessionStorage.getItem('mySessionKey');
console.log(sessionValue); // Output: mySessionValue

sessionStorage.removeItem('mySessionKey');
// sessionStorage.clear(); // Clears all items in session storage

// Key Differences:
// - LocalStorage: Persistent storage. Data remains even after the browser is closed and reopened.  Useful for things like remembering user preferences or keeping a user logged in (with appropriate security measures).
// - SessionStorage: Temporary storage. Data is cleared when the current session ends (the tab or window is closed). Useful for storing temporary data related to the user's current interaction with the site, like form data that you don't want to persist across sessions or items in a shopping cart.

// Important Considerations:
// - Storage Limits: Both localStorage and sessionStorage have storage limits (typically around 5-10MB, but it varies by browser).  Don't try to store large amounts of data.
// - Security:  Be mindful of what you store in localStorage, especially sensitive information. While the data is not directly accessible to other websites (due to the same-origin policy), it can be vulnerable to client-side attacks (like cross-site scripting - XSS) if your site is not properly secured.  Avoid storing sensitive data like passwords or credit card details directly in localStorage.  Consider using HTTP-only cookies for sensitive data.
// - Performance: Accessing localStorage can be synchronous and potentially block the main thread, especially if you're dealing with a lot of data.  For better performance, consider using asynchronous APIs like IndexedDB for larger datasets.
```
