# Metatype
Data.self presents the **type object (which is a singleton)**, Data.Type refers to the **type of that type object** 

One way to easily understand the concept of P.Type and P.self is to **view P as an object instead of a type**
Calling **P.init() is equivalent to P.self.init()**. P.init() is the shorthand syntax to _hide the singleton type object_. 
<img width="526" alt="image" src="https://github.com/hoangelec/Knowledge-consolidation/assets/9737526/bc315716-5911-48c6-8aae-7a8e3530b8d4">

# Objc memory management
When you create an object, it has a retain count of 1.

When you send an object a retain message, its retain count is incremented by 1.

When you send an object a release message, its retain count is decremented by 1.

When you send an object a autorelease message, its retain count is decremented by 1 at the end of the current autorelease pool block.

If an object’s retain count is reduced to zero, it is deallocated.

# UIView vs UILayer
**UIView**
- Represents a rectangle in the UI system. 
- More complex functionalities: handle user interactions, gesture, etc.. 
- Doesn't draw the visual content by itself."

**UILayer**
- Lightweight object that is optimized for drawing visual content and animation
- Doesn't handle event

# Runloop vs DispatchQueue
## Runloop
A mechanism that manage events, timer and async tasks in event-driven programming. 
- A runloop operation on a specific thread. Instead of constantly polling for event, it's optimized so that it's only take up thread's execution time when events are available.  
When an event arrives, the runloop wakes up and process the event/task. 
- a runloop can only run on 1 mode at a time. For each mode, the runloop only care about specifics input sources 

## DispatchQueue
DispatchQueue is used to manage the concurrent execution of tasks, abstracting away the low-level details of threading, while RunLoop is focused on processing events and tasks, often associated with user interactions and managing asynchronous operations in an event-driven manner

# setNeedsLayout vs layoutIfNeeded vs layoutSubviews
## setNeedsLayout
- Tell the OS to update the view in the next update cycle by the Main runloop -> Thus async action
- Can consolidate multiple views' update into 1 update cycle -> Better for performance
## setNeedsLayout
- Tell the OS to update the view in the next update cycle by the Main runloop -> Thus async action
## layoutSubviews
By default, this method relies on the constraints of the view to dictate the size and position of any subviews
We can override this to achieve a custom layout for for subviews
we should not call this method directly. 

# @escaping closure
Because a closure can capture variables/objects of the enclosing func, they should be retained even after the func has returned. 
The compiler will retain the capture variables/objects until the closure is deallocated.

# Capture List
Closure implicitly captures a **strong reference** to a variable/object from the outside
When we explicitly define a capture list, the closure captures the **underlying value** of the variable and treat it as a **let**

# Serial queue suspend() and resume()

We can tell a serial queue to stop dispatching its work item to the thread pool by calling **queue.suspend()**
Likewise, we can tell the queue to continue after suspending by calling **queue.resume()**

# struct vs class
## Struct
- Value type
- No retain cycle
- Stored in stack, less memory cost due to refCount and refType memory slot
- No inheritance. 
=> **Better performance** (guaranteed static dispatch, no refCount, stored in stack)

## class
- Reference type
- Stored in heap, more cost
- Can inherit
- Can have dynamic dispatch (slower performance)

# Message dispatching in Swift
## Static
- The compiler can determine the execution (binary) code at **compile time**
- Value types **all use static dispatch** (because it cannot be inherited)
- Extension methods are **generally static dispatch** (except that it's declared with **@objc inside a class extension**)
## Dynamic
- The system can only determine the correct implementation **at run time**.
- In case of table lookup, the virtual table is constructed **at compile time**. 
- In case of message dispatch, the the method/message is send to the object, then it tries to look for the implementation of the message up the class hierarchy
- The message dispatch table **can be modified at runtime**



