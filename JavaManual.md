# Java manual
**Write a reference manual for the Java language. For each of the following topics, provide a description and (where applicable) a simple example:**

### values

The Java programming language is a statically typed language, which means that every variable and every expression has a type that is known at compile time.

The Java programming language is also a strongly typed language, because types limit the values that a variable can hold or that an expression can produce, limit the operations supported on those values, and determine the meaning of the operations. Strong static typing helps detect errors at compile time.

Literal String values are expressed within double quotes"".


### operations

**Operator:** specifies action to perform
**Operand:** a value being acted upon by an operator
**Operation:** a use of an operator. For example, in the operation 5 + 3, + is the operator, 3 and 5 are the operands.

**Java Operators:**

**arithmetic operators**
+ addition
- subtraction
* multiplication
/ division
% modulus

**assignment operators**	= += -= *= /= %= &= ^= |= <<= >>= >>>=
postfix/'''expr++ expr-- '''
unary	++expr --expr +expr -expr ~ !
multiplication, division	* / %
additive	+ -
shift	<< >> >>>
relational	< > <= >= instanceof
equality	== !=
bitwise AND	&
bitwise exclusive OR	^
bitwise inclusive OR	|
logical AND	&&
logical OR	||
ternary	? :

### variables
Variable names are also called fields in Java.

**Naming**

Variable names are case-sensitive. A variable's name can be any legal identifier — an unlimited-length sequence of Unicode letters and digits, beginning with a letter, the dollar sign "$", or the underscore character "_".

The convention, however, is to always begin your variable names with a letter, not "$" or "_". Additionally, the dollar sign character, by convention, is never used at all. You may find some situations where auto-generated names will contain the dollar sign, but your variable names should always avoid using it. A similar convention exists for the underscore character; while it's technically legal to begin your variable's name with "_", this practice is discouraged.

White space is not permitted.

Subsequent characters may be letters, digits, dollar signs, or underscore characters. Conventions (and common sense) apply to this rule as well. When choosing a name for your variables, use full words instead of cryptic abbreviations. Doing so will make your code easier to read and understand. In many cases it will also make your code self-documenting; fields named cadence, speed, and gear, for example, are much more intuitive than abbreviated versions, such as s, c, and g. Also keep in mind that the name you choose must not be a keyword or reserved word.

If the name you choose consists of only one word, spell that word in all lowercase letters. If it consists of more than one word, capitalize the first letter of each subsequent word (i.e. camelCase) The names gearRatio and currentGear are prime examples of this convention. If your variable stores a constant value, such as static final int NUM_GEARS = 6, the convention changes slightly, capitalizing every letter and separating subsequent words with the underscore character. By convention, the underscore character is never used elsewhere.

**The Java programming language defines the following kinds of variables:**

**Instance Variables **(Non-Static Fields) Technically speaking, objects store their individual states in "non-static fields", that is, fields declared without the static keyword. Non-static fields are also known as instance variables because their values are unique to each instance of a class (to each object, in other words); the currentSpeed of one bicycle is independent from the currentSpeed of another.
**Class Variables (Static Fields)** A class variable is any field declared with the static modifier; this tells the compiler that there is exactly one copy of this variable in existence, regardless of how many times the class has been instantiated. A field defining the number of gears for a particular kind of bicycle could be marked as static since conceptually the same number of gears will apply to all instances. The code static int numGears = 6; would create such a static field. Additionally, the keyword final could be added to indicate that the number of gears will never change.
Local Variables Similar to how an object stores its state in fields, a method will often store its temporary state in local variables. The syntax for declaring a local variable is similar to declaring a field (for example, int count = 0;). There is no special keyword designating a variable as local; that determination comes entirely from the location in which the variable is declared — which is between the opening and closing braces of a method. As such, local variables are only visible to the methods in which they are declared; they are not accessible from the rest of the class.
Parameters You've already seen examples of parameters, both in the Bicycle class and in the main method of the "Hello World!" application. Recall that the signature for the main method is public static void main(String[] args). Here, the args variable is the parameter to this method. The important thing to remember is that parameters are always classified as "variables" not "fields". This applies to other parameter-accepting constructs as well (such as constructors and exception handlers) that you'll learn about later in the tutorial.


