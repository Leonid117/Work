# User interface
# User interface
### What is Responder Chain?
Responder Chain — it is a hierarchy of objects that can respond to received events.

### What's the difference beetween frame и bound?
Bounds refers to the views own coordinate system while Frame refers to the views parent coordinate system.

### What is Live Rendering? And how to set it up?
In Xcode 6 and iOS 8 SDK, Apple added the ability to render custom components and edit their properties directly in the standard Interface Builder
The @IBDesignable attribute allows the Interface Builder to update specific elements.
live rendering is a great way to speed up prototyping, developing and debugging custom views. It is especially good that during live rendering, the layout constraints and intrinsic content size of your view are taken into account, so autolayout works without stub constraints.

# Objective-C
### Why don't we use strong for enum in Objective-C?
Because enums are not objects, we don't specify strong or weak here.

### What is @synthesize in Objective-C?
Synthesize generates getter and setter methods for your property.

### What is @dynamic in Objective-C?
@dynamic just tells the compiler that the getter and setter methods are implemented not by the class itself but somewhere else (like the superclass or will be provided at runtime)

### What is dynamic dispatch?
Dynamic Dispatch is the process of selecting the implementation of a polymorphic operation, which is a method or function to call at run time. This happens when we want to call our methods as a method on an object. Swift doesn't do Dynamic Dispatch by default.

#### Dynamic Dispatch
Messaging is the power of Objective-C and the Objective-C runtime. Each message is sent dynamically. What does it mean? The Objective-C runtime shows you which method to call for a message at run time by checking the class hierarchy. This is why Objective-C is such a dynamic language. The dynamism of Objective-C is also the ability of several Cocoa features, including Key-Value Observing, as well as the behavior model.
There is one major drawback to dynamic dispatch. Because the runtime must determine which method to call on a message, dynamic dispatch is slower than static dispatch. In other words, dynamic dispatch comes with a small overhead.

#### Static Dispatch
The compiler can determine at compile time which method to call on a message. As the name suggests, this is not a dynamic send. What is lost in flexibility and dynamism is gained in performance.
The runtime does not need to determine which method to call at run time. The little performance associated with dynamic dispatch is simply not there when using direct dispatch.

# Simple Questions

### What's difference between strong, weak, read only и copy?
The property attributes strong, weak, assign determine how the memory for this property will be managed.

Strong : Through the life of the object, the reference count will be increased and the reference will be maintained

Weak : It can be said as a non-strong reference that means it refers to the fact that we are referring to an object but not adding to its reference count. It’s often used to establish a parent-child relationship. The parent has a strong connection with the infant, but the child has only a small connection with the parent.

Read-only : Initially, The property will be set and it can’t be changed.

Copy : It means that when an object is created, we’re copying its value. Also prevents its value from changing.

### What is completion closure?
Closures are self-contained blocks of functionality that can be passed around and used in your code.

- completion closure come in very handy when our application calls an API and we need to do something when that task is done, such as updating the UI to display the data from the API call. Completion closure can be found in Apple APIs like dataTaskWithRequest and can be very useful in your code.
- The completion closure takes a code with three arguments: (NSData?, NSURLResponse?, NSError?), which returns nothing: void. It means completion.
- Completion closure should be marked with @escaping as they are executed after the function is executed.

### What is NSError?
Information about an error condition including a domain, a domain-specific error code, and application-specific information.
There are three parts to an NSError object: the domain, the error code, and a dictionary of user information. The domain is a string that identifies which category the error belongs to.

### What is RegExp?
Regular expressions are special pattern strings that describe how to search within a string.

### What is operator overloading?
Operator overloading allows you to change the way existing operators work with specific structures or classes. This is exactly what you need – you’d like to change the way the + operator works with Int arrays!


The example below shows how the addition (+) arithmetic operator can be implemented for a custom structure.

```
struct Vector2D {
    var x = 0.0, y = 0.0
}
 
extension Vector2D {
    static func + (left: Vector2D, right: Vector2D) -> Vector2D {
        return Vector2D(x: left.x + right.x, y: left.y + right.y)
    }
}
```

### What is the difference between synchronous and asynchronous task?
Synchronous: waits for the task to complete. Asynchronous: Finishes a task in the background and notifies you when it's completed.

### Why do we use synchronized?
Synchronized ensures that only one thread can execute this code in a block at any given time.

### What is Enum?
In Swift, an enum (short for enumeration) is a user-defined data type that has a fixed set of related values. We use the enum keyword to create an enum. For example, enum Season { case spring, summer, autumn, winter } Here, Season - name of the enum.

# Difficult Questions 

### What is b-trees?
These are search trees that provide an ordered store of key values with excellent performance characteristics. Each node keeps a sorted array of its own elements and another array for its children.
https://en.wikipedia.org/wiki/B-tree

### What is TVMLKit?
TVMLKit — it is the link between TVML, JavaScript and native tvOS app.

### What are the limitations of the platform tvOS?
First, tvOS does not support browsers and therefore you will not be able to use WebKit or any other web rendering engine. This means that your application will not be able to reference the web browser at all, including web links, OAuth, or social networking sites.
Second, tvOS apps cannot explicitly use local storage. Devices are shipped with either a 32 GB or 64 GB hard drive when the product is launched, but applications are not allowed to directly save files to the device.
A tvOS app bundle cannot exceed 4 GB.





