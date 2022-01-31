# framework

🚀 Simple express.js 'framework' to evaluate expressions in HTML templates.

## Installation

```sh
npm install @bharadwajduggaraju/framework
```

## Usage

First create a HTML file with things you want to be evaluate (index.html).

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>Hey {"BOB".toLowerCase()}</h1>
    <p>1+1 is equal to {1+1}</p>
  </body>
</html>
```

Then create a express application with the framework (index.js).

```sh
npm i express
```

```js
const fv = require("@bharadwajduggaraju/framework");
const express = require("express");

const app = express();

app.get("/", (req, res) => {
  res.send(fv(__dirname + "/index.html"));
});

app.listen(8080);
```

Once you run the application, head to `localhost:8080`, and you will see all
the expressions evaluated!

## Variables

You can also evaluate variables from your express application.

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>Hey {name}</h1>
    <p>{greeting}</p>
  </body>
</html>
```

Then, when you call ```fv()```, pass in the variables like this:

```js
res.send(
  fv(__dirname + "/index.html", { name: "Bob", greeting: "How's life!" })
);
```

