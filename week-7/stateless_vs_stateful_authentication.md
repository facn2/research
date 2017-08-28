# Stateful vs Stateless Authentication

### Stateful Authentication
Server does all the heavy lifting sever side. A client authenticates with its credentials (username and password) and receives a session id (a unique number). The session id is both stored on the clients browser as a cookie and in the server database. Every subsequent request the session id is verified against the session id stored in the database. When the session id validates the server sends back the requested data.

### Stateless Authentication
Stateless is the polar opposite of stateful. Stateless or token based authentication validates credentials which are then exchanged for a token.  This token is stored in the browser only. The token is attached to each subsequent request and validated by decoding the token and checking it is correct.

**Creating web tokens**

To create a web token there are several packages including [jsonwebtokens (JWT)](https://www.npmjs.com/package/jsonwebtoken).

Require the JWT package
```javascript
var jwt = require('jsonwebtoken');
```
Use JWT sign function to create a token
```javascript
jwt.sign(payload, secretKey, [options, callback]);
```
Use JWT verify function to check the validate the token
```javascript
jwt.verify(token, secretKey, [options, callback]);
```

**Flow diagram for cookie vs token based authentication steps**

![flow diagram for cookie vs token based authentication](https://cdn.auth0.com/blog/cookies-vs-tokens/cookie-token-auth.png)

### Which way is better?
Stateless is a fundamental aspect of the modern internet so much so that every single day you use a variety of stateless services and applciations.

**Pros of stateless**
+ Back end does not need to store anything (stateful uses lots of memory)
+ It can manage many different domains (doesn't check against a database)
+ Can store any type of data in the json web token (JWT) e.g. email address
+ Improved performance - it is faster to decode and check rather than looping through a database of session ids
+ Works well on mobile platforms - cookies don't mix well with mobile browsers

**Cons of stateless**
+ Size of JWT - if you add lots of data to the JWT it can be relatively big compared to the cookie, may be a problem as the JWT has to be attached to every request
+ Token storage - normally stored in browsers local storage but this is set to a specific domain. They can be stored in a cookie but there is a size limit of only 4Kb. Session storage can also be used but this will be wiped.
+ Don't store sensitive data in the payload
+ Slightly easier to run cross site scripting(XSS) attack

### Productive Systems
This is a more complex method. They use both short lived bearer tokens and longer lived refresh tokens. The longer lived refresh tokens are used to get the shorter bearer tokens . This allows users to create new bearer tokens without having to login again.
