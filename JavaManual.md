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

TBD Ravi

### instance

TBD Ravi

### instance methods

TBD Ravi

### static fields

TBD Ravi

### static methods

TBD Ravi

### this

TBD Ravi

### constructors

TBD Ravi

### new operator

TBD Ravi

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

TBD David

### casting

TBD David

### instanceof operator

TBD David

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

TBD Elizabeth

### important classes of the standard library

TBD Elizabeth
