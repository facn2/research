Client side development is done almost exclusively in JavaScript. This is, of course, in addition to basic HTML and CSS code. The reason JavaScript is called a client side language is because it runs scripts on your computer after you’ve loaded a web page. 

A decade ago, the general rule was to use server-side coding whenever possible and only use client-side code when necessary. But due to the fact that javascript can be utilized 

![alt text](https://files.gitter.im/veredrec/N1ow/JS-vs-other.png)

## Seperation of Concerns:
* Clean code
* Easy maintenance
* Easy testing

Front end: Design, DOM manipulation, User Experience
Back end: Database, Servers, Authentication
Validation can be in both - front end and back end:
Validation in front end - fast and the user get a quick response
Validation in back end - provides security

## Coding on the client side vs server side:

### Pro for client-side:
* Speed: Client-side code can run almost anything on the browser - and much faster too. With server-side code, the user must send a request to the server, the server processes the data, and a response is sent back to the user. Even with fast Internet connections, this process takes time. When the process just runs on the user’s computer, it’s fast and provides an instant response for the user.
* Reuse: JS templates can be rendered on the client. Even if JS is disabled on the client-side, using v8 or some other embedded JS engine, it's possible to render the exact same template server side.
* User interactive: JS reacts to user input, and can be seen and edited by the user in full

### Con for client-side:
* Poor security: Source code is easily accessible to the consumer, meaning that you can hack and compromise JS without much trouble
* Less resources: Server-side languages can easily access resource bundles and complex formatter code for translations. On the client-side, it can be expensive to send down huge dictionaries and formatting logic.

## Node vs. PHP

PHP was created by Rasmus Lerdorf in 1994.
Node.js was created by Ryan Dahl in 2009.
PHP is a long-established language but Node.js is a young upstart receiving increased attention.
Should PHP developers believe the Node.js hype? Should they consider switching?

### Challenge 1 - Console.Log Hello
```javascript
<?php
    echo 'Hello World!';
?>

var http = require('http');
http.createServer(function (req, res) {
    res.writeHead(200, {'Content-Type': 'text/plain'});
    res.end('Hello World!');

}).listen(3000, '127.0.0.1');
```

PHP is conceptually simpler and wins this round. Those who know a few PHP statements can write something useful. It has more software dependencies, but PHP concepts are less daunting to new developers.

### Challenge 2 - Help and Support
Twenty Years worth of Q and A's for PHP. It is still more of a titan than Node.
However there is a wealth of material for Node also. Learn Node by Wes Bos. You get 52% of because we are in Israel.

### Challenge 3 - Language Syntax
Full-stack developers can use JavaScript on the client and server. Your brain doesn’t need to switch modes

### Challenge 4 - Development Tools
NPM gives Node the edge. PHP has a similar called the composer project. It has made less of an impact.

### Challenge 5 - Programmer Passion
It’s a little difficult to make comparisons but relatively few PHP developers are passionate about the language. When was the last time you read a PHP article or saw a presentation which captivated the audience? Perhaps everything has been said? Perhaps there’s less exposure? Perhaps I’m not looking in the right places? There are some nice features arriving in PHP7 but the technology has been treading water for a few years. That said, few PHP developers berate the language.

```javascript
Number on Reddit Forums
NodeJS - 30,960
PHP - 49,850
Java - 70,711
Elexir - 7,924
```

## Different Environment:
* The main difference between the JS between the client-side and server-side is that ES6 is usable universally on the server-side, while the client-side has not been implemented across all browsers yet. 
