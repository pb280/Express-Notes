## Basics of Express

<br>

`Using Express to create server based app`

```
const express = require('express')

const app = express()

app.get('/', (req, res) => {
  res.status(200).json({ message: 'Hello from the server', app: 'natours' })
})

app.post('/', (req, res) => {
  res.send('You can post to this endpoint.....')
})

const port = 3000
app.listen(port, () => {
  console.log(`App running on port ${port}`)
})

```

<br>

<br>

<hr>

### HTTP Methods

<br>

`GET`: Delivers resource(data) to the client

`POST`: Takes resource(data) from the client to the server

`PUT`: Client sends entire updated object(resource)

`PATCH`: Client sends only relevant part of the object to be changed

`DELETE`: Deletes the resource(data) from the object or entire object

<br>

<hr>

### Response Codes

<br>

`200`: Successful

`201`: Created

`204`: Deleted OR No-Content

`500`: Internal Server Error

<br>

<hr>

### Express Design Pattern: Fetching API requests on Route

```
app = express()

// GET
app.get('api/v1/tours', (req, res) => {
  console.log(res.params);
})

// POST
app.post('api/v1/tours', (req, res) => {
  console.log(res.params);
})

// PATCH
app.patch('api/v1/tours', (req, res) => {
  console.log(res.params);
})

// DELETE
app.delete('api/v1/tours', (req, res) => {
  console.log(res.params);
})
```

<br>

<hr>

### Catching custom params from route

```
app = express()

app.get('api/v1/tours/:id/:name/:duration?', (req, res) => {
  console.log(req.params.id);
  console.log(req.params.name);
})
```

Here, `duaration` is optional param.

<br>

<hr>

### Middleware

<br>

**1. Creating our own middleware**

```
app = express()

app.use((req, res, next) => {
  console.log("Hello from the middleware 🚀");
})
```

**2. Using 3rd party middleware**

- Helps to log request results in console during development

```
app = express()

app.use(morgan('dev'))

// ... Other Middlewares

app.route('api/v1/tours').get(getAllTours)

const port = 8000
app.start(port, () => {
  console.log('Server started at port 8000')
})

```

**3. Serving static files using express.static() middleware**

```
app.use(express.static(`${__dirname}/public`));
```

Will look into public folder so that user can access static files from browser.
E.g `localhost:3000/overview.html` here 'localhost:3000' will be treated as 'public/' to get the file.

<br>

`Order of the Middleware's matters a lot in Express`