### if else
Conditional statement where a certain block of code will be executed if the condition is true, otherwise the code block specified by the else is executed.
```
if (testscore >= 90) {
        grade = 'A';
    } else if (testscore >= 80) {
        grade = 'B';
    } else if (testscore >= 70) {
        grade = 'C';
    } else if (testscore >= 60) {
        grade = 'D';
    } else {
        grade = 'F';
    }
    System.out.println("Grade = " + grade);
```

### while
The while statement continually executes a block of statements while a particular condition is true. Its syntax can be expressed as:

```
while (expression) {
     statement(s)
}
```

You can implement an infinite loop using the while statement as follows:

```
while (true){
    // your code goes here
}

```

### for

The for statement provides a compact way to iterate over a range of values. The code within the block repeatedly loops until a particular condition is satisfied. The general form of the for statement can be expressed as follows:

```
for (initialization; termination;
     increment) {
    statement(s)
}
```

When using this version of the for statement, keep in mind that:

The initialization expression initializes the loop; it's executed once, as the loop begins.

When the termination expression evaluates to false, the loop terminates.

The increment expression is invoked after each iteration through the loop; it is perfectly acceptable for this expression to increment or decrement a value.

### primitive types

The eight primitive data types supported by the Java programming language are:

**byte:** The byte data type is an 8-bit signed two's complement integer. It has a minimum value of -128 and a maximum value of 127 (inclusive). The byte data type can be useful for saving memory in large arrays, where the memory savings actually matters. They can also be used in place of int where their limits help to clarify your code; the fact that a variable's range is limited can serve as a form of documentation.

**short:** The short data type is a 16-bit signed two's complement integer. It has a minimum value of -32,768 and a maximum value of 32,767 (inclusive). As with byte, the same guidelines apply: you can use a short to save memory in large arrays, in situations where the memory savings actually matters.

**int:** By default, the int data type is a 32-bit signed two's complement integer, which has a minimum value of -231 and a maximum value of 231-1. In Java SE 8 and later, you can use the int data type to represent an unsigned 32-bit integer, which has a minimum value of 0 and a maximum value of 232-1. Use the Integer class to use int data type as an unsigned integer. See the section The Number Classes for more information. Static methods like compareUnsigned, divideUnsigned etc have been added to the Integer class to support the arithmetic operations for unsigned integers.

**long:** The long data type is a 64-bit two's complement integer. The signed long has a minimum value of -263 and a maximum value of 263-1. In Java SE 8 and later, you can use the long data type to represent an unsigned 64-bit long, which has a minimum value of 0 and a maximum value of 264-1. Use this data type when you need a range of values wider than those provided by int. The Long class also contains methods like compareUnsigned, divideUnsigned etc to support arithmetic operations for unsigned long.

**float:** The float data type is a single-precision 32-bit IEEE 754 floating point. Its range of values is beyond the scope of this discussion, but is specified in the Floating-Point Types, Formats, and Values section of the Java Language Specification. As with the recommendations for byte and short, use a float (instead of double) if you need to save memory in large arrays of floating point numbers. This data type should never be used for precise values, such as currency. For that, you will need to use the java.math.BigDecimal class instead.

**double:** The double data type is a double-precision 64-bit IEEE 754 floating point. Its range of values is beyond the scope of this discussion, but is specified in the Floating-Point Types, Formats, and Values section of the Java Language Specification. For decimal values, this data type is generally the default choice. This data type should never be used for precise values, such as currency.

**boolean:** The boolean data type has only two possible values: true and false. Use this data type for simple flags that track true/false conditions.

**char:** The char data type is a single 16-bit Unicode character. It has a minimum value of '\u0000' (or 0) and a maximum value of '\uffff' (or 65,535 inclusive).

### reference types

Reference types are any instantiable class as well as String , Integer etc..
Primitive types store values but Reference type store handles to objects in heap space.


