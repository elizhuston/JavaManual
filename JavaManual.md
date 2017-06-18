# Java manual
**Write a reference manual for the Java language. For each of the following topics, provide a description and (where applicable) a simple example:**

### values

TBD Elizabeth

### operations

TBD Elizabeth

### variables

TBD Elizabeth

### if else

TBD Elizabeth

### while

TBD Elizabeth

### for

TBD Elizabeth

### primitive types

TBD Elizabeth

### reference types

TBD Elizabeth

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
