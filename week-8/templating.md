# **Templating and Severside Rendering**

### What is server-side rendering?
It works by converting HTML files in the server into usable information for the browser. Each time you go to a new page on the site the browser sends a request and the server responds with the fully rendered html.

### What is client-side rendering?
Client side rendering is essentially loading all the content of the webpage using Javascript. The server renders a bare bones html and the browser is left to render everything else using javascript. Eg using web API create element and append to website (DOM manipulation).

### What are the pros and cons of serverside rendering vs clientside?

**Pros of server-side**
+ Initial loading of the web page is slightly faster
+ Static sites
+ Doesn't require external library

**Cons of server-side**
+ Multiple server requests
+ Full page reloads (slower rendering)
+ Less dynamic site

### What problems do templating languages solve?

**What is a templating language?**

Templating languages are for writing templates which are designed to combine with a data model to produce result documents, like HTML with dynamic data from backend. Examples include Handlebars, Mustache,  Pug(Jade) and EJS to name a few.
The templating engine has 2 primary responsibilities
+ The fragmentification and inclusion of common interface assets (to avoid duplication and maintaining the same code in multiple files) - eg. headers, footers, sidebars and the like
+ The output of dynamic content

### Examples of functionality that templating languages provide
e.g. conditional logic etc.
+ In built logic such as for loops and if statements
```javascript
{{#each people}}

<li>{{this}}</li>

{{/each}}
```

+ You can also write your own helper functions