### classes / instances
Classes, fields, methods, constructors, and objects are the building blocks of object-based Java applications.
A class is a template for manufacturing objects. You declare a class by specifying the class keyword followed by a non-reserved identifier that names it. A pair of matching open and close brace characters ({ and }) follow and delimit the class's body. This syntax appears below:

class identifier
{
   // class body
}
By convention, the first letter of a class's name is uppercased and subsequent characters are lowercased (for example, Employee). If a name consists of multiple words, the first letter of each word is uppercased (such as SavingsAccount). This naming convention is called camelcasing.

The following example declares a class named Book:

class Book
{
   // class body
}

A class's body is populated with fields, methods, and constructors. Combining these language features into classes is known as encapsulation. This capability lets us program at a higher level of abstraction (classes and objects) rather than focusing separately on data structures and functionality.

### instance
An instance, in object-oriented programming (OOP), is a specific realization of any object. An object may be varied in a number of ways. Each realized variation of that object is an instance. The creation of a realized instance is called instantiation.
Each time a program runs, it is an instance of that program. In languages that create objects from classes, an object is an instantiation of a class. That is, it is a member of a given class that has specified values rather than variables. In a non-programming context, you could think of "dog" as a class and your particular dog as an instance of that class.



### instance methods

Instance method are methods which require an object of its class to be created before it can be called. To invoke a instance method, we have to create an Object of the class in within which it defined.
public void geek(String name)
{
 // code to be executed....
}
// Return type can be int, float String or user defined data type.
Memory allocation: These methods themselves are stored in Permanent Generation space of heap but the parameters (arguments passed to them) and their local variables and the value to be returned are allocated in stack. They can be called within the same class in which they reside or from the different classes defined either in the same package or other packages depend on the access type provided to the desired instance method.

Important Points:

Instance method(s) belong to the Object of the class not to the class i.e. they can be called after creating the Object of the class.
Every individual Object created from the class has its own copy of the instance method(s) of that class.
They can be overridden since they are resolved using dynamic binding at run time.
// Example to illustrate accessing the instance method .
import java.io.

class Foo{

    String name = "";

    // Instance method to be called within the same class or
    // from a another class defined in the same package
    // or in different package.
    public void geek(String name){

        this.name = name;
    }
}

class GFG {
    public static void main (String[] args) {

        // create an instance of the class.
        Foo ob = new Foo();

        // calling an instance method in the class 'Foo'.
        ob.geek("GeeksforGeeks");
        System.out.println(ob.name);
    }
}
Run on IDE
Output :
GeeksforGeeks

### static fields
Static variable’s value is same for all the object(or instances) of the class or in other words you can say that all instances(objects) of the same class share a single copy of static variables. lets understand this with an example:
class VariableDemo
{
   static int count=0;
   public void increment()
   {
       count++;
   }
   public static void main(String args[])
   {
       VariableDemo obj1=new VariableDemo();
       VariableDemo obj2=new VariableDemo();
       obj1.increment();
       obj2.increment();
       System.out.println("Obj1: count is="+obj1.count);
       System.out.println("Obj2: count is="+obj2.count);
   }
}
Output:
Obj1: count is=2
Obj2: count is=2
As you can see in the above example that both the objects of class, are sharing a same copy of static variable that’s why they displayed the same value of count.

Static variable initialization

Static variables are initialized when class is loaded.
Static variables in a class are initialized before any object of that class can be created.
Static variables in a class are initialized before any static method of the class runs.

### static methods
Static methods are the methods in Java that can be called without creating an object of class. They are referenced by the class name itself or reference to the Object of that class.
  public static void geek(String name)
  {
    // code to be executed....
  }

  // Must have static modifier in their declaration.
  // Return type can be int, float, String or user defined data type.

Memory Allocation: They are stored in Permanent Generation space of heap as they are associated to the class in which they reside not to the objects of that class. But their local variables and the passed argument(s) to them are stored in the stack. Since they belong to the class so they can be called to without creating the object of the class.

Important Points:

Static method(s) are associated to the class in which they reside i.e. they can be called even without creating an instance of the class i.e ClassName.methodName(args).
They are designed with aim to be shared among all Objects created from the same class.
Static methods can not be overridden. But can be overloaded since they are resolved using static binding by compiler at compile time.

