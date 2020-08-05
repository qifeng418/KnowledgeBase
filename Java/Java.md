## Java JVM

### Q: Differences between JDK, JRE and JVM.
<img src="https://beginnersbook.com/wp-content/uploads/2013/05/jdk.jpg" height="400" width="600" />

JDK: Java Development Kit is the core component of Java Environment and provides all the tools, executables and binaries required to compile, debug and execute a Java Program.

JRE: Java Runtime Environment provides a platform to execute java programs. JRE consists of JVM and java binaries and other classes to execute any program successfully.

JVM: JVM is responsible for converting Byte code to the machine specific code. JVM is also platform dependent and provides core java functions like memory management, garbage collection, security etc. JVM is customizable and we can use java options to customize it, for example allocating minimum and maximum memory to JVM. JVM is called virtual because it provides an interface that does not depend on the underlying operating system and machine hardware.

### Q: What is JVM and is it platform independent?
Java Virtual Machine (JVM) is a specification that provides runtime environment in which java bytecode(.class files) can be executed. The JVM is the platform. The JVM acts as a "virtual" machine or processor. Java's platform independence consists mostly of its Java Virtual Machine (JVM). JVM makes this possible because it is aware of the specific instruction lengths and other particularities of the platform (Operating System).

The JVM is not platform independent. Java Virtual Machine (JVM) provides the environment to execute the java file(. Class file). So at the end it's depends on kernel and kernel is differ from OS (Operating System) to OS. The JVM is used to both translate the bytecode into the machine language for a particular computer and actually execute the corresponding machine-language instructions as well.


### Q: Explain the JVM architecture.
<img src="https://lh3.googleusercontent.com/mI9DsbikQHpvY6nkdOxfdEyFzCHbiG7oqDwRCW7ty4golJPXp2RClTaxqMlQuDqHdo09IvQynIJlz4fC7P2zC0HwcfXTQLVOmzDT_foGKSe53CID8tn_ZulFjPXtX_k1OGiZ_8hw" height="400" width="600" />

### Q: What is Class Loader?
[Answer Reference](https://www.tutorialspoint.com/java_virtual_machine/java_virtual_machine_class_loader.htm)


### Q: What are the types of class loaders?

The **BootStrap class loader** is on the top of the class loader hierarchy. It loads the standard JDK classes in the JRE’s lib directory.

The **Extension class loader** is in the middle of the class loader hierarchy and is the immediate child of the bootstrap class loader and loads the classes in the JRE’s lib\ext directory.

The **Application class loader** is at the bottom of the class loader hierarchy and is the immediate child of the application class loader. It loads the jars and classes specified by the CLASSPATH ENV variable.

### Q: What are the phrases of class loading process?
### Q: What are the steps in linking process?

### Q: Explain JVM Runtime Data Areas.

**Method Area:**

**Java Heap Space:** Java Heap space is used by java runtime to allocate memory to Objects and JRE classes. Whenever we create any object, it’s always created in the Heap space. Garbage Collection runs on the heap memory to free the memory used by objects that doesn’t have any reference. Any object created in the heap space has global access and can be referenced from anywhere of the application.

**Java Stack Memory:** Stack in java is a section of memory which contains methods, local variables and reference variables. Local variables are created in the stack. Stack memory is always referenced in LIFO (Last-In-First-Out) order. Whenever a method is invoked, a new block is created in the stack memory for the method to hold local primitive values and reference to other objects in the method.
As soon as method ends, the block becomes unused and become available for next method. Stack memory size is very less compared to Heap memory.

**PC Register:**

**Native Internal Threads:**


### Q: What is JIT compiler in java?
The Just-In-Time (JIT) compiler is a component of the runtime environment that improves the performance of Java applications by compiling bytecodes to native machine code at run time.

Java programs consists of classes, which contain platform-neutral bytecodes that can be interpreted by a JVM on many different computer architectures. At run time, the JVM loads the class files, determines the semantics of each individual bytecode, and performs the appropriate computation. The additional processor and memory usage during interpretation means that a Java application performs more slowly than a native application. The JIT compiler helps improve the performance of Java programs by compiling bytecodes into native machine code at run time. The JIT compiler is enabled by default. When a method has been compiled, the JVM calls the compiled code of that method directly instead of interpreting it.


### Q: A Definition of Java Garbage Collection
[Answer Reference](https://stackify.com/what-is-java-garbage-collection/#:~:text=Java%20garbage%20collection%20is%20the,Machine%2C%20or%20JVM%20for%20short.&text=The%20garbage%20collector%20finds%20these,them%20to%20free%20up%20memory.)

[How Does GC Work in Java? (Detailed Explanation)](https://medium.com/@alitech_2017/how-does-garbage-collection-work-in-java-cf4e31343e43)

Java garbage collection is the process by which Java programs perform automatic memory management. Java programs compile to bytecode that can be run on a Java Virtual Machine, or JVM for short. When Java programs run on the JVM, objects are created on the heap, which is a portion of memory dedicated to the program. Eventually, some objects will no longer be needed. The garbage collector finds these unused objects and deletes them to free up memory.


### Q: How Java Garbage Collection Works?



