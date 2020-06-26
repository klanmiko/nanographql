# nanographql-esm

[![npm version][1]][2] ![Node.js CI](https://github.com/klanmiko/nanographql-esm/workflows/Node.js%20CI/badge.svg)

Tiny graphQL client library. Does everything you need with GraphQL 15 lines of
code.

## Usage
```js
import gql from 'nanographql-esm'

var query = gql`
  query($name: String!) {
    movie (name: $name) {
      releaseDate
    }
  }
`

try {
  var res = await fetch('/query', {
    body: query({ name: 'Back to the Future' }),
    method: 'POST'
  })
  var json = res.json()
  console.log(json)
} catch (err) {
  console.error(err)
}
```

## API
### `query = gql(string)`
Create a new graphql query function.

### `json = query([data])`
Create a new query object that can be sent as `application/json` to a server.

## License
[MIT](https://tldrlegal.com/license/mit-license)

[1]: https://img.shields.io/npm/v/nanographql-esm
[2]: https://npmjs.org/package/nanographql-esm