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
