# Code Coverage 
##What is test coverage?
* **Code coverage** is a measurement of how many lines/blocks/arcs of your code are executed while the automated tests are running.
 
* In other words, in case of a program with _high degree code coverage,_ we can say that most of the codes written are being tested/called by our tests. On the other hand, we can say that a progam with _low code degree coverage_contains lines of code that can be removed or might require additional testings.

* A program with _high code coverage,_ measured as a percentage, has had more of its source code executed during testing which suggests it has a lower chance of containing undetected software bugs compared to a program with low code coverage. 

 
## Basic Coverage Criteria 
#### There are a number of coverage criteria, the main ones beings:
* **Function coverage** -- Has each function in the program being called/executed?

* **Statement coverage** -- Has each statement in the program been executed?

* **Branch coverage** -- Has each branch of each control structure(such as in if and case statement) been executed 

* **Condition coverage**  -- Has each Boolean evaluated both to true and false?
 
##Why is test coverage useful? 

* code coverage data gives an important insight how effective our tests are, what parts of our source code are throughy executed 

* to find out specific areas of code which are not exercised by our tests 

###What is the difference between Istanbul and nyc?
* **Istanbul** and **NYC** both are tools to check code coverage.
* The original purpose of nyc was to allow a user to capture test coverage, regardless of how programs are spawning subprocesses, without requiring any changes in the instrumented code. This is useful for:

* tests that spawn sub-processes, e.g., in the yargs codebase we have a set of tests that spawn the CLI.

* some test frameworks, e.g., ava, tap., run their tests within subprocesses -- nyc provides a simple mechanism for adding coverage to these technologies.

* Istanbul and nyc are currently being merged. 

##How would you use them to improve your testing?
* code coverage measures the degree of written codes being executed by given tests. So, based on code coverage report of source code & test.js developers can improve/ optimize source codes by removing unneccessary lines to increase conciseness and to add additional tests. 


##Use Istanbul/nyc to calculate your code coverage for the TDD workshop.

* ####block of codes with unused line
![codes with unused line](https://files.gitter.im/rinoma/mvtE/Screen-Shot-2017-07-10-at-15.22.37.png)

* ####code coverage for source code decreases
![lower percentage](https://files.gitter.im/rinoma/mvtE/Screen-Shot-2017-07-10-at-15.22.23.png)

* ####test.js with irrelevant test
![random tests included](https://files.gitter.im/rinoma/mvtE/Screen-Shot-2017-07-10-at-15.36.54.png)

* ####code coverage for test.js decreases 
![lower coverage percentage for test.js] (https://files.gitter.im/rinoma/trGG/Screen-Shot-2017-07-10-at-16.20.05.png)

## why inspect code coverage of both test.js and js? 
* we witnessed redundant or unneccessary lines in script.js decreases code coverage.

* *However*, we are not sure what could cause a code coverag of test.js to decrease. (other than putting irrelavant tests)   