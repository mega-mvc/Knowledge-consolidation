# SOLID


SOLID tells us how to arrange functions and data structures into classes / modules, and how those classes / modules should be **interconnected**. 

SOLID is therefore applied at the mid-level (class / module level).

# Single Responsibility
A class/module should only have 1 reason to change. To simplify: A class/module should server one purpose for one user. 

In short: Small interfaces help reduce blast radius and promote good design.

# Open-Close
Write your code so that when you want to add more functionalities, add new code instead of (drastically) modify the existing one

**Practical example**: When we want to add new functionalities to an existing class, we can use Decorator: https://refactoring.guru/design-patterns/decorator/swift/example

# Liskov substitution principle
When substitute an object of base class with subclass, the logic should still stay correct. 

Write function/code so that when you use an object of a subclass in place of a superclass, it doesn't behave incorrectly. 

Practical application: If we have a superclass that is supposed to be subclassed in the future, we should write test cases for that that superclass. When we subclass it, we write the same test cases for said subclasses to make sure the subclasses don't break the test cases.

# Interface Segregation
An interface of a type should not contain functions that it doesn't use (fat interface)
**Simply put**: Breakdown a big protocol into smaller ones, then use protocol composition to compose a specific, bigger protocol. 

<img width="1012" alt="image" src="https://github.com/hoangelec/Knowledge-consolidation/assets/9737526/1a75062f-e77a-4479-aca9-80004e8958e8">

# Dependency Inversion
Higher module should not depend on detailed implementation of lower module, instead it should use abstraction. 
This principle is particularly important when implementing CLEAN architecture. 

<img width="668" alt="image" src="https://github.com/hoangelec/Knowledge-consolidation/assets/9737526/d566af17-571f-4768-834c-57b024503724">
<img width="630" alt="image" src="https://github.com/hoangelec/Knowledge-consolidation/assets/9737526/b3b7368a-1bf1-4441-949c-d03f549eef73">





