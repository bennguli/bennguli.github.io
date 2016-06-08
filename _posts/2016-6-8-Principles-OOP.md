---
layout: post
title: Principles
---

<html>
<head>
<body>---

<b><strong><title> object oriented programming</title></strong></b>
</head>


<p>Languages that support object-oriented programming typically use inheritance for code reuse and extensibility in the form of either classes or prototypes. Those that use classes support two main concepts:<br />
<br />
Classes - the definitions for the data format and available procedures for a given type or class of object; may also contain data and procedures (known as class methods) themselves. i.e. Classes contains the data members and member functions.<br />
Objects - instances of classes<br /></p>
<p>Objects sometimes correspond to things found in the real world. For example, a graphics program may have objects such as "circle", "square", "menu". An online shopping system might have objects such as "shopping cart", "customer", and "product". Sometimes objects represent more abstract entities, like an object that represents an open file, or an object which provides the service of translating measurements from U.S. customary to metric.</p>
<p>
Each object is said to be an instance of a particular class (for example, an object with its name field set to "Mary" might be an instance of class Employee). <br/>Procedures in object-oriented programming are known as methods; variables are also known as fields, members, attributes, or properties. This leads to the following terms:<br/>
Class variables - belong to the class as a whole; there is only one copy of each one<br />
Instance variables or attributes - data that belongs to individual objects; every object has its own copy of each one<br />
Member variables - refers to both the class and instance variables that are defined by a particular class<br />
Class methods - belong to the class as a whole and have access only to class variables and inputs from the procedure call<br />
Instance methods - belong to individual objects, and have access to instance variables for the specific object they are called on, inputs, and class variables.</p>
<p>Objects are accessed somewhat like variables with complex internal structure, and in many languages are effectively pointers, serving as actual references to a single instance of said object in memory within a heap or stack. They provide a layer of abstraction which can be used to separate internal from external code.<br/> External code can use an object by calling a specific instance method with a certain set of input parameters, read an instance variable, or write to an instance variable. Objects are created by calling a special type of method in the class known as a constructor. A program may create many instances of the same class as it runs, which operate independently. This is an easy way for the same procedures to be used on different sets of data.</p>
<p>
Object-oriented programming that uses classes is sometimes called class-based programming, while prototype-based programming does not typically use classes. As a result, a significantly different yet analogous terminology is used to define the concepts of object and instance.</p>
<p >


<p>Encapsulation
If a class disallows calling code from accessing internal object data and forces access through methods only, this is a strong form of abstraction or information hiding known as encapsulation. java languange let classes enforce access restrictions explicitly, for example denoting internal data with the private keyword and designating methods intended for use by code outside the class with the public keyword. Methods may also be designed public, private, or intermediate levels such as protected (which typically allows access from other objects of the same class, but not objects of a different class). In other languages (like Python) this is enforced only by convention (for example, private methods may have names that start with an underscore). Encapsulation prevents external code from being concerned with the internal workings of an object. This facilitates code refactoring, for example allowing the author of the class to change how objects of that class represent their data internally without changing any external code (as long as "public" method calls work the same way). It also encourages programmers to put all the code that is concerned with a certain set of data in the same class, which organizes it for easy comprehension by other programmers. Encapsulation is a technique that encourages decoupling.</p>

<p>Composition, inheritance, and delegation.
<p>Objects can contain other objects in their instance variables; this is known as object composition. For example, an object in the Employee class might contain (point to) an object in the Address class, in addition to its own instance variables like "first_name" and "position". Object composition is used to represent "has-a" relationships: every employee has an address, so every Employee object has a place to store an Address object.</p>
<br />
Languages that support classes almost always support inheritance. This allows classes to be arranged in a hierarchy that represents "is-a-type-of" relationships. For example, class Employee might inherit from class Person. All the data and methods available to the parent class also appear in the child class with the same names. For example, class Person might define variables "first_name" and "last_name" with method "make_full_name()". These will also be available in class Employee, which might add the variables "position" and "salary". This technique allows easy re-use of the same procedures and data definitions, in addition to potentially mirroring real-world relationships in an intuitive way. These classes and subclasses correspond to sets and subsets in mathematical logic. Rather than utilizing database tables and programming subroutines, the developer utilizes objects the user may be more familiar with: objects from their application domain.[8]<br />
<br />
Subclasses can override the methods defined by superclasses. Multiple inheritance is allowed in some languages, though this can make resolving overrides complicated. Some languages have special support for mixins, though in any language with multiple inheritance, a mixin is simply a class that does not represent an is-a-type-of relationship. Mixins are typically used to add the same methods to multiple classes. For example, class UnicodeConversionMixin might provide a method unicode_to_ascii() when included in class FileReader and class WebPageScraper, which don't share a common parent.<br />
<br />
Abstract classes cannot be instantiated into objects; they exist only for the purpose of inheritance into other "concrete" classes which can be instantiated. In Java, the final keyword can be used to prevent a class from being subclassed.<br />
<br />
The doctrine of composition over inheritance advocates implementing has-a relationships using composition instead of inheritance. For example, instead of inheriting from class Person, class Employee could give each Employee object an internal Person object, which it then has the opportunity to hide from external code even if class Person has many public attributes or methods. Some languages, like Go do not support inheritance at all.<br />
<br />
The "open/closed principle" advocates that classes and functions "should be open for extension, but closed for modification".<br />
<br />
Delegation is another language feature that can be used as an alternative to inheritance.<br />
<br />
Polymorphism<br />
Subtyping, a form of polymorphism, is when calling code can be agnostic as to whether an object belongs to a parent class or one of its descendants. For example, a function might call "make_full_name()" on an object, which will work whether the object is of class Person or class Employee. This is another type of abstraction which simplifies code external to the class hierarchy and enables strong separation of concerns.
</body>
</html>
