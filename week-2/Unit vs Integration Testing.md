## Unit Testing

Unit Testing is a level of software testing where individual units/ components of a software are tested. The purpose is to validate that each unit of the software performs as designed. It usually has one or a few inputs and usually a single output.

While the developers can do their own unit test, it is not uncommon for developers to outsource it to a tester.

Benefits:
- Development is faster in the long run too. How? The effort required to find and fix defects found during unit testing is very less in comparison to the effort required to fix defects found during system testing or acceptance testing.
- The cost of fixing a defect detected during unit testing is lesser in comparison to that of defects detected at higher levels. Compare the cost (time, effort, destruction, humiliation) of a defect detected during acceptance testing or when the software is live.
- Debugging is easy. When a test fails, only the latest changes need to be debugged. With testing at higher levels, changes made over the span of several days/ weeks/ months need to be scanned.
- Codes are more reliable.


## Integration Testing:
Integration Testing is a level of software testing where individual units are combined and tested as a group.

This focuses mainly on the interfaces & flow of data/information between the modules. Here, priority is to be given for the integrating links rather than the unit functions which are already tested.

Different Methods of Integration Testing:
- Big Bang Integration Testing
  - Wait for all modules to be developed before testing it out
  - Unfortunately, this increase project execution time, as developers have to wait for the others
  - Difficult to trace root cause of bugs
  
- Incremental Approach
  - One-by-one and whenever modules are available.
  - Two different Incremental Testing:
    - Top-Down Approach: Higher level modules are tested first
      - Starts from the top most module and gradually progress towards the lower modules. Only the top module is unit tested in isolation. After this, the lower modules are integrated one by one. The process is repeated until all the modules are integrated and tested.

    - Bottom-Up Approach: Lower level modules are tested first
      - Starts from the lowest or the innermost unit of the application, and gradually moves up. This integration continues till all the modules are integrated and the entire application is tested as a single unit.

