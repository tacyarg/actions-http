# actions-http

Provides a simple http interface with json parsing.

# Interface

```
yarn add actions-http
```

## Setup
> Below is a simple use case of the client.

```js
// your desired application interface.
const actions = {
  async ping(params) {
    return 'pong'
  },
  async echo(params) {
    return params
  }
}

const config = {
  port: 9001
}

// start the server
const web = require('actions-http')(config, actions)
```

## Call

```js
const request = require('request')

request.post('http://localhost:9001/echo', {
  // some json body
  test: true
})

request.get('http://localhost:9001/ping')
```
