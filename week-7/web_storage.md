# What is web storage?

Web storage, sometimes known as DOM storage (Document Object Model storage), provides web application software methods and protocols used for storing data in a web browser.

# Local and session storage
Web storage offers two different storage areas—local storage and session storage—which differ in scope and lifetime.  

Data placed in *local storage* is per origin (the combination of protocol, hostname, and port number as defined in the same-origin policy) (the data is available to all scripts loaded from pages from the same origin that previously stored the data) and persists after the browser is closed.

*Session storage* is per-origin-per-window-or-tab and is limited to the lifetime of the window. Session storage is intended to allow separate instances of the same web application to run in different windows without interfering with each other, a use case that's not well supported by cookies.

Unlike cookies, which can be accessed by both the server and client side and automatically passed in header to maintain stateful connections to app, web storage falls exclusively under the purview of client-side scripting.

Web storage data *is not automatically transmitted to the server in every HTTP request, and a web server can't directly write to Web storage.*

Hence it is kind of immune to CSRF, but since it is interactive with javascript, it is still vulnerable to XSS of that website.

Cookies on the other hand, if the httpOnly flag is on, it is kind of immune to XSS as it does not interact with javascript in the browser.

# Comparison between cookies vs localStorage vs  sessionStorage

|                    | cookies             | localStorage   |sessionStorage   |
|---                 |---                  |---             |---              |
| capacity           | 4kB                 |  5MB*          | 5MB*            |
| accessibility      | any window          | any window     | same tab           |
| expires            | manually set        | never          | on tab close                |
| storage location   | browser and server  | browser        | browser |
| sent with requests | yes                 | no             | no      |


# Demo for local storage and session storage

To set values in local storage:  

localStorage.setItem('katia', 'smart');  

To get values in local storage:  

localStorage.getItem('katia');
// it should show you the key value 'smart';

To set values in session storage:

sessionStorage.setItem('katia', 'really smart');

To get values in session storage:

sessionStorage.getItem('katia');
// it should show you the key value 'really smart';

Action point :
Show both storage after 1. refresh 2. close the tab


[A good video explaining cookies and web storage](https://www.youtube.com/watch?v=AwicscsvGLg)
