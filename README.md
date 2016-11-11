# fetch-graphql-schema

[![NPM version][npm-image]][npm-url]
[![Build Status][travis-image]][travis-url]
[![Test coverage][coveralls-image]][coveralls-url]
[![Dependency Status][david_img]][david_site]

> fetch GraphQL schema via introspection query


## Install

```
$ npm install fetch-graphql-schema
```


## Usage

```js
const fetchSchema = require('fetch-graphql-schema');

fetchSchema('http://localhost:8080/graphql')
  .then(schemaJSON => {
    /**
     * {
     *   "data": {
     *     "__schema": {
     *       "queryType": {
     *         "name": "Query"
     *          ....
     */
  });

fetchSchema('http://localhost:8080/graphql', { readable: true })
  .then(clientSchema => {
    /**
     * type User implements Node {
     *   id: ID!
     *   name: String!
     * }
     */
  });
//=>
```


## API

### fetchGraphqlSchema(url, [options])

#### url

*Required*
Type: `string`

URL of GraphQL server.

#### options

##### readable

Type: `boolean`
Default: `false`

resolve `.graphql` instead of `.json`.


## License

MIT © [C.T. Lin](https://github.com/chentsulin/fetch-graphql-schema)

[npm-image]: https://badge.fury.io/js/fetch-graphql-schema.svg
[npm-url]: https://npmjs.org/package/fetch-graphql-schema
[travis-image]: https://travis-ci.org/chentsulin/fetch-graphql-schema.svg
[travis-url]: https://travis-ci.org/chentsulin/fetch-graphql-schema
[coveralls-image]: https://coveralls.io/repos/chentsulin/fetch-graphql-schema/badge.svg?branch=master&service=github
[coveralls-url]: https://coveralls.io/r/chentsulin/fetch-graphql-schema?branch=master
[david_img]: https://david-dm.org/chentsulin/fetch-graphql-schema.svg
[david_site]: https://david-dm.org/chentsulin/fetch-graphql-schema

