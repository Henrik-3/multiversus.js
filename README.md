<div align="center">
  <h1>
    multiversus.js
  </h1>
	<p>
		<a href="https://discord.gg/Sxqn7hqKZY"><img src="https://img.shields.io/discord/1003096141258309732?color=5865F2&logo=discord&logoColor=white" alt="Discord server" /></a>
		<a href="https://www.npmjs.com/package/multiversus.js"><img src="https://img.shields.io/npm/v/multiversus.js.svg?maxAge=3600" alt="npm version" /></a>
	</p>
</div>

## About

A simple Node.js module to access the MultiVersus API.

## Installation

```sh
npm install multiversus.js
yarn add multiversus.js
```

## Example usage

To create a client, an access token and client ID are necessary. To retrieve these values, a tool such as [Fiddler](https://www.telerik.com/fiddler) is required. The required values can then be retrieved by analyzing the network requests made from MultiVersus.

Initialize the client:

```js
const { Client } = require('multiversus.js');
const client = new Client('accessToken', 'clientId');
```

To retrieve an access token, alternatively, initialize the client as follows, using your Steam username and password in place of 'username' and 'password':

```js
const { Client } = require('multiversus.js');
const client = new Client('accessToken', 'clientId');
client.login('username', 'password');
```

Get the MultiVersus 2v2 leaderboard:

```js
const leaderboardData = await client.getLeaderboard('2v2'); // The type of the leaderboard to be retrieved can also be set to '1v1'.
console.log(leaderboardData);
```

Get a profile by a user's ID:

```js
const userData = await client.getProfile('62e471bc5f77e966a384a570');
console.log(userData);
```

Search for users:

```js
const searchData = await client.searchByUsername('ElijahPepe'); // A second parameter can also be defined to limit the results returned.
console.log(searchData);
```

## Links

- [npm](https://www.npmjs.com/package/multiversus.js)
- [GitHub](https://github.com/ElijahPepe/multiversus.js)
- [Discord server](https://discord.gg/Sxqn7hqKZY)
