# ExpressJS - Templating

Templating in ExpressJS is a crucial aspect of building dynamic and data-driven web applications. Express supports various templating engines, allowing developers to generate HTML dynamically by rendering templates with data. In this guide, we'll explore the basics of templating in ExpressJS and demonstrate how to use the popular templating engine EJS (Embedded JavaScript).

## Setting Up EJS Templating Engine

Before using EJS, you need to install it as a dependency for your Express project. Open your terminal and run:

```bash
npm install ejs
```

Once installed, you can configure Express to use EJS as the templating engine in your application.

```javascript
const express = require('express');
const app = express();
const port = 3000;

// Set EJS as the view engine
app.set('view engine', 'ejs');

// Define a route that renders an EJS template
app.get('/', (req, res) => {
  const data = { message: 'Hello, Express with EJS!' };
  res.render('index', data);
});

// Start the server
app.listen(port, () => {
  console.log(`Server listening at http://localhost:${port}`);
});
```

In this example, the `app.set('view engine', 'ejs')` line configures Express to use EJS as the templating engine. The `res.render('index', data)` line renders the `index.ejs` template with the provided data.

## Creating an EJS Template

Create a new file named `views/index.ejs` in your project. This file will be the EJS template.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Express with EJS</title>
</head>
<body>
  <h1><%= message %></h1>
</body>
</html>
```

In this EJS template:

- `<%= message %>` is an EJS tag that inserts the value of the `message` variable.

## Passing Data to EJS Templates

As demonstrated earlier, data can be passed to EJS templates using the `res.render` method. The keys in the data object become variables accessible in the template. Here's an example with more data:

```javascript
const express = require('express');
const app = express();
const port = 3000;

app.set('view engine', 'ejs');

app.get('/', (req, res) => {
  const data = {
    title: 'Express with EJS',
    message: 'Hello, Express with EJS!',
    items: ['Item 1', 'Item 2', 'Item 3']
  };
  res.render('index', data);
});

app.listen(port, () => {
  console.log(`Server listening at http://localhost:${port}`);
});
```

Now, you can update your `views/index.ejs` template to display the additional data:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title><%= title %></title>
</head>
<body>
  <h1><%= message %></h1>
  <ul>
    <% items.forEach(item => { %>
      <li><%= item %></li>
    <% }); %>
  </ul>
</body>
</html>
```

In this template, `<% items.forEach(item => { %>` is an EJS tag used for looping through the `items` array, and `<%= item %>` displays each item in a list.

## Conclusion

ExpressJS makes templating straightforward with the use of templating engines like EJS. Leveraging templating engines allows developers to generate dynamic content efficiently. As you explore Express further, experiment with different templating engines, such as Handlebars or Pug, and discover which one aligns best with your preferences and project requirements.
