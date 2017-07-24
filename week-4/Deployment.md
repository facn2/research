# Deployment
Software deployment includes all processes required for preparing a software application to run and operate in a specific environment. It involves installation, configuration, testing and making changes to optimize the performance of the software. It can either be carried out manually or through automated systems
# What is PaaS ???
Platform as a service (PaaS) is a cloud computing service which provides a platform allowing customers to develop, run, and manage applications without the complexity of building and maintaining the infrastructure themselves. 


# What does that mean?


Most would be familiar with traditional hosting which requires the setup of a server. Setting up a server would include the following proccess: 



```git
- Set up the application server (e.g. Apache, Nginx, etc.)
- Set up MySQL database
- Setting up the run-time platform like PHP, Ruby, etc
- Something isn’t working.
- Diagnose, re-configure/re-setup, try again.
- Dependencies… right, have to setup those up too.
- Setup FTP to deploy your code.
- Setup security and firewall.
- etc. etc. etc.
```
As a developer your core competency is writing code, not managing servers. With cloud based deployment solutions, you're able to have all of the above features "out of the box". 
# PaaS Providers
Some of the bigger providers in the PaaS industry would be AWS, Salesforce/Heroku, Window Azure and Google Cloud. While all of these and more have a known precense in the industry, Amazon by far consumes the majority of the market share.

![Image](https://api.monosnap.com/rpc/file/download?id=nQDE2wjWhx33uWmm8NK8jjGM8QPdLv)


# Heroku Deployment
Go to project directory and type

```javascript
$ heroku
```
Login to Heroku

```javascript
$ heroku login
```
Add info to package.json

```git
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1", // remember add comma
    "start": "node app.js" //This line is new
  },
```
Initialize git repository in project root folder

```javascript
$ git init
```
Add files 

```javascript
$ git status
$ git add . // (stages new and modified, without deleted)
// You can also add files individually - Example: 
$ git add app.js
$ git add package.json
$ git add views/
```
Commit files

```git
$ git commit -m "initial commit"
```
Create Heroku project

```git
$ heroku create
```
Heroku project create w/ link

```git
//Heroku output after heroku create. Example:
Creating app... done, ⬢ whispering-hamlet-61266
https://whispering-hamlet-61266.herokuapp.com/ | https://git.heroku.com/whispering-hamlet-61266.git
//Initial link will state "Heroku | Welcome to your new app
```
Links to push code to

```javascript
$ git remote -v
heroku  https://git.heroku.com/whispering-hamlet-61266.git (fetch)
heroku  https://git.heroku.com/whispering-hamlet-61266.git (push)
```
Push master git repository to Heroku

```git
$ git push heroku master
```
Check for errors

```git
$ heroku logs
```
after rectifying issues or making changes

```git
$ git status
$ git add <filename>
$ git commit -m "leave note here"
```
Once rectified 

```git
$ git push heroku master
```


# What is an environment variable?
An environment variable is a KEY=value pair that is stored on the local system where your code/app is being run and is accessible from within your code. Environment variables are the best way of storing sensitive data like API Keys, Login Credentials and Database Passwords.
# Why?

Avoid (accidentally) committing (exposing) your private keys, passwords or other sensitive details
(by hard-coding in them in your script) to GitHub by storing them as environment variables.


This simply means that you save any configuration both the values that are the
same everywhere you run your app and the keys that change depending on where
you are running the app, in the environment where you are running your app.


# How?
In your terminal type: 

```git
$printenv
//press enter
```

You should see something like this:

```git
{
TERM_PROGRAM: 'Apple_Terminal',
SHELL: '/bin/bash',
TERM: 'xterm-256color',
TERM_PROGRAM_VERSION: '343.7',
USER: 'n',
PWD: '/Users/n/code/learn-environment-variables',
LANG: 'en_GB.UTF-8',
_system_arch: 'x86_64',
_systemname: 'OSX', : '/usr/local/bin/node'
}

```

This is a list of all the variables defined in your environment, in this case we are running "printenv" on a Mac using the "Terminal" app. 


Log the list of environment variables available to node.js in process.env
Node.js gives you access to the variables defined in your environment in the "process.env" global object.






