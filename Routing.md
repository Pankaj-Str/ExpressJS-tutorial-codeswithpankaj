# ExpressJS - Using Routing in the "p4n" Project

## Step 1: Update Project Structure

Before diving into routing, make sure your project structure looks like this:

```
p4n/
|-- node_modules/
|-- app.js
|-- package.json
|-- package-lock.json
```

## Step 2: Install Nodemon (Optional)

For development convenience, you can install `nodemon` as a development dependency to automatically restart your server when changes are made. Install it by running:

```bash
npm install --save-dev nodemon
```

## Step 3: Update `package.json` Scripts

Open your `package.json` file and update the "scripts" section to include a start script using `nodemon`:

```json
"scripts": {
  "start": "nodemon app.js"
}
```

Now, you can start your server using `npm start`.

## Step 4: Update `app.js` for Routing

Open `app.js` in your text editor and modify it to include routing:

```javascript
const express = require('express');
const app = express();
const port = 3000;

// Route for the root URL
app.get('/', (req, res) => {
  res.send('Welcome to p4n - codeswithpankaj');
});

// Route for '/about'
app.get('/about', (req, res) => {
  res.send('About p4n - codeswithpankaj');
});

// Route with parameters
app.get('/user/:username', (req, res) => {
  const username = req.params.username;
  res.send(`Hello, ${username}! Welcome to p4n - codeswithpankaj`);
});

// Handling POST request
app.post('/login', (req, res) => {
  res.send('Login Page - codeswithpankaj');
});

// Handling PUT request
app.put('/user/:id', (req, res) => {
  const userId = req.params.id;
  res.send(`Updating user with ID ${userId} - codeswithpankaj`);
});

// Start the server
app.listen(port, () => {
  console.log(`Server listening at http://localhost:${port}`);
});
```

In this updated `app.js`:

- The root URL `/` responds with the original welcome message.
- The `/about` path responds with an "About p4n" message.
- The `/user/:username` path demonstrates the use of parameters.
- The `/login` path handles a POST request.
- The `/user/:id` path handles a PUT request.

## Step 5: Run Your Updated Express Application

Start your Express application by running:

```bash
npm start
```

Visit [http://localhost:3000](http://localhost:3000) in your web browser to see the original welcome message. Explore other routes like [http://localhost:3000/about](http://localhost:3000/about) and [http://localhost:3000/user/john](http://localhost:3000/user/john) to see different responses.

Congratulations! You've successfully implemented routing in the "p4n" project using ExpressJS. This is a foundation that you can build upon for more complex web applications. Feel free to experiment with additional routes, middleware, and features to enhance your Express project further.
