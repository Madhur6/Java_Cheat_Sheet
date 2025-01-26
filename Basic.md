# Java (Madhur's Cheat Sheet)


src(.java) -------> byteCode(.class) ------------------jvm interprets the byte-code(.class)---------------------->(machine-code) 
           javac                                       & JIT(just-in-time compiles the interpreted bytye-code to --> )
                          
                          (Platform-Independence) [Any machine that has 'jvm' can execute the .class file]



## JShell: Assigns variable name if not provided by user.
   - Ex.: 6 ---> $6 = 6...


## public static void main(String[] args){}:
   - main method: [Entry-point of out program]
   - String[]: To accept the `cli` arguments.
   - args: Accessible as array of string. [can be hello/apple/args/etc]
   - Can also write: (String...args) [Allows method to accept 0 or more arguments.]




-----------------------------------------------------------------------------------------------------------------


- **Primitive-Data-Type**                                      | - **Non-Primitive-Data-Type**
                                                               |
  - Basic data-types [Pre-defined].                            |   - Reference-Type.
  - Are not objects.                                           |   - Are Objects.
  - Immutable.                                                 |   - Immutable/ Mutable.
  - Non-Nullable.                                              |   - Nullable.
  - Hold data directly in memory.                              |   - Stores reference to objects.
  - Stored in stack.                                           |   - Stored in Heap [Reference stored in stack].
  - Doesn't have methods.                                      |   - Have methods.
  - Ex. byte, short, int, long, float, double, char, boolean...|   - Ex. ArrayList[Mutable], Arrays[String & int],
                                                               |   -     Objects, String,**Wrapper-Classes**[Immutable].
                                                               |   -     Custom-Classes...



### **Wrapper-Classes**
- Higher memory-usage than primitive-types, [Stores meta-data & behaviours(methods)]...
- Immutable.
- Used to represent 'primitive-data-types' as 'Objects'.
- Allows user to use them where an object is required, such as in 'generic collections' like 'ArrayList'.
- Allows for 'null-representation'.

- Ex. Byte, Short, Integer, Long, Double, Float, Character, Boolean etc...


- **Auto-Boxing & Un-Boxing**:
  ```Java

  // Auto-Boxing
  - int x = 11;
  - Integer obj = x;


  // Un-Boxing
  - Integer obj = 12;
  - int y = obj;

  ```



-----------------------------------------------------------------------------------------------------------------



# Java Oops
- Style of programming, Where we organize our programs around data rather than logic & objects rather than actions.

**Class** - Blueprint that outlines the structure of our program.

**Object** - Programming representation of real-world entity.

- JVM creates objects, With the help of Class, Hence called 'blueprint'.

                                            
Class(Blueprint) -------------------------> JVM ----------------------> Objects
                  with the help of class    |          creates
                                            |
                                            | state & behaviour information
                                            |
                                            |
                                        Programmer(US)  


- Now Programmer needs to provide more information, JVM is concerned about just 2 information about any object:
   - **State**: Represents it's properties, The 'attributes' possibly distinguishing 1 object from the other.
   - **Behaviour**: Represents the actions Object might perform.

- *Note*: Behaviours are represented via non-static methods.





-----------------------------------------------------------------------------------------------------------------


## Pillars of Oops

- **Encapsulation**: Process of wrapping data & methods into a single unit.

- **Inheritence**: Process of inheriting properties of 'Parent(Super)-Class' by 'Child(Sub)-Class'.
  
- **Abstraction**: Process of hiding complex implementation details of an Object & Showing only the essential features of an object.

- **Polymorphism**: Ability of different classes to be treated as instance of same class.


-----------------------------------------------------------------------------------------------------------------


### Detailed Explanation for Pillars of Oops

- **Encapsulation**: Giving controlled access to very important aspect of application/code.
  - Pros
    - Enhances the Security.s
    - Access-Control.
    - Data-Protection.
    - Organized-Structure.
    - Easy-Update.

  - Ex. Secure digital bagpack


