
# Delegation
A object delegates its work to another object. Use abstraction (protocol) and weak reference

# Singleton
One unique object to be shared and access across the whole app. 
using static/class property. Hide the init() to prevent multiple instances to be allocated

# Pros
- Easy to access and use 
- Easy to trace the logic flow

# Cons
- If it has shared state, it could cause unexpected behavior
- The object stays in the memory forever 
- make the code untestable if not used correctly (e.g: we should use DI for singleton)

# Coordinator
Using a coordinator to control the page transition of the app flow, instead of letting the ViewController to perform the transition by themselves.using a coordinator to control the page transition of the app flow, instead of letting the ViewController to perform the transition by themselves.using a coordinator to control the page transition of the app flow, instead of letting the ViewController to perform the transition by themselves.using a coordinator to control the page transition of the app flow, instead of letting the ViewController to perform the transition by themselves.using a coordinator to control the page transition of the app flow, instead of letting the ViewController to perform the transition by themselves.using a coordinator to control the page transition of the app flow, instead of letting the ViewController to perform the transition by themselves.
Coordinator is a specialized case of delegation.
- Helps migrate the transition code out of the VC
- Add more flexibility in controlling app flow

# Observer
- Publish/subscribe pattern. E.g: NotificationCenter, KVO, property observer.

# Adapter
A technique to make 2 incompatible interface to work together
## Example: 
### Problem:
Module A offers verifyUser(_: A.User) -> Result<A.Verification, Error>, Main module uses that API.
Then there's a module B offser similar function, but different API signature. => We need to write an adapter for B so it can be used in Main module 
### Solution: 
- Write a wrapper class
- Define a protocol to be used for both A and B's APIs to conform to 

# Factory
Abstract the initialization of an object behind a factory method. This helps decoupling the initialization of an object from the caller side. 

## Example: 
e.g: 
```
let apiService = ApiServiceClass() // Bad
let apiService = self.apiServiceFactory.apiService() // Good
```

# Builder
Given a type with complex init(...) signature with many arguments. We can use builder to abstract the init code from client.
Builder also often comes with chaining to provide flexible configuration for object construction

# Decorator
A wrapper with the same interface with the wrapped object to extend its functionality. This is a form of composition over inheritance and also an example of Open-Close principle.

# Facade  
Offer a simple interface for complex subsystems behind it. 

**Example**: A Repository whose responsible is to fetch data using this logic: If data is already in the persistent store -> Return the data immediately, otherwise request the network -> Save the data to persistent store -> Return the data to caller. 




