[JVM](#jvm)

[Java Basics](#basics)

[Java OOP](#oop)

[Java Servlet](#servlet)




## 📖 Java JVM <div id="jvm"></div>

### Q. Differences between JDK, JRE and JVM.
<img src="https://beginnersbook.com/wp-content/uploads/2013/05/jdk.jpg" height="300" width="600" />

JDK: Java Development Kit is the core component of Java Environment and provides all the tools, executables and binaries required to compile, debug and execute a Java Program.

JRE: Java Runtime Environment provides a platform to execute java programs. JRE consists of JVM and java binaries and other classes to execute any program successfully.

JVM: JVM is responsible for converting Byte code to the machine specific code. JVM is also platform dependent and provides core java functions like memory management, garbage collection, security etc. JVM is customizable and we can use java options to customize it, for example allocating minimum and maximum memory to JVM. JVM is called virtual because it provides an interface that does not depend on the underlying operating system and machine hardware.

### Q. What is JVM and is it platform independent?
Java Virtual Machine (JVM) is a specification that provides runtime environment in which java bytecode(.class files) can be executed. The JVM is the platform. The JVM acts as a "virtual" machine or processor. Java's platform independence consists mostly of its Java Virtual Machine (JVM). JVM makes this possible because it is aware of the specific instruction lengths and other particularities of the platform (Operating System).

The JVM is not platform independent. Java Virtual Machine (JVM) provides the environment to execute the java file(. Class file). So at the end it's depends on kernel and kernel is differ from OS (Operating System) to OS. The JVM is used to both translate the bytecode into the machine language for a particular computer and actually execute the corresponding machine-language instructions as well.


### Q. Explain the JVM architecture.
<img src="https://lh3.googleusercontent.com/mI9DsbikQHpvY6nkdOxfdEyFzCHbiG7oqDwRCW7ty4golJPXp2RClTaxqMlQuDqHdo09IvQynIJlz4fC7P2zC0HwcfXTQLVOmzDT_foGKSe53CID8tn_ZulFjPXtX_k1OGiZ_8hw" height="400" width="600" />

### Q. What is Class Loader?
[Answer Reference](https://www.tutorialspoint.com/java_virtual_machine/java_virtual_machine_class_loader.htm)


### Q. What are the types of class loaders?

The **BootStrap class loader** is on the top of the class loader hierarchy. It loads the standard JDK classes in the JRE’s lib directory.

The **Extension class loader** is in the middle of the class loader hierarchy and is the immediate child of the bootstrap class loader and loads the classes in the JRE’s lib\ext directory.

The **Application class loader** is at the bottom of the class loader hierarchy and is the immediate child of the application class loader. It loads the jars and classes specified by the CLASSPATH ENV variable.

### Q. What are the phrases of class loading process?
### Q. What are the steps in linking process?

### Q. Explain JVM Runtime Data Areas.

**Method Area:**

**Java Heap Space:** Java Heap space is used by java runtime to allocate memory to Objects and JRE classes. Whenever we create any object, it’s always created in the Heap space. Garbage Collection runs on the heap memory to free the memory used by objects that doesn’t have any reference. Any object created in the heap space has global access and can be referenced from anywhere of the application.

**Java Stack Memory:** Stack in java is a section of memory which contains methods, local variables and reference variables. Local variables are created in the stack. Stack memory is always referenced in LIFO (Last-In-First-Out) order. Whenever a method is invoked, a new block is created in the stack memory for the method to hold local primitive values and reference to other objects in the method.
As soon as method ends, the block becomes unused and become available for next method. Stack memory size is very less compared to Heap memory.

**PC Register:**

**Native Internal Threads:**


### Q. What is JIT compiler in java?
The Just-In-Time (JIT) compiler is a component of the runtime environment that improves the performance of Java applications by compiling bytecodes to native machine code at run time.

Java programs consists of classes, which contain platform-neutral bytecodes that can be interpreted by a JVM on many different computer architectures. At run time, the JVM loads the class files, determines the semantics of each individual bytecode, and performs the appropriate computation. The additional processor and memory usage during interpretation means that a Java application performs more slowly than a native application. The JIT compiler helps improve the performance of Java programs by compiling bytecodes into native machine code at run time. The JIT compiler is enabled by default. When a method has been compiled, the JVM calls the compiled code of that method directly instead of interpreting it.


### Q. A Definition of Java Garbage Collection
[Answer Reference](https://stackify.com/what-is-java-garbage-collection/#:~:text=Java%20garbage%20collection%20is%20the,Machine%2C%20or%20JVM%20for%20short.&text=The%20garbage%20collector%20finds%20these,them%20to%20free%20up%20memory.)

[How Does GC Work in Java? (Detailed Explanation)](https://medium.com/@alitech_2017/how-does-garbage-collection-work-in-java-cf4e31343e43)

Java garbage collection is the process by which Java programs perform automatic memory management. Java programs compile to bytecode that can be run on a Java Virtual Machine, or JVM for short. When Java programs run on the JVM, objects are created on the heap, which is a portion of memory dedicated to the program. Eventually, some objects will no longer be needed. The garbage collector finds these unused objects and deletes them to free up memory.


### Q. How Java Garbage Collection Works?


## 📖 Java Basics <div id="basics"></div>

### Q. What is Java?
Java is a general-purpose **programming language** that is class-based, object-oriented, and designed to have as few implementation dependencies as possible. It is intended to let application developers write once, run anywhere (WORA), meaning that compiled Java code can run on all platforms that support Java without the need for recompilation. Java applications are typically compiled to bytecode that can run on any Java virtual machine (JVM) regardless of the underlying computer architecture.

Java can also be known as the **platform** as it provides its own JRE and API.

### Q. Explain public static void main(String args[]) in Java?
main() in Java is the **entry point** for any Java program. It is always written as
```Java
public static void main(String[] args).
```

**public**: Public is an access modifier, which is used to specify who can access this method. Public means that this Method will be accessible by any Class.

**static**: It is a keyword in java which identifies it is class-based. main() is made static in Java so that it can be accessed without creating the instance of a Class. In case, main is not made static then the compiler will throw an error as main() is called by the JVM before any objects are made and only static methods can be directly invoked via the class. 

**void**: It is the return type of the method. Void defines the method which will not return any value.

**main**: It is the name of the method which is searched by JVM as a starting point for an application with a particular signature only. It is the method where the main execution occurs.

**String args[]**: It is the parameter passed to the main method.

### Q. Why Java is platform independent?
Once compiled Java can be executed on any platform (OS). The Java compiler converts the source code to bytecode, which is Intermidiate Language. Bytecode can be executed on any platform (OS) using JVM( Java Virtual Machine).

### Q. Differences between Java and C++?
<img src="https://2.bp.blogspot.com/-TnfjbMv6UPs/WpHG2TxbXQI/AAAAAAAAAJI/eoFnFKPtoDcQSPZkUPhw8PcryJqpRxGggCLcBGAs/s1600/C%252B%252BJAVA.PNG" height="330" width="950" />

### Q. Why Java is not 100% Object-oriented?
Java is not 100% Object-oriented because it makes use of **eight primitive data types** such as boolean, byte, char, short, int, float, double, long which are not objects.

### Q. Why pointers are not used in Java?
Java doesn’t use pointers because they are **unsafe** and increases the **complexity** of the program. Since, Java is known for its simplicity of code, adding the concept of pointers will be contradicting. Moreover, since JVM is responsible for implicit memory allocation, thus in order to avoid direct access to memory by the user,  pointers are discouraged in Java.

### Q. What are Java Datatypes?
<img src="https://www.softwaretestingmaterial.com/wp-content/uploads/2018/03/Data-Types.png?ezimgfmt=ng:webp/ngcb2" height="330" width="600" />

### Q. Explain 8 Java primitives?
<img src="https://facingissuesonitcom.files.wordpress.com/2019/06/java-primitive-type-keywords-.png?w=1000" height="620" width="800" />

### Q. What are wrapper classes?
Wrapper classes convert the Java primitives into the reference types (objects). Every primitive data type has a class dedicated to it. Refer to the below image which displays different primitive type, wrapper class and constructor argument.

<img src="https://www.techguruspeaks.com/wp-content/uploads/2019/12/a03.png" height="300" width="450" />

### Q. What are Access Modifiers in Java?
<img src="https://lh3.googleusercontent.com/proxy/7RTF2MD2ZQ9KX-oREc4wHeBFkSU5AGtnPPzgFTbmnNsoefpfswgM96neyP774yLK5WKXvFio5Fy_z53wzfZosU6p1m50Ng6FCBcOE5Tn597ekam8phnN" height="150" width="350" />

### Q. What are constructors in Java?
In Java, constructor refers to a block of code which is used to initialize an object. It must have the same name as that of the class. Also, it has no return type and it is automatically called when an object is created.

There are two types of constructors:

1) **Default Constructor**: In Java, a default constructor is the one which does not take any inputs. In other words, default constructors are the no argument constructors which will be created by default in case you no other constructor is defined by the user. Its main purpose is to initialize the instance variables with the default values.

2) **Parameterized Constructor**: The parameterized constructor in Java, is the constructor which is capable of initializing the instance variables with the provided values. In other words, the constructors which take the arguments are called parameterized constructors.

### Q. In what scenario do we use constructor private?


### Q. What is the difference between == and equals() in Java?
“==” or equality operator in Java is a binary operator provided by Java programming language and **used to compare primitives** and objects.

Equals() method is defined in Object class in Java and **used for checking equality of two objects** defined by business logic. ***public boolean equals(Object o)*** is the method provided by the Object class. The default implementation uses == operator to compare two objects. For example: method can be overridden like String class. equals() method is used to compare the values of two objects.


### Q. 

## 📖 Java OOP <div id="oop"></div>

### Q. What is Object Oriented Programming?
Object-oriented programming (OOP) is a programming paradigm based on the concept of "objects", which can contain data and code: data in the form of fields (often known as attributes or properties), and code, in the form of procedures (often known as methods).

A feature of objects is that an object's own procedures can access and often modify the data fields of itself. In OOP, computer programs are designed by making them out of objects that interact with one another. OOP languages are diverse, but the most popular ones are class-based, meaning that objects are instances of classes, which also determine their types.

This approach is ideal for the programs large and complex codes and needs to be actively updated or maintained.

### Q. What are the main concepts of OOPs in Java?
1) **Abstraction**: Abstraction is the methodology of hiding the implementation details from the user and only providing the functionality to the users.
2) **Encapsulation**: Encapsulation in Java is a mechanism of wrapping up the data and code together as a single unit.
3) **Inheritance**: Inheritance is a process where one class acquires the properties of another.
4) **Polymorphism**: Polymorphism is the ability of a variable, function or object to take multiple forms.

### Q. What are member variables?
The instance variables and class variables are generally called member variables.

### Q. Class variable vs. Instance variable vs. Local variable?
**Class variables(Static Fields)** − Class variables also known as static variables are declared with the static keyword in a class, but outside a method, constructor or a block. There would only be one copy of each class variable per class, regardless of how many objects are created from it.

**Instance variables(Non-Static Fields)** − Instance variables are declared in a class, but outside a method. When space is allocated for an object in the heap, a slot for each instance variable value is created. Instance variables hold values that must be referenced by more than one method, constructor or block, or essential parts of an object's state that must be present throughout the class.

**Local variables** − Local variables are declared in methods, constructors, or blocks. Local variables are created when the method, constructor or block is entered and the variable will be destroyed once it exits the method, constructor, or block.



### Q. 

### Q. 

### Q. 

### Q. 



## 📖 Java Servlet <div id="servlet"></div>

### Q. What is RedirectAttributes?
**RedirectAttributes** is a sub-interface of Model. It is a preferred way to pass attributes to redirect target. Using Model attributes for passing redirection data is not always desirable as it may conflict some attributes used for rendering purposes.

### Q. addAttribute() vs addFlashAttribute() ?
**addFlashAttribute()** actually stores the attributes in a flashmap (which is internally maintained in the users session and removed once the next redirected request gets fulfilled)

**addAttribute()** essentially constructs request parameters out of your attributes and redirects to the desired page with the request parameters.

The advantage of addFlashAttribute() will be that you can store pretty much any object in your flash attribute (as it is not serialized into request params at all, but maintained as an object), whereas with addAttribute() since the object that you add gets transformed to a normal request param, you are pretty limited to the object types like String or primitives.

### Q. 