# Ruby

### History

### Etc

* What does DRY stand for?

* What's the difference betweent attr_accessor and attr_accessible?

* What's a Ruby Module?

* What's the difference between extend and include?

### Data Types, Operators, Built in methods, Loops
* What is the splat operator and what would you use it for?

* Explain how Ruby's Map function actually works. 

* What's a hash? How do you add/remove values. Review these hash methods: #keys, #values, #min, #sort, #min_by.

* Explain truthy & falsey in Ruby. 
  * In Ruby only false and nil are falsey. Everything else is truthy (yes, even 0 is truthy). [Sourced from Learn](https://learn.co/tracks/full-stack-web-development/intro-to-ruby-development/logic-and-conditions/truthiness)
  * The double bang operator: A "double-bang operator" (!!) will return true or false based on whether a value is truthy or falsey to begin with.

* What does Ruby's flatten do?
 * a =  {1=> "one", 2 => [2,"two"], 3 => "three"}
 * a.flatten    # => [1, "one", 2, [2, "two"], 3, "three"]
 * a.flatten(2) # => [1, "one", 2, 2, "two", 3, "three"]

* Explain the ||= operator.

* When to use return in Ruby code?

* Explain some of the looping structures available in Ruby, and when you would use one over another.
  * Loop do, for loop, while loop, until loop...

* The difference between Iteration & Looping?
  * Looping occurs when you tell your program to do something a certain number of times. 
  * Iteration occurs when you have a collection of data (for example, an array), and you operate on each member of that collection.
   * Times, each

* Is Ruby a statically typed or a dynamically typed language?
  * It's dynamically typed since the type checking is done at runtime.

* How does a symbol differ from a string?
  * Symbols are immutable and reusable, retaining the same object_id. Be prepared to discuss the benefits of using symbols vs. strings, the effect on memory usage, and in which situations you would use one over the other

### Variables
* How and when would you declare a Global Variable?
  * Global variables are declared with the ‘$’ symbol and can be declared and used anywhere within your program. You should use them sparingly to never.

* Describe the difference between class and instance variables.
  * Class variables are created with the prefix ‘@@’ and are shared by all objects in a class. 
  * An instance variable is a variable that is accessible in any instance method in a particular instance of a class.Instance variables are created with the prefix ‘@’ and belong to a single object within a class.Beyond the simple textbook definition, be able to describe an example of a class and how you would use class and instance variables within it, and how they relate to issues of class inheritance.

### Objects
* What is an object?
  * An object is an instance of a class and has state, behavior, and identity. In a plain text example, you can say that a truck and a car are both objects of the class Vehicle, or that apple and pear are both objects of the class Fruit. You should be able to explain in detail how object structure and behavior relate to their common class, and why this is so important in Ruby

* What's a first-class object?

* What is self?

* Explain "In Ruby everything is an object"
  * Methods are not objects. Blocks are not objects. Keywords are not objects. However, there exist Method objects and Proc objects, and some keywords refer to objects.

* Explain the difference between procedural programming & oo.
  *  Procedural programming, we have data and we have the procedures or instructions for operating on that data. In procedural programming, data and procedures, or instructions, are two separate things. In object-oriented programming, we have units of code that contain both data and instructions, such that an "object" operates on its own data structure. [Source](https://learn.co/tracks/full-stack-web-development/intro-to-ruby-development/oo-tic-tac-toe/procedural-vs-object-oriented-ruby)

### Methods
* How would you create getter and setter methods in Ruby?
  * Setter and getter methods in Ruby are generated with the attr_accessor method. attr_accessor is used to generate instance variables for data that’s not stored in your database column. You can also create these methods manually.

* Explain the difference between a setter & a getter method.
  * Ex) #name, #name=

* What's the difference between public / private / protected methods?
  * Public methods can be called by all objects and subclasses of the class in which they are defined in.
  * Protected methods are only accessible to objects within the same class.
  * Private methods are only accessible within the same instance. Private methods cannot be called by an explicit receiver. The receiver of a private method is always self. They are a way of encapsulating functionality within a class.

* What is a singleton method?
  * A method attached to an instance of a class.

* Are instance methods public or private? What about class methods?
  * Both are public by default.

* What does ! at the end of a method signify?

### Blocks, Procs, Lambdas, Iterators, Enumerables
* A block is a chunk of code between braces, { } or between do/end keywords that you can pass to a method almost exactly like you can pass an argument to a method. There are some methods, like iterator methods, that can be called with a block, i.e. accompanied by a block denoted with { } or do/end. Such a method would run and pass, or yield, data to the code in the block for that code to operate on or do something with.

* Does a while block define a new scope?
  * No.

* Is a block an object?
  * A: No. A block is a syntactic structure of the interpreter. A block can be converted to a Proc object.

* What is a Proc? 
  * Procs, short for procedures, act similar to blocks, but can be saved as variables and reused. Think of them as blocks you can call over and over again on multiple arrays.

* What is a lambda?
  * Lambdas are very similar to procs in terms of functionality. However, they have a few key differences. Lambdas check the number of arguments passed and will return an error if you try to pass the wrong number (while procs set extra variables to nil). The other difference is that lambdas can handle a return function, whereas procs will return an error.

* What's the difference between Procs and lambdas? 

* Know your enumerables!
  * #map / #collect vs #each
  * #detect / #find  - Whereas #select will return all elements from the original collection that cause the block to evaluate to true, #detect will only return the first element that makes the block true. 
  * #select
  * #reject
  * #inject
  * #reduce
  * #any?
  * #none?
  * #all?

* Why would you use #each instead of for/in?
  *  It's the "Ruby way" - an example of how Ruby defines methods that mimic natural language concepts. Iterator methods such as #each read more naturally. #each is a block so it defines a new variable scope. for/in depends on the existence of #each which implies that #each is a more fundamental aspect of the language.

* Why/how is a block anonymous?
  * It doesn't have a name. It doesn't exist beyond it's execution unless converted to a Proc object.

* Difference between block invocation & method invocation?
  * Ruby will throw an exception if more than the expected number of arguments are passed to a method. A block will simply ignore the extra values.

### Classes
* Explain Ruby inheritance

* What is Class::new ?
  * A class method of the Class object which creates new classes.

* How do you define a class? What about instances?
  * Classes are the blueprints that define the behavior and information our objects will contain. They let us manufacture and instantiate new instances.
  * An instance is a single occurrence of an object. Instances refer to the individual objects produced from the class.

* What is a factory method?
  * An initialization method that creates specialized instances of a class.

* Is #initialize an instance method or a class method? Is it public or private?
  * An instance method, private by default. An #initialize method is a method that is called automatically whenever #new is used. The initialize method is what's called a callback method, because it is automatically invoked every time the #new method is used to create a new instance of the class.

* What is a singleton? How would you create a singleton?
  * A class having only a single instance.
  * Create one by including the Singleton module.

* Explain the difference between a class and a module. When would you use each?
  * A module cannot be subclassed or instantiated, and modules can implement mixins.


### Gems
* What are gems and what are your favorites?
  * Gems are packaged bits of Ruby code that you can install to extend or add functionality to your app.
