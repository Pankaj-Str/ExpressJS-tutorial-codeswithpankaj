# ExpressJS - Installation and Creating the "Welcome to p4n" Project

In this guide, we will go through the process of installing ExpressJS and creating a simple Express project named "p4n" that displays a welcome message including the phrase "codeswithpankaj."

## Step 1: Install Node.js and npm

Ensure that you have Node.js and npm installed on your machine. You can download them from the official Node.js website: [Node.js Downloads](https://nodejs.org/en/download/).

## Step 2: Create a New Project

Open your terminal or command prompt and create a new directory for your Express project. Navigate to the project directory using the `cd` command:

```bash
mkdir p4n
cd p4n
```

## Step 3: Initialize Your Project with npm

Initialize your project by running the following command:

```bash
npm init -y
```

This command creates a `package.json` file with default settings.

## Step 4: Install Express

Install Express in your project by running the following command:

```bash
npm install express
```

## Step 5: Create Your "Welcome to p4n" Express Program

Create a file named `app.js` in your project directory. Open this file in a text editor and add the following code:

```javascript
const express = require('express');
const app = express();
const port = 3000;

// Define a route for the root URL
app.get('/', (req, res) => {
  res.send('Welcome to p4n - codeswithpankaj');
});

// Start the server
app.listen(port, () => {
  console.log(`Server listening at http://localhost:${port}`);
});
```

This code does the following:

- Requires the Express module.
- Creates an Express application.
- Defines a route for the root URL that responds with 'Welcome to p4n - codeswithpankaj.'
- Starts the server on port 3000.

## Step 6: Run Your Express Application

In your terminal, run the following command to start your Express application:

```bash
node app.js
```

You should see the message "Server listening at http://localhost:3000" in the terminal.

Visit [http://localhost:3000](http://localhost:3000) in your web browser, and you should see the text "Welcome to p4n - codeswithpankaj" displayed on the page.

Congratulations! You've successfully installed Express, set up your project, and created a basic "Welcome to p4n" Express application. This serves as a starting point for building more features and functionality into your Express projects. Explore the Express documentation for additional features and options to enhance your Express applications further.