// Example to illustrate Accessing the Static method(s) of the class.
import java.io.

class Geek{

    public static String geekName = "";

    public static void geek(String name){

        geekName = name;
    }
}

class GFG {
    public static void main (String[] args) {

        // Accessing the static method geek() and
        // field by class name itself.
        Geek.geek("vaibhav");
        System.out.println(Geek.geekName);

        // Accessing the static method geek() by using Object's reference.
        Geek obj = new Geek();
        obj.geek("mohit");
        System.out.println(obj.geekName);   
    }
}

Output:
vaibhav
mohit

Note: Static variables and their values (primitives or references) defined in the class are stored in PermGen space of memory.
What if static variable refers to an Object ?

static int i = 1;
static Object obj = new Object();
In first line,  the value 1 would be stored in PermGen section. In second line, the reference obj would be stored in PermGen section and the Object it refers to would be stored in heap section.

When to use static methods ??

When you have code that can be shared across all instances of the same class, put that portion of code into static method.
They are basically used to access static field(s) of the class.

### this

this is one of the java keywords and it helps in referring to the current object. When we use the dot(.) operator on this keyword, then we can access the member variables of the current object. this keyword can also be used to call one constructor from another constructors of the same class.

The parameter names passed to the constructors can have the same name as the member variables of that class.
For e.g., the constructor with parameters nameParam, marksParam and sectionParam
class Student
{
    String name;
    int marks;
    char section;

    Student(String nameParam, int marksParam, char sectionParam)
    {
        name = nameParam;
        marks = marksParam;
        section = sectionParam;
    }
}
can be rewritten as
Student(String name, int marks, char section)
{
    this.name = name;
    this.marks = marks;
    this.section = section;
}
If we have the parameter name same as the member variable, then the parameter hides the member variable. That is even if we assign value to the parameter, then the member variable is not affected. We can use the this keyword to distinguish the member variable name from the parameter name. When this.name is called it is the member variable, and when only name is called it is the parameter. Similarly, this.marks and this.section are member variables, where as marks and section are parameters.
The other use this keyword is to call the same class constructors. For e.g., the following code
// CONSTRUCTOR 1
Student(String nameParam, int marksParam, char sectionParam)
{
    name = nameParam;
    marks = marksParam;
    section = sectionParam;
}
// CONSTRUCTOR 2
Student(String nameParam, int marksParam)
{
    name = nameParam;
    marks = marksParam;
    section = 'A';
}
// CONSTRUCTOR 3
Student(String nameParam)
{
    name = nameParam;
    marks = 0;
    section = 'A';
}
can be rewritten as
// CONSTRUCTOR 1
Student(String name, int marks, char section)
{
    this.name = name;
    this.marks = marks;
    this.section = section;
}
// CONSTRUCTOR 2
Student(String name, int marks)
{
    this(name, marks, 'A');
}
// CONSTRUCTOR 3
Student(String name)
{
    this(name, 0, 'A');
}
Here we have used this keyword, both to distinguish (or identify) the member variables from the parameters and also to call the same class constructor.
In CONSTRUCTOR 1, we have initialized the member variables this.name, this.marks and this.section with parameters name, marks and section.
In CONSTRUCTOR 2, we are calling the CONSTRUCTOR 1 using this keyword.
Similarly, in CONSTRUCTOR 3 also, we are calling the CONSTRUCTOR 1 using this keyword.

### constructors
Constructors is a special mechanism using which, the member variables of an object can be initialized when the object is being created. Constructors also ensure that no object is created with missing or invalid data. e.g., Since every student should have a name, section and marks, we can restrict such that Student can only be created when all the required information is present and is valid.

class Student
{
    String name;
    int marks;
    char section;
}
For a class Student, we need to do the following to initialize the member variables of the student object.
Student st1 = new Student();
st1.name = "Srini"; // LINE A
st1.marks = 78;
st1.section = 'C';
There is a chance, we might accidentally not initialize the variable name, i.e. we forgot writing the code in LINE A, then the student will exist with out any name. Having student with out any name, is not a desirable situation. So we declare a constructor in the class Student as shown below. This constructor takes 3 parameters - nameParam, marksParam and sectionParam.
class Student
{
    String name;
    int marks;
    char section;

