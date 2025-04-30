# @virtuals-protocol/game-twitter-node

Strongly typed, full-featured, light, versatile yet powerful Virtual Twitter API v2 client for Node.js, specifically designed for GAME Virtuals Protocol.

This is a fork of the original twitter-api-v2 library, modified to support Virtual Twitter API v2 endpoints within the GAME Virtuals Protocol ecosystem.

## Important Note

This is a modified version of the original twitter-api-v2 library that focuses exclusively on Virtual Twitter API v2 support for GAME Virtuals Protocol. This implementation provides a virtualized Twitter API experience while maintaining compatibility with the v2 endpoint structure.

## Highlights

✅ **Ready for Virtual Twitter API v2**

✅ **Light: No dependencies, 23kb minified+gzipped**

✅ **Bundled types for request parameters and responses**

✅ **Streaming support**

✅ **Pagination utils**

✅ **GAME Virtuals Protocol integration**

## How to use

Install it through your favorite package manager:

```bash
yarn add @virtuals-protocol/game-twitter-node
# or
npm i @virtuals-protocol/game-twitter-node
```

Here's a quick example of usage:

```ts
import { TwitterApi } from "@virtuals-protocol/game-twitter-node";

// Instantiate with GAME Virtuals Protocol authentication
const twitterClient = new TwitterApi({
  gameTwitterAccessToken: "<YOUR_GAME_VIRTUALS_TOKEN>",
});

// Tell typescript it's a readonly app
const readOnlyClient = twitterClient.readOnly;

// Play with the built in methods
const user = await readOnlyClient.v2.userByUsername("plhery");
await twitterClient.v2.tweet("Hello, this is a test.");
```

To get the access token, run the following command:

```bash
npx @virtuals-protocol/game-twitter-plugin auth -k <GAME_API_KEY>
```

Here is an example run:

```bash
npx @virtuals-protocol/game-twitter-plugin auth -k apt-xxxxxxxxxx
```

You will see the following output:

```
Waiting for authentication...

Visit the following URL to authenticate:
https://x.com/i/oauth2/authorize?response_type=code&client_id=VVdyZ0t4WFFRMjBlMzVaczZyMzU6MTpjaQ&redirect_uri=http%3A%2F%2Flocalhost%3A8714%2Fcallback&state=866c82c0-e3f6-444e-a2de-e58bcc95f08b&code_challenge=K47t-0Mcl8B99ufyqmwJYZFB56fiXiZf7f3euQ4H2_0&code_challenge_method=s256&scope=tweet.read%20tweet.write%20users.read%20offline.access
```

After authenticating, you will receive the following message:

````
Authenticated! Here's your access token:
apx-613f64069424d88c6fbf2e75c0c80a34
```|

## Features

Here's everything `@virtuals-protocol/game-twitter-node` can do:

### Basics:

- Full support for **Virtual Twitter API v2**
- Make signed HTTP requests with **GAME Virtuals Protocol Authentication**
- Helpers for numerous HTTP request methods (`GET`, `POST`, `PUT`, `DELETE` and `PATCH`),
  that handle query string parse & format, automatic body formatting and more
- High-class support for stream endpoints, with easy data consumption and auto-reconnect on stream errors

### Request helpers:

- Automatic paginator for endpoints like user and tweet timelines,
  allowing payload consumption with modern asynchronous iterators
- Convenient methods for GAME Virtuals Protocol authentication
- Dedicated methods that wrap Virtual API v2 endpoints, with **typed arguments** and fully **typed responses**
- Typed errors, meaningful error messages, and error enumerations

### Type-safe first:

- **Typings for tweet, user, media entities (and more) are bundled!**
- Type-safe wrapping of dedicated methods in 3 right level: _DM_/_Read-write_/_Read-only_
- Declare a read-only client - you will only see the methods associated with read-only endpoints

And last but not least, fully powered by native `Promise`s.
````
