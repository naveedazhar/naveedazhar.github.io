# ⚒ SOLID

Yet another common programming principle. This one though, stands for:

* Single Responsibility Principle
* Open-Closed Principle
* Liskov Substitution Principle
* Interface Segregation Principle
* Dependency Inversion Principle

So if you think about it, it’s really 5 principles all packed into one. So let’s unpack it to make some sense out of it.

### Single Responsibility Principle <a href="#53b7" id="53b7"></a>

Here we’re talking about how your functions should only do one thing and nothing else. If you’re familiar with \*nix-based systems, such as Linux distributions, macOS or similar, you’ve probably experienced their terminal and used some of their commands (I’m talking about things like `ls` , `cd`, and the like). They follow this principle as well, they only perform one type of task, mind you, they do everything related to that task, but you won’t find a command line utility that, for example, helps you change directory and list their content.

The point here is that your functions should be simple enough to only have one responsibility, if you need more complex behavior, then combine their input and output in order to compose them.

And although I’m talking about functions here, this principle applies to everything in our industry. Think about the architecture of a platform, if instead of creating a mega-module responsible of doing **everything** you need, you create several microservices responsible of their own little tasks, this system becomes a lot easier to maintain and grow. The same goes for functions, simpler functions are easier to maintain, to read and understand and even to write.

Essentially, if you find yourself writing a function called `getUserAndRelatedBooks` where you actually have all the logic for both tasks, consider creating two functions: `getUser` and `getUsersBooks` where the second one takes the output of the first one, so you can then implement `getUserAndRelatedBooks` simply saying `getUsersBooks(getUser)` (i.e by composing them).

### Open-Closed principle <a href="#0c7c" id="0c7c"></a>

This one is a reference to the fact that your modules or libraries (depending on how you’re exporting your code) need to be Open for extension (as in, extending their behavior) but Closed for modification (I mean, nobody wants to go around changing other peoples modules).

The moment you find others having to change your code in order for them to add or extend the existing behavior, you my friend, have successfully failed the Open-Closed principle.

The following code, for example, fails the principle, because if you needed to add extra cities to make it work for your use case, you would have to open the file and modify the `knownCities` array.

However, the following code fixes that and remains Open-Closed.

Now the `addValidCity` method allows you to extend the behavior to make it work for you, without having to change its code.

### Liskov Substitution Principle <a href="#b97e" id="b97e"></a>

Nice name uh? This is taking us as close as I like to be to programming theory. I don’t want to go too deep into it, but let’s first take a look at what this principle, also known as LSP, states:

> _Functions that use pointers or references to base classes must be able to use objects of derived classes without knowing it._

The first thing you can see is that we’re dealing with an OOP principle, one meant to help us correctly use inheritance and avoid using it when we can use other alternatives.

Think about the following example: in geometry, a square can be considered a specialization of a rectangle, since essentially it is a rectangle with matching width and height. But if you try to model that relationship with code, such as the code below:

The abstraction makes no sense, since using either the `setWidth` or `setHeight` methods they would not modify the other, essentially turning the square into a rectangle, which is not what you want. So the above code is breaking Liskov Substitution Principle.

In other words, this principle makes sure your code is using inheritance correctly, so even though it might sound like a terrible name, you should keep it in mind when you’re designing your classes.

### Interface Segregation Principle <a href="#8b34" id="8b34"></a>

This one references the fact that you should not expose your users (i.e developers using your code) to unneeded methods. Remember, an interface is just a contract for your classes (listing the methods that need to be implemented). So if you’re creating interfaces (for example in TypeScript), make sure the required methods that need to be implemented are the ones your users will need, don’t force them to implement methods that are optional.

Consider the above code, users of `MyModule` might want to implement the `close` and `open` methods, but if they don’t have to deal with IE8, then that last method is definitely not needed.

So this principle takes care of looking out for interface design. Try to avoid blotted interfaces and segregate the methods into different ones, allowing your users to decide how which ones to implement depending on their needs.

### Dependency Inversion Principle <a href="#6db0" id="6db0"></a>

Finally, closing the SOLID concept, we have dependency inversion, also known as dependency injection.

In essence, this principle states that if you have dependencies in your code, you should allow for them to be injected into your logic. How do you ask? Simple! By allowing them to be passed in as parameters.

This is a very useful tool for many scenarios, one of them being unit testing, because if you’re testing code that you wrote and that depends on a third party library, you can inject a mocked version of that library to control its behavior. Let me show you an example:

Consider the above code, the connection to the database is declared and performed inside the same module, but you’re only exporting the `saveUser` function. So if you were to test it somehow, it would automatically try to connect to the database and accomplish its original goal: save the user data into the database.

However, if you were to allow for dependency injection and receive the database connection (which is an external dependency) as a second parameter, then you would be able to inject a mocked version in the future:

Now you can even switch dependencies for other purposes such as using a different module to connect to the database and your code is not affected.

Dependency injection is a wonderful tool, it creates a very extensible design and shows you care about extensibility. So consider it while defining your modules.