    // Constructor for student which takes 3 parameters.
    Student(String nameParam, int marksParam, char sectionParam)
    {
        name = nameParam;
        marks = marksParam;
        section = sectionParam;
    }
}
In the constructor, the passed values nameParam, marksParam and sectionParam are assigned to the member variables name, marks and section. Now the code for creating the Student object and initializing the variables is simplified as shown below.
Student st1 = new Student("Srini", 78, 'C');
For every class, when there is no constructor defined, then a default constructor with no parameters is automatically created by the compiler. That is the reason, we were able to call new Student(); even with out any constructor.
If a constructor with parameters is defined in the class, then the compiler will not add any default constructor, which means we can not create any object using the default constructor. We have to use the constructor with parameters, to create the object. If we also want to support the default constructor, then we should also explicitly declare that in the class.
We can have more than one constructor in a class. For e.g., for the Student class we can have one constructor which does not take parameters (default constructor), one constructor which takes only name, one constructor which takes both name and marks and one more constructor which takes name, marks and section. The objects can be created using any one of the four constructors.


### new operator
The new operator allocates memory dynamically for an object. Here is the general form to use new operator in Java:

class-var = new classname();
Here, class-var is the variable of the class type being created. The classname is the name of the class that is being instantiated.

The class name followed by the parentheses determines the constructor for the class. A constructor defines what occurs whenever an object of a class is created.

Constructors are an crucial part of all the classes and have many significant attributes.

Most real-world classes explicitly define its own constructors inside their class definition. However, if no explicit constructor is stated, then Java will automatically supply a default constructor. This is the case with Box. For now, we will use the default constructor. Shortly, you will see how to define your own constructors.

It is important to understand that the new operator/keyword allocates memory for an object during run time. The advantage of this approach is that your program can create as many/few objects as it needs during the execution of your program. However, since memory is finite, it is possible that the new will not be able to allocate memory for an object because insufficient memory exists. If this will happen, a run-time exception will occur.

### inheritance

Java allows for a hierarchy of classes.  Classes can be created from other classes by deriving the new class from the existing class.  In doing so, the new class becomes a subclass to the existing class, which in this case, is a superclass.  This new class can inherit all of the fields and methods from its superclass.  At the very top of the hierarchy is the Object class, which represents the highest possible superclass.

Here is a possible inheritance scenario:

```public class Car {

    <!-- the car class has three fields -->
    public int numberofSeats;
    public int engineDisplacement;
    public int topSpeed;

    <!-- a class declaration like TRUCK could look something like this: -->
    public class Truck extends Car {

        <!-- TRUCK subclass adds one field -->
        public int bedCapacity;
    }
}
```
The class `Truck` inherits all the fields and methods of `Car`, but also can add it's own custom fields and methods, specific to that class only.  Inheritance can be useful when you are creating multiple classes which share some fields or methods with an existing class.  See the section below about "overriding".

### super

By default, subclasses can override the fields or methods of their superclass.  However, it may be necessary to invoke the superclass' field or method instead.  This is done by invoking the `super` keyword.  For example, we may have a superclass of `bakedThing` and a subclass of `brownie`, with `brownie` having its own constructor.  To invoke the superclass' fields, the keyword super is invoked, as shown below:

```public brownie(int bakingTemp,
                  int cupsOfFlour,
                  int calories,
                  int numberOfEggs) {
                      super(cupsOfFlour, numberOfEggs); //this is where the super keyword is invoked
                                                        //two of the bakedThing's fields will now be used as part of this constructor
                  }
```

By using the `super` keyword, the inheritances between super and subclasses can be optimized for each use case.

### overloading

Overloading is a feature of classes that allows them to have multiple methods with the same name, as long as the argument list is unique for each.  The arguments might differ the number of parameters or the data types of the parameters.  Overloading is a convenience for programmers, since it improves readability by reducing the need to create a new name for each method.  An example of method overloading is provided below, along with notes to provide further explanation.

