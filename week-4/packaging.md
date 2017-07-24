# Packaging

## Dependencies:
+ What is a dependency?
  + A dependency is normally a package that is installed and is essential for the project to work.
+ Why might you want to use a dependency in your project, rather than writing the code from scratch?
  + It's easier, takes less time. More efficient.
+ What have traditionally been some of the issues with managing dependencies?
  + awful documentation
  + packages aren't maintained

## NPM:
+ What is a package manager?
  + A package manager is a library of packages that allows the easy install of packages
+ How does it help with dependencies?
  + easy to install
+ What is package.json, and what does npm init do?
  + contains meta-information about your project, including any third-party modules you install
+ How do you use an installed package in your code?
  + `$<package name> <filename>`
  + write a script in the `package.json` then use `$npm run <scriptname>`

### npm install:
How to install a package using npm.
```
$ npm install <package name>
```
```
$ npm i <package name>
```
#### Global
```
$ npm i -g <package name>
```
#### Dependency
```
$ npm i -P <package name>
```
#### Development dependency
```
$ npm i -D <package name>
```

+ What is the difference between installing a package globally, installing it as a dependency, or installing it as a development dependency? When would you use each?
  + Global - use it when you are installing a package you want to use in the shell/terminal
  + Dependency - use for packages that make the app/website work for the client
  + Dev dependency - use for packages that the developer needs to write the code e.g. testing
+ Why is it normally a bad idea to install a package globally?
  + global modules are not listed as dependecies in your project - if someone else wants to work on the same project, they can't type `npm install` and get the dependencies.

## Package files:
+ Where does NPM install packages?
  + `$npm list` for list of local
  + `$npm -g root` to find the root location
  + `$cd <root location>`
  + `$cd /home/matthew/.npm-global/lib/node_modules`
+ Why is it important to make sure that installed packages aren't included in your repositories?
  + large files and lots of them
+ How do you prevent Git from including these files in your repository?
  + create a `.gitignore` file, then type `node_modules/`
