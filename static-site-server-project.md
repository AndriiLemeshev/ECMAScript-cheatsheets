Here is a guide on setting up a Node.js project from scratch. This will cover the essential steps for a basic project, including setting up a `package.json`, installing dependencies, and creating a simple server.

**1. Create the Project Directory:**

First, create a directory for your project.  You can do this from your terminal or file explorer.  For example, in the terminal:

```bash
mkdir static-site-server-project
cd static-site-server-project
```

**2. Initialize a `package.json` file:**

The `package.json` file is essential for managing dependencies and scripts.  Initialize it using npm (Node Package Manager):

```bash
npm init -y  # The -y flag accepts all defaults
```

This will create a `package.json` file with default settings. You can later customize it as needed (e.g., change the description, author, etc.).

**3. Install Express.js (or other dependencies):**

Let's use Express.js for this example, as it's commonly used for web applications. Install it:

```bash
npm install express
```

This will add Express.js to your project's dependencies and update the `package.json` file. If you need other packages (e.g., `nodemon` for development), install them now as well:

```bash
npm install --save-dev nodemon  # For development only
```

**4. Create your main application file (e.g., `index.js`):**

Create a file named `index.js` (or whatever you prefer) in your project directory. This will be the entry point of your application.

**5. Write your code (example with Express.js):**

Paste the following code into `index.js` (or your chosen file):

```js
const express = require('express');
const path = require('path');
const app = express();
const port = 3000;

app.use(express.static(path.join(__dirname, 'public'))); // Serve static files

app.get('/', (req, res) => {
  res.sendFile(path.join(__dirname, 'public', 'index.html')); // Serve index.html
});

app.listen(port, () => {
  console.log(`Server listening on port ${port}`);
});
```

**6. Create the `public` directory (for static files):**

Create a directory named `public` in your project's root directory.  This is where you'll put your static files (HTML, CSS, JavaScript, images).

**7. Create an `index.html` file (optional):**

Inside the `public` directory, create an `index.html` file (or any other static files you need).  This is the file that will be served when a user visits the root URL.  A simple example `index.html`:

```html
<!DOCTYPE html>
<html>
<head>
  <title>My Node.js App</title>
</head>
<body>
  <h1>Hello, World!</h1>
</body>
</html>
```

**8. Configure the `package.json` scripts:**

Open your `package.json` file and add a `start` script (and a `dev` script if you installed `nodemon`):

```json
{
  // ... other parts of package.json
  "scripts": {
    "start": "node index.js",
    "dev": "nodemon index.js"
  },
  // ... other parts of package.json
}
```

**9. Run your application:**

Open your terminal in your project directory and run:

```bash
npm start       # To start the server (production)
# or
npm run dev     # To start the server with nodemon (development)
```

**10. Access your application:**

Open your web browser and go to `http://localhost:3000`. You should see the content of your `index.html` file.

**Summary of commands:**

* `mkdir static-site-server-project`: Create a new directory.
* `cd static-site-server-project`: Change directory.
* `npm init -y`: Initialize a `package.json` file.
* `npm install express`: Install Express.js.
* `npm install --save-dev nodemon`: Install nodemon (for development).
* `npm start`: Start the application (using the "start" script).
* `npm run dev`: Start the application with nodemon.

This guide provides a basic setup for a Node.js project.  As your project grows, you'll likely add more dependencies, routes, and other features. 
Understanding these fundamental steps is crucial for building more complex applications.
Remember to install packages using npm or yarn, and always refer to the documentation of the specific packages you are using for more advanced configurations.