```class mathMachine{ //here is our class
                   //it holds an overloaded method called add
static int add(int alpha, int beta){return alpha+beta;} //the first version of the method accepts two integers
static int add(int alpha, int beta, int gamma){return alpha+beta+gamma;} //the second version of the method accepts three integers
}
System.out.println(Adder.add(10,10));  
System.out.println(Adder.add(10,10,10));
```

### overriding

Overriding is the process by which a subclass can implement it's own fields and methods, rather than being limited to those of its superclass.  In this way, the subclass functionality can be customized as needed, while still using the inheritances from its superclass.  Here is an example of overriding by a subclass `truck` over its superclass `car`:

```public class car {

    <!-- the car class has a constructor -->
    public void primaryUse() {
        System.out.println("moving people and goods from place to place");
    }

    <!-- the truck class could override the primaryUse method in order to do something more accurate: -->
    public class truck extends Car {

        <!-- truck subclass overrides the primaryUse method of car -->
        public void primaryUse() {
            System.out.println("hauling materials and trailers");    
    }
}
```

### packages

Packages are a convenience for developers that are used to group and categorize related classes and subpackages together.  There are some built in packages, but the developer can also create her own, in order to provide structure to her code.  Packages can be created automatically by an IDE or through manually adding the `package` keyword to a body of code.  For example:

```//the package keyword creates a package
package awesomePackage;
//the rest of the code would go here
public class example{
    public static void main(String args[]){
        . . .
    }
}
```
### interfaces

Interfaces are reference types, like classes.  Interfaces cannot be instantiated.  They can only be implemented by classes or extended by other interfaces.  Interfaces define which behaviors happen.  Defining an interface is similar to creating a new class.  Here is an example of a defined interfaces:

```public interface OperateCar {

   // constant declarations, if any

   // method signatures

   // An enum with values RIGHT, LEFT
   int turn(Direction direction,
            double radius,
            double startSpeed,
            double endSpeed);
   int changeLanes(Direction direction,
                   double startSpeed,
                   double endSpeed);
   int signalTurn(Direction direction,
                  boolean signalOn);
   int getRadarFront(double distanceToCar,
                     double speedOfCar);
   int getRadarRear(double distanceToCar,
                    double speedOfCar);
         ......
   // more method signatures
}
```

To use an interface, you must write a class that implements the interface.  This provides a method body for each of the methods declared in the interface.  Here is an example:

```public class OperateBMW760i implements OperateCar {

    // the OperateCar method signatures, with implementation --
    // for example:
    int signalTurn(Direction direction, boolean signalOn) {
       // code to turn BMW's LEFT turn indicator lights on
       // code to turn BMW's LEFT turn indicator lights off
       // code to turn BMW's RIGHT turn indicator lights on
       // code to turn BMW's RIGHT turn indicator lights off
    }

    // other members, as needed -- for example, helper classes not
    // visible to clients of the interface
}
```

from https://docs.oracle.com/javase/tutorial/java/IandI/createinterface.html.

### casting

The type of a given object be changed to a different type.  This is implemented by casting the variable.  However, an object cannot be cast to any type.  There are two types of casting--downcasting and upcasting.  Downcasting refers to the process of taking an object and casting it into a more specific object.  Conversely, upcasting is the process of changing the type of an object from ony type to a more generic type.

### instanceof operator

The instanceof operator is used to test whether the object is an instance of the specified type.  This operator compares the instance with the type.  It returns a true or false value.  Here is a simple example of instance operator where it tests the current class:

```class Simple1{  
 public static void main(String args[]){  
 Simple1 s=new Simple1();  
 System.out.println(s instanceof Simple1);//this will output to true  
 }  
}
```

### arrays

TBD Nick

### the uses of . [] {} ;

  TBD Nick

### access modifiers (public, private, protected)

TBD Nick

### exceptions

TBD Nick

### generics

TBD Nick

### abstract classes, abstract methods

TBD Nick

### enums

TBD Nick