- **Inheritence**: Extending the properties from parent to child.
  - Pros
    - Reuseability,
    - Minimize Duplication,
    - No need to re-enter basic details,
    - Core information remains same,
    - Each feature can add it's own specialized information, While retaining basic details.

  - Cons
    - Super & Sub Class can be tightly-coupled.


  - Ex. GrandFather ---> Father ---> Child


  - Types:
  - 1). Single-Level, [Base-Class ---------> Derived-Class]
  - 2). Multi-Level,  [Base-Class ---------> Derived-Class ---------> Derived-Class]
  - 3). Hierarchial,  [Base-Class ---------> Derived-Class]
                        |
                        |
                        v
                      [Derived-Class]

  - 4). Hybrid,       [Combination of above types]
  - 5). Multiple,     [Doesn't Exists in Java as inheritence but rather as Interface]




- **Abstraction**: Hiding complex implementation details from users.
  - Pros
    - Simplicity,
    - Flexibility,
    - Enhanced UX,
    - Focus on Essentials,
    - Provides you with essential details & information/controls without exposing complex mechanics underneath.

  - Can-not be **instantiated**. (& may or may not include abstract-method).



  - Ex. Imagine a car-dashboard.




### Difference B/W Abstract-Class & Interface(Multiple-Inheritence)

- **Abstract-Class**                           | - **Interface**
  - Can have both abstract & concrete method.  |   - All methods are abstract or default.
                                               |
  - Can have instance variables.               |   - Only constants (public static final).
                                               |
  - Single Level inheritence.                  |   - Supports multiple inheritence.
                                               |
  - Access Modifiers.                          |   - All methods are public.
                                               |
  - Can have 'Constructors'.                   |   - Cannot have 'Constructors'.
                                               |
  - Methods can have body.                     |   - Methods can not have body untilunless they're declared as "default".
                                               |
  -                                            |   - @Override annotation is not mandatory but highly recommended.
                                               |
                                               |   - Lambda [ Way of interface ]


### Types of Interface

- **Marker**
  - Aka 'Empty-Interface'
  - Do not contain any methods or fields.
  
  - *Purpose*: They're used to provide 'meta-data' to classes, signaling to 'JVM' or other components that a class has a specific property or capabilities.

  - Ex. java.io.serializable: [Marks a class as serializable].
        java.lang.Cloneable:  [Indicates that a class supports 'Cloning'].



- **Functional**
  - Contain only one 'abstract-method'.
  - They can be used with 'Lambda-Expressions'.

  - *Purpose*: Design to support 'Functional-Programming' in java.

  - *Annotation*: `@FunctionalInterface` [Optional].

  - Ex. java.lang.Runnable: [Single method run()].
        java.util.function.Predicate:  [Single method test(T t)].




- **Normal**
  - Normal or Standard Interfaces with one or more abstract methods.

  - *Purpose*: Used to define general-contract for classes to *implement*.

  - Ex. java.util.List: [Contains multiple abstract-methods related to lists].
        java.util.Map:  [Defines methods for map-operation].



- **Other**

  - Taggin-Interface [class Example implements Taggable]
  
  - Nested-Interface: *Interface declared inside another interface or class.* [java.util.Map.entry]

  - Comparable[compareTo()] & Comparator Interface[compare]

  - Functional Programming Interfaces [java.util.function]

        





- **Polymorphism**: Single Entity Taking multiple forms.
  - Pros
    - Flexibility,
    - Single Entity taking multiple forms.

  - Ex. Animal ---> Dog / Elephant / Lion etc...

  - Types:
  - 1). Compile time polymorphism [We create different-different functions but with same names.]
  - 2). Run time polymorphism [Will learn in inheritence]



-----------------------------------------------------------------------------------------------------------------


### Polymorphism

- **Static or Compile** ----------------> Method-Overloading
        |
        |
        |
        V
      Operator-Overloading



- **Dynamic or Runtime** -----------------> Virtual/Over-riding method
  
  - *UpCasting*: We can only access the static-methods defined in super-class(Parent)
                 We can access the overridden-methods of child-class.


  - *DownCasting*: We can access the sub-class specific methods.
                   It must be done Explicitly.

  
  Parent p ================> new Child();
  *reference*              *object-type*


- **Static-Binding**                                  |  - **Dynamic-Binding**
                                                      |
  - Aka *early-binding* because method to be called   |    - The type of object is determined at runtime.
    is determined based on the reference-type not on  |
    the object-type.                                  |
                                                      |
  - Resolved at compile-time.                         |    - Resolved at run-time.
  - Applies to static, private & final methods.       |    - Applies to over-ridden methods
  - Based on reference-type.                          |    - Based on actual-types.
                                                      |
                                                      |
                                                      |
                                                      |

- **Note**: Static-Methods can't be annotated with @Overridden.



-----------------------------------------------------------------------------------------------------------------





**Constructors**:

```Java

class Student {
    String name;
    int age;

    // In Java, If we call the class to create an object without creating the constructor, Java will automatically creates it's own constructor.

    // Constructor
    Student(){}
    
    // Parameterized Constructor
    Student (String inputName, int inputAge){
        this.name = name;
        this.age = inputAge;
    }


    // Copy Constructor [But We do have to define another constructor, As we've define "Copy Constructor".]
    Student (Student s){
        this.name = s.name;
        this.age = s.age;
    }
}

```






-----------------------------------------------------------------------------------------------------------------


# Variables in Java

- Giving name to a 'memory-location' that holds some data.
- Used in order to store the data & retrieve the data.

