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

<p> ref: https://www.tutorialspoint.com/java_virtual_machine/java_virtual_machine_class_loader.htm
### Q: What is Class Loader?

### Q: What are the types of class loaders?
The <strong>BootStrap class loader</strong> is on the top of the class loader hierarchy. It loads the standard JDK classes in the JRE’s lib directory.

The <strong>Extension class loader</strong> is in the middle of the class loader hierarchy and is the immediate child of the bootstrap class loader and loads the classes in the JRE’s lib\ext directory.

The <strong>Application class loader</strong> is at the bottom of the class loader hierarchy and is the immediate child of the application class loader. It loads the jars and classes specified by the CLASSPATH ENV variable.

### Q: What are the phrases of class loading process?
### Q: What are the steps in linking process?

### Q: Explain JVM Runtime Data Areas.

<p><strong>Method Area:</strong>

<p><strong>Java Heap Space:</strong> Java Heap space is used by java runtime to allocate memory to Objects and JRE classes. Whenever we create any object, it’s always created in the Heap space.
Garbage Collection runs on the heap memory to free the memory used by objects that doesn’t have any reference. Any object created in the heap space has global access and can be referenced from anywhere of the application.

<p><strong>Java Stack Memory:</strong> Stack in java is a section of memory which contains methods, local variables and reference variables. Local variables are created in the stack.
Stack memory is always referenced in LIFO (Last-In-First-Out) order. Whenever a method is invoked, a new block is created in the stack memory for the method to hold local primitive values and reference to other objects in the method.
As soon as method ends, the block becomes unused and become available for next method. Stack memory size is very less compared to Heap memory.

<p><strong>PC Register:</strong>

<p><strong>Native Internal Threads:</strong>