### anonymous inner classes, lambdas

**Inner Classes**

As with instance methods and variables, an inner class is associated with an instance of its enclosing class and has direct access to that object's methods and fields. Also, because an inner class is associated with an instance, it cannot define any static members itself.

Objects that are instances of an inner class exist within an instance of the outer class. Consider the following classes:

```
class OuterClass {
    ...
    class InnerClass {
        ...
    }
}
```

An instance of InnerClass can exist only within an instance of OuterClass and has direct access to the methods and fields of its enclosing instance.

To instantiate an inner class, you must first instantiate the outer class. Then, create the inner object within the outer object with this syntax:

```
OuterClass.InnerClass innerObject = outerObject.new InnerClass();
```

There are two special kinds of inner classes: local classes and anonymous classes.

**Anonymous Inner Class**
Anonymous classes enable you to make your code more concise. They enable you to declare and instantiate a class at the same time. They are like local classes except that they do not have a name. Use them if you need to use a local class only once.

An inner class declared without a class name is known as an anonymous inner class. In the case of anonymous inner classes, we declare and instantiate them at the same time.

An anonymous class is an expression. The syntax of an anonymous class expression is like the invocation of a constructor, except that there is a class definition contained in a block of code.


The following program shows how to override the method of a class using anonymous inner class.

```

abstract class AnonymousInner {
   public abstract void mymethod();
}

public class Outer_class {

   public static void main(String args[]) {
      AnonymousInner inner = new AnonymousInner() {
         public void mymethod() {
            System.out.println("This is an example of anonymous inner class");
         }
      };
      inner.mymethod();
   }
}
```

**Lambda Expressions**

One issue with anonymous classes is that if the implementation of your anonymous class is very simple, such as an interface that contains only one method, then the syntax of anonymous classes may seem unwieldy and unclear. In these cases, you're usually trying to pass functionality as an argument to another method, such as what action should be taken when someone clicks a button. Lambda expressions enable you to do this, to treat functionality as method argument, or code as data.

The previous section, Anonymous Classes, shows you how to implement a base class without giving it a name. Although this is often more concise than a named class, for classes with only one method, even an anonymous class seems a bit excessive and cumbersome. Lambda expressions let you express instances of single-method classes more compactly.

**Syntax of Lambda Expressions**

A lambda expression consists of the following:

**A comma-separated list of formal parameters enclosed in parentheses. **

The CheckPerson.test method example below, contains one parameter, p, which represents an instance of the Person class.

Note: You can omit the data type of the parameters in a lambda expression. In addition, you can omit the parentheses if there is only one parameter.

p -> p.getGender() == Person.Sex.MALE
    && p.getAge() >= 18
    && p.getAge() <= 25

**The arrow token, ->**

**A body, which consists of a single expression or a statement block.** This example uses the following expression:

p.getGender() == Person.Sex.MALE
    && p.getAge() >= 18
    && p.getAge() <= 25

If you specify a single expression, then the Java runtime evaluates the expression and then returns its value. Alternatively, you can use a return statement:

p -> {
    return p.getGender() == Person.Sex.MALE
        && p.getAge() >= 18
        && p.getAge() <= 25;
}

A return statement is not an expression; in a lambda expression, you must enclose statements in braces ({}). However, you do not have to enclose a void method invocation in braces. For example, the following is a valid lambda expression:

email -> System.out.println(email)
Note that a lambda expression looks a lot like a method declaration; **you can consider lambda expressions as anonymous methods—methods without a name.**

### important classes of the standard library

**Object** - Object is the root of the class hierarchy.
**String** - The String class represents character strings.
**Integer** - The Integer class wraps a value of the primitive type int in an object. and provides the parseInt method useful for parsing strings to Integers.

**Runtime**  -Every Java application has a single instance of class Runtime that allows the application to interface with the environment in which the application is running.

**System** - contains several useful fields and methods including System.out.println

**Throwable**  - the superclass of all errors and exceptions in the Java language.

**Math** - contains methods for performing basic numeric operations such as the elementary exponential, logarithm, square root, and trigonometric functions.
