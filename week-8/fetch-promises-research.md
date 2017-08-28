### Promise
#### What is a Promise?
Javascript is **single-thread** thus we need ways to handle functions in asyncrous way. Just like callback, promise is another way to handle asyncronous behaviors.




#### What are pros and cons of using promises compared to callbacks?
**pro:** flexibility, liberty, maintainabiliy as in it is more readable,
composable, promises  offer an ability to chain different functions together and to share logic across the codes

**cons:** it requires an additional abstraction layer which means we have to rely on libraries (e.g. Polyfill).
 Though promise is native in ECMA6, it is not fully supported by all the browsers.
#### How does promise work?

 ![diagram](https://files.gitter.im/sajedazoabi/Xb9H/thumb/Screenshot-from-2017-08-21-16-09-35.png)



### Fetch
** What is fetch and how do you use it? **

+ ```fetch()```  allows a programmer to make a network request similar to XHR but it uses promises which enable a simpler and cleaner API, avoiding callbacks hell.

+ Response of a ```fetch()``` request is a stream object which means that when we ask for something, a promise is returned since the reading of the stream will happen asynchronously.  

** What are the downsides of using Fetch? what does Fetch miss?**

+ By default, ```fetch``` does not send cookies

+ Server needs to know that the client will be able to handle a JSON encoded response
