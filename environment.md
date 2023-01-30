### Displaying environment using Express object

<br>

> In `server.js`

```
const app = require("./app");

console.log(app.get('env'));

const port = 3000;

app.listen(port, () => {
  console.log(`App running on port ${port}`);
});
```

<br>

### Logging env setup to console created by the NodeJS

<br>

> In `server.js`

```
const app = require("./app");

console.log(process.env);

const port = 3000;

app.listen(port, () => {
  console.log(`App running on port ${port}`);
});

```

<br>

### Passing env values through CLI

<br>

Linux/Mac: `NODE_env=development X=25 nodemon server.js`
Windows: `NODE_env=development X=25 nodemon server.js`

when we log `process.env` to the console through will show all the env variables that we passed

<br>

### Passing env values through `.env` file

<br>

```
NODE_ENV=development
PORT=8000
USER=Prathamesh
PASSWORD=123456
```

<br>

### Connecting .env files to NodeJS

<br>

1. Installing package through npm

   `npm install dotenv`

2. In `server.js`

```
const dotenv = require("dotenv");
const app = require("./app");

dotenv.config({ path: "./config.env" });

console.log(process.env);

const port = 3000;

app.listen(port, () => {
  console.log(`App running on port ${port}`);
});

```

<br>
