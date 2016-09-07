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

* What is an iterator?

* What's a hash? How do you add/remove values?

* Explain truthy & falsey in Ruby. 
  * In Ruby only false and nil are falsey. Everything else is truthy (yes, even 0 is truthy). [Sourced from Learn](https://learn.co/tracks/full-stack-web-development/intro-to-ruby-development/logic-and-conditions/truthiness)
  * The double bang operator: A "double-bang operator" (!!) will return true or false based on whether a value is truthy or falsey to begin with.

* What does Ruby's flatten do?

* Explain the ||= operator.

* When to use return in Ruby code?

* Explain some of the looping structures available in Ruby, and when you would use one over another.
  * For loop, while loop, until loop...

* Is Ruby a statically typed or a dynamically typed language?
  * It's dynamically typed since the type checking is done at runtime.

* How does a symbol differ from a string?
  * Symbols are immutable and reusable, retaining the same object_id. Be prepared to discuss the benefits of using symbols vs. strings, the effect on memory usage, and in which situations you would use one over the other

### Variables
* How and when would you declare a Global Variable?
  * Global variables are declared with the ‘$’ symbol and can be declared and used anywhere within your program. You should use them sparingly to never.

* Describe the difference between class and instance variables.
  * Class variables are created with the prefix ‘@@’ and are shared by all objects in a class. Instance variables are created with the prefix ‘@’ and belong to a single object within a class.Beyond the simple textbook definition, be able to describe an example of a class and how you would use class and instance variables within it, and how they relate to issues of class inheritance.

### Objects
* What is an object?
  * An object is an instance of a class and has state, behavior, and identity. In a plain text example, you can say that a truck and a car are both objects of the class Vehicle, or that apple and pear are both objects of the class Fruit. You should be able to explain in detail how object structure and behavior relate to their common class, and why this is so important in Ruby

* What's a first-class object?

* What is self?

* Explain "In Ruby everything is an object"
  * Methods are not objects. Blocks are not objects. Keywords are not objects. However, there exist Method objects and Proc objects, and some keywords refer to objects.

### Methods
* How would you create getter and setter methods in Ruby?
  * Setter and getter methods in Ruby are generated with the attr_accessor method. attr_accessor is used to generate instance variables for data that’s not stored in your database column. You can also create these methods manually.

* What's the difference between public / private / protected methods?
  * Public methods can be called by all objects and subclasses of the class in which they are defined in.
  * Protected methods are only accessible to objects within the same class.
  * Private methods are only accessible within the same instance.

* What is a singleton method?

* Are instance methods public or private? What about class methods?
  * Both are public by default.

* What does ! at the end of a method signify?

### Blocks, Procs, Lambdas, Iterators
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
  * #map
  * #collect
  * #find
  * #detect
  * #select
  * #reject
  * #inject
  * #reduce

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

* How do you define a class?

* What is a factory method?
  * An initialization method that creates specialized instances of a class.

* Is #initialize an instance method or a class method? Is it public or private?
  * An instance method, private by default.

* What is a singleton? How would you create a singleton?
  * A class having only a single instance.
  * Create one by including the Singleton module.

* Explain the difference between a class and a module. When would you use each?
  * A module cannot be subclassed or instantiated, and modules can implement mixins.

### Rails

* Explain MVC.

* Explain Rails filters
  * ex: before_save, after_save 

* Super - What does it do? How does it respond when you call with or without () ? 

### Web Security
* What is a cookie?

* What is CSRF? How does Rails protect against it?
  * CSRF stands for Cross-Site Request Forgery. This is a form of an attack where the attacker submits a form on your behalf to a different website, potentially causing damage or revealing sensitive information. Since browsers will automatically include cookies for a domain on a request, if you were recently logged in to the target site, the attacker’s request will appear to come from you as a logged-in user (as your session cookie will be sent with the POST request).

  * In order to protect against CSRF attacks, you can add protect_from_forgery to your ApplicationController. This will then cause Rails to require a CSRF token to be present before accepting any POST, PUT, or DELETE requests. The CSRF token is included as a hidden field in every form created using Rails’ form builders. It is also included as a header in GET requests so that other, non-form-based mechanisms for sending a POST can use it as well. Attackers are prevented from stealing the CSRF token by browsers’ “same origin” policy.

### ActiveRecord

* Explain the difference between a has_one and belongs_to association.
  * has_one: Indicates a direct 1:1 relationship between objects where each instance of a model contains one instance of another model.
  * belongs_to: Represents the inverse of a has_one (or has_many) association.
  * A good way to remember this is that if a table has foreign keys, its model should have a belongs_to association.

* Explain polymorphic associations.
  * Polymorphic associations allow a model to belong to more than one other model through a single association.

* What's the difference between find() & find_by_id()?

* What are the various model validations in Rails?

### Gems
* What are gems and what are your favorites?
  * Gems are packaged bits of Ruby code that you can install to extend or add functionality to your app.

### Testing
* What is functional testing?
  * Functional testing in Rails allows you to test the response of  various actions contained in a controller. Using the Rails default test library, mini test, functional tests use a collection of assert statements that will tell your testing library to expect a certain response based on a control request passed in (either a get, post, patch, put, head, delete request).
