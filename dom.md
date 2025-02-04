```js
// DOM manipulation: creating, changing, querying, removing, and handling events

// Creating a new element:
const newParagraph = document.createElement('p');

// Changing the text content of an element:
newParagraph.textContent = 'This is a new paragraph!';

// Alternatively, using innerHTML (be careful of XSS vulnerabilities if inserting user-provided content):
// newParagraph.innerHTML = 'This is a <strong>new</strong> paragraph!';

// Setting an attribute:
newParagraph.setAttribute('id', 'myParagraph');
newParagraph.classList.add('highlighted'); // Adding a class

// Getting an attribute:
const paragraphId = newParagraph.getAttribute('id');
const hasHighlight = newParagraph.classList.contains('highlighted'); // Checking class

// Querying elements:
const elementById = document.getElementById('myParagraph'); // Get by ID (fastest)
const elementsByClass = document.getElementsByClassName('highlighted'); // Get by class name (returns a live HTMLCollection)
const elementsByTag = document.getElementsByTagName('p'); // Get by tag name (returns a live HTMLCollection)
const firstParagraph = document.querySelector('p'); // Get the first matching element using CSS selectors
const allParagraphs = document.querySelectorAll('p'); // Get all matching elements using CSS selectors (returns a NodeList)

// Appending the new paragraph to the body:
document.body.appendChild(newParagraph);

// Inserting before another element:
const anotherParagraph = document.createElement('p');
anotherParagraph.textContent = "I'm another paragraph";
document.body.insertBefore(anotherParagraph, newParagraph); // Insert before newParagraph

// Removing an element:
// newParagraph.remove(); // Modern way
// document.body.removeChild(newParagraph); // Older way (requires parent)

// Event handling:
const button = document.createElement('button');
button.textContent = 'Click me!';
document.body.appendChild(button);

button.addEventListener('click', function(event) {
  console.log('Button clicked!', event);
  // event.target refers to the button itself
  event.target.textContent = 'Clicked!';

  // Example of accessing event properties
  console.log("ClientX: ", event.clientX);
  console.log("ClientY: ", event.clientY);


});

// More concise event listener using an arrow function:
button.addEventListener('mouseover', (event) => {
    console.log("Mouse over!");
});


// Removing Event Listener (important to prevent memory leaks)
// button.removeEventListener('click', theClickHandlerFunction); // Where theClickHandlerFunction is a reference to the original function passed in addEventListener
```