- The value that is stored in the variable can change during the program's execution, Hence the therm "Variable".

   - Java is case-sensitive.
   - Start with a letter or _.
   - CamelCase Convention.
   - Avoid reserved words. (new, int etc...)

   - "VAR" keyword: var number = 42 {JAVAC infers that "number" is an 'int'}.
   - If type of var is declared, It can't change later. (String ---> int).


- **Static-Variables**:   Variables belongs to class itself & not to any instance.

- **Instance-Variables**: Variables declared inside class but outside any methods.

- **Final-Variables**:    Variables can't be modified once it is initialized.




-----------------------------------------------------------------------------------------------------------------

# Operations

## Increment & Decrement Operators

```Java

int x = 5, y = 5;

int res = x++ + ++x;  // OP: x++ uses 5, then increments to 6, Then ++x increments to 7 & uses 7.
int res = ++y + y++;  // OP: ++y increments to 6 & uses 6, Then y++ uses 6, then increments to 7.


```


-----------------------------------------------------------------------------------------------------------------


### Packages in Java


- Contains related code (Built-In & User-Defined Packages).
- Ex. Java.util etc...

- Groups of similar types of classes, interfaces or sub-packages.

- Steps to create a package:
  - create a folder (ur_pkg_name)
  - create a file (ur_pkg_name/file.java)
  - Now compile the code as > `javac ur_pkg_name/file.java` > `java ur_pkg_name.file`
  - Outside of "package", U can't use Default class, (Use public class main)
  - if In current-working directory, No problems.
  - else, use classPath (an env. variable) ---> Temporary (Set ClassPath == `package-path;main-file path`).
                                        OR ---> Permanent (Set env. variable)



-----------------------------------------------------------------------------------------------------------------

## Access Modifiers in Java

- Types:

modifiers   - Same-Class      | - Same Package      | - Same Pkg          | - Diff. Pkg       | - Diff. Pkg 
                              |   & Sub-class       |   & non-subclass    |  & Sub-Class      | & non-sub-class

private         yes                  no                    no                   no                   no

default         yes                  yes                   yes                  no                   no

protected       yes                  yes                   yes                  yes                  no

public          yes                  yes                   yes                  yes                  yes



- **Note**: The access-modifiers for an overriding method can allow more but not les access to the over-ridden-method.

  - Ex. a protected instance method in super-class can be made public, But not private in sub-class.

  - final / static / private methods can-not be overridden.





-----------------------------------------------------------------------------------------------------------------


## Handeling Exceptions in Java


java.lang --------------> object --------------------> throwable --------------------> Errors
                                                          |
                                                          |
                                                          |
                                                          V
                                                        Exceptions

### Types

- **Checked-Exception**: [Compile-Time] Classes that directly inherit throwable class.

    - IOException [FileNotFoundException, EofException]
    - SQLException
    - NetWork & Class Exceptions

- **Unchecked-Exception**: [Run-Time] Ex. Arithmetic, IndexOutOfBounds, ClassCast & NullPointer Exception.

    - [NullPointerException, IndexOutOfBounds Exception]
    - [ClassCastException, Array, NullPointer, NumberFormatting, IllegalArgument] 

- **Errors**: [OutOfMemoryError, StackOverFlowError]



### Try-Catch-Finally

- **Try**: Allows you to define a block of code to be tested for errors while it's being executed.
- **Catch**: Allows you to define a block of code to be executed if an error occurs in the 'try' block.
- **Finally**: Let's you execute code, After `try...catch` block, Regardless the result.


### Throw / Throws

- **Throw**: Allows you to create a custom-errors, & is used together with an exception type. There're many exception types available in java.

    - Arithmetic Exception,
    - FileNoteFoundException,
    - ArrayIndexOutOfBoundsException,
    - SecurityException,

- **Throws**: Used to define which type of exception can be occured, It is written besides the methods.





-----------------------------------------------------------------------------------------------------------------


**Collection-type**            **Interface**            **Common-Implementation**            **Key-Feature**

*List*                         *List*                   *ArrayList*, *LinkedList*           *Ordered*, *Allows-Duplicate*

*Set*                          *Set*                    *HashSet*, *Tree-Set*          *Un-Ordered(hash)*, *No-Duplicate*

*Map*                          *Map*                    *HashMap*, *Tree-Map*             *Key-Value-Pair*, *Unique-Keys*

*Queue*                        *Queue*                  *LinkedList*, *PQ*                  *Fifo processing*

*Dequeue*                      *Dequeue*                *ArrayDequeue*                      *Double-Ending-Queue*

*Stack*                        *Stack*                  *Stack*                             *Lifo processing*


-----------------------------------------------------------------------------------------------------------------

