# GraphQL Hello World

This is a very simple example based on [Getting Started With GraphQL.js](http://graphql.org/graphql-js/).

The whole thing is just:

```
npm init
npm install graphql --save
```

Create a `server.js`:

```javascript
var { graphql, buildSchema } = require('graphql');

// Construct a schema, using GraphQL schema language
var schema = buildSchema(`
  type Query {
    hello: String
  }
`);

// The root provides a resolver function for each API endpoint
var root = {
  hello: () => {
    return 'Hello world!';
  },
};

// Run the GraphQL query '{ hello }' and print out the response
graphql(schema, '{ hello }', root).then((response) => {
  console.log(response);
});
```

And now you can:

`node server.js`

Which should output:
 
```javascript
{ data: { hello: 'Hello world!' } }
```
 
🎉
