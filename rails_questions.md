# Rails

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

### Testing
* What is functional testing?
  * Functional testing in Rails allows you to test the response of  various actions contained in a controller. Using the Rails default test library, mini test, functional tests use a collection of assert statements that will tell your testing library to expect a certain response based on a control request passed in (either a get, post, patch, put, head, delete request).
