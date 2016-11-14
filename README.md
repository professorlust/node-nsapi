# nsapi #

[![npm version](https://badge.fury.io/js/nsapi.svg)](https://badge.fury.io/js/nsapi)

nsapi is a free and open source library that allows Node.js and web 
applications to easily access the NationStates API without worrying about 
making HTTP requests, decoding XML or rate limiting.

nsapi features the following:
* a complete interface to the NationStates API (supports the nation, region,
  world, World Assembly, telegram, and authentication APIs)
* rate-limiting to prevent blocked access to the API, including for the 
  telegram API (recruitment and non-recruitment)
* XML decoding (all data is returned in simple JavaScript data structures)
* support for version 9 of the NationStates API

## Usage ##

You can install nsapi using npm: `npm install nsapi`.

You can also build nsapi from source using Gulp. There are two targets: `prod`
and `dev`. The only difference between them is that `dev` includes source maps.

## Examples ##

The following is a simple example that retrieves a nation's full name and prints 
it to the console.

```js
// The following is a simple example that retrieves the nation Auralia's full
// name and prints it to the console.

var nsapi = require("nsapi");

// TODO: Replace the user agent with your own
var api = new nsapi.NsApi("<user agent>");
return api.nationRequest("Auralia", ["fullname"])
          .then(function(data) {
              console.log(data["fullname"]);
          })
          .then(function() {
              api.cleanup();
          });
```

For additional examples, consult the example.js file.

## License ##

nsapi is licensed under the [Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0).
