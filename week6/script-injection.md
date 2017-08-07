# Script Injections

### What is a script injection?
Code injection is the exploitation of a computer bug that is caused by processing invalid data. Injection is used by a hacker to introduce code into a vulnerable computer program and manipulate the outcome of the program.

Injection can result in data loss or corruption, lack of accountability, or denial of access. Injection can sometimes lead to complete host takeover.

For example XSS (cross site scripting) is one of the script injection methods from the client side.

### How do script injections happen?
+ Malicious user inputs by trying to run javascript through the user input.
+ Common injections
  * SQL
  * Web
  * OS commands

A few examples:
```
http://www.example.com/user/details?id=123; SELECT * FROM userdata WHERE id=123
```
```
<script>alert('HAHA')</script>
```

### How would you prevent script injections?
+ input checking
+ use safer methods
+ encode user input using server.HTMLEncode()
+ white listing

Check out this [game](https://xss-game.appspot.com/).
