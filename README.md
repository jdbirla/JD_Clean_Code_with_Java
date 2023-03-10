# The JD Clean code with Java
- https://refactoring.guru/refactoring
# Refactoring
- Refactoring is a systematic process of improving code without creating new functionality that can transform a mess into clean code and simple design
## Clean code
- The main purpose of refactoring is to fight technical debt. It transforms a mess into clean code and simple design.
   -  Clean code is obvious for other programmers.
   -  Clean code doesn’t contain duplication.
   -  Clean code contains a minimal number of classes and other moving parts.
   -  Clean code passes all tests.
   -  Clean code is easier and cheaper to maintain!
## Technical debt
   
## When to refactor
  - Rule of Three
      - When you’re doing something for the first time, just get it done.
      - When you’re doing something similar for the second time, cringe at having to repeat but do the same thing anyway.
      - When you’re doing something for the third time, start refactoring.
  - When adding a feature
  - When fixing a bug
  - During a code review

## How to refactor
  -  The code should become cleaner.
  -   New functionality shouldn’t be created during refactoring.
  -   All existing tests must pass after refactoring.
---
## Refactoring Techniques
### Composing Methods
- The refactoring techniques in this group streamline methods, remove code duplication, and pave the way for future improvements.
#### Extract Method
  - Problem You have a code fragment that can be grouped together.
  - Solution Move this code to a separate new method (or function) and replace the old code with a call to the method.
#### Inline Method
  - Problem: When a method body is more obvious than the method itself, use this technique.
  - Solution: Replace calls to the method with the method’s content and delete the method itself.
#### Extract Variable
  - Problem: You have an expression that’s hard to understand.
  - Solution: Place the result of the expression or its parts in separate variables that are self-explanatory.
#### Inline Temp
  - Problem: You have a temporary variable that’s assigned the result of a simple expression and nothing more.
  - Solution: Replace the references to the variable with the expression itself.
#### Replace Temp with Query
  - Problem: You place the result of an expression in a local variable for later use in your code.
  - Solution: Move the entire expression to a separate method and return the result from it. Query the method instead of using a variable. Incorporate the new method in other methods, if necessary.
#### Split Temporary Variable
  - Problem: You have a local variable that’s used to store various intermediate values inside a method (except for cycle variables).
  - Solution: Use different variables for different values. Each variable should be responsible for only one particular thing.
#### Remove Assignments to Parameters
  - Problem: Some value is assigned to a parameter inside method’s body.
  - Solution: Use a local variable instead of a parameter.
#### Replace Method with Method Object
  - Problem: You have a long method in which the local variables are so intertwined that you can’t apply Extract Method.
  - Solution: Transform the method into a separate class so that the local variables become fields of the class. Then you can split the method into several methods within the same class.
#### Substitute Algorithm
  - Problem: So you want to replace an existing algorithm with a new one?
  - Solution: Replace the body of the method that implements the algorithm with a new algorithm.
