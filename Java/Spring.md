[Spring](#spring)

[Spring IoC](#ioc)

[Spring AOP](#aop)

[Spring MVC](#mvc)


## 📖 Spring <div id="spring"></div>

### Q: What is Spring?

Spring is an open source development framework for enterprise Java. The core features of the Spring Framework can be used in developing any Java application, but there are extensions for building web applications on top of the Java EE platform. Spring framework targets to make J2EE development easier to use and promote good programming practice by enabling a POJO-based programming model.

### Q: What are benefits of using spring?

**Lightweight** − Spring is lightweight when it comes to size and transparency. The basic version of spring framework is around 2MB.

**Inversion of control (IOC)** − Loose coupling is achieved in spring using the technique Inversion of Control. The objects give their dependencies instead of creating or looking for dependent objects.

**Aspect oriented (AOP)** − Spring supports Aspect oriented programming and enables cohesive development by separating application business logic from system services.

**Container** − Spring contains and manages the life cycle and configuration of application objects.

**MVC Framework** − Spring's web framework is a well-designed web MVC framework, which provides a great alternative to web frameworks such as Struts or other over engineered or less popular web frameworks.

**Transaction Management** − Spring provides a consistent transaction management interface that can scale down to a local transaction (using a single database, for example) and scale up to global transactions (using JTA, for example).

**Exception Handling** − Spring provides a convenient API to translate technology-specific exceptions (thrown by JDBC, Hibernate, or JDO, for example) into consistent, unchecked exceptions.

### Q: What are the different modules in Spring framework?

<img src="https://docs.spring.io/spring/docs/4.0.x/spring-framework-reference/html/images/spring-overview.png" height="450" width="550" />

### Q: What is Spring configuration file?
Spring configuration file is an **XML file**. This file contains the classes information and describes how these classes are configured and introduced to each other.

## 📖 Spring IoC Container <div id="ioc"></div>

### Q: What is Spring IOC Container?

<img src="https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/05/ioc-2.png" height="200" width="300" />

At the core of the Spring Framework, lies the Spring container. The container creates the object, wires them together, configures them and manages their complete life cycle. The Spring container makes use of Dependency Injection to manage the components that make up an application. The container receives instructions for which objects to instantiate, configure, and assemble by reading the configuration metadata provided. This metadata can be provided either by XML, Java annotations or Java code.

### Q: What is Dependency Injection?
Dependency Injection (DI) is a design pattern used to implement IoC. It allows the creation of dependent objects outside of a class and provides those objects to a class through different ways. Using DI, we move the creation and binding of the dependent objects outside of the class that depends on them.

It bastically means that you do not create your objects but describe how they should be created. You don't directly connect your components and services together in code but describe which services are needed by which components in a configuration file. A container (the IOC container) is then responsible for hooking it all up.

### Q: What are the different types of IoC (dependency injection)?
**Constructor-based dependency injection** − Constructor-based DI is accomplished when the container invokes a class constructor with a number of arguments, each representing a dependency on other class.

**Setter-based dependency injection** − Setter-based DI is accomplished by the container calling setter methods on your beans after invoking a no-argument constructor or no-argument static factory method to instantiate your bean.

### Q: Spring Setter vs. Constructor Injection
1) The fundamental difference between setter and constructor injection, as their name implies, is How dependency is injected.  Setter injection in Spring uses setter methods like setDependency() to inject dependency on any bean managed by Spring's IOC container. On the other hand, constructor injection uses the constructor to inject dependency on any Spring-managed bean.

2) Because of using the setter method, setter Injection in more readable than constructor injection in Spring configuration file usually applicationContext.xml . Since the setter method has name like setReporotService() by reading Spring XML config file you know which dependency you are setting. While in constructor injection, since it uses an index to inject the dependency, it's not as readable as setter injection and you need to refer either Java documentation or code to find which index corresponds to which property.

3) Another difference between setter vs constructor injection in Spring and one of the drawbacks of setter injection is that it does not ensures dependency Injection. You can not guarantee that certain dependency is injected or not, which means you may have an object with incomplete dependency. On the other hand, constructor Injection does not allow you to construct an object until your dependencies are ready.

4) One more drawback of setter Injection is Security. By using setter injection, you can override certain dependency which is not possible with constructor injection because every time you call the constructor, a new object is gets created.

5) One of our reader Murali Mohan Reddy pointed out one more difference between Setter and Constructor Injection in Spring, where later can help if there is a circular dependency between two object A and B.



## 📖 Spring AOP <div id="aop"></div>

### Q: Describe Spring AOP?
[Answer Reference](https://howtodoinjava.com/interview-questions/top-spring-aop-interview-questions-with-answers/)

compliments OOPs in the sense that it also provides modularity. In OOPs, key unit is Objects, but in AOP key unit is aspects or concerns (simply assume stand-alone modules in your application). Some aspects have centralized code but other aspects may be scattered or tangled e.g. logging or transactions. These scattered aspects are called cross-cutting concern. A cross-cutting concern is a concern that can affect the whole application and should be centralized in one location in code as possible, such as transaction management, authentication, logging, security etc.

AOP provides the way to dynamically add the cross-cutting concern before, after or around the actual logic using simple pluggable configurations. It makes easy to maintain code in present and future as well. You can add/remove concerns without recompiling complete sourcecode simply by changing configuration files (if you are applying aspects suing XML configuration).

Spring AOP can be used by majorly 2 ways given below. But the widely used approach is Spring AspectJ Annotation Style.

1. By AspectJ annotation-style
2. By Spring XML configuration-style

### Q: What is the difference between concern and cross-cutting concern in Spring AOP?
**Concern** is behavior which we want to have in a module of an application. Concern may be defined as a functionality we want to implement to solve a specific business problem. E.g. in any eCommerce application different concerns (or modules) may be inventory management, shipping management, user management etc.

**Cross-cutting concern** is a concern which is applicable throughout the application (or more than one module). e.g. logging , security and data transfer are the concerns which are needed in almost every module of an application, hence they are termed as cross-cutting concerns.

### Q: What are the available AOP implementations?
Main java based AOP implementations are listed below

1. AspectJ
2. Spring AOP
3. JBoss AOP

### Q: What are the different advice types in spring?
An advice is the implementation of cross-cutting concern which you are interested in applying on other modules of your application. Advices are of mainly 5 types :

1. **Before advice** : Advice that executes before a join point, but which does not have the ability to prevent execution flow proceeding to the join point (unless it throws an exception). To use this advice, use **@Before** annotation.

2. **After returning advice** : Advice to be executed after a join point completes normally. For example, if a method returns without throwing an exception. To use this advice, use **@AfterReturning** annotation.

3.  **After throwing advice** : Advice to be executed if a method exits by throwing an exception. To use this advice, use **@AfterThrowing** annotation.

4. **After advice** : Advice to be executed regardless of the means by which a join point exits (normal or exceptional return). To use this advice, use **@After** annotation.

5. **Around advice** : Advice that surrounds a join point such as a method invocation. This is the most powerful kind of advice. To use this advice, use **@Around** annotation.

### Q: What is Spring AOP Proxy?
A proxy is a well-used design pattern. To put it simply, a proxy is an object that looks like another object, but adds special functionality behind the scene.

Spring AOP is proxy-based. AOP proxy is an object created by the AOP framework in order to implement the aspect contracts in runtime.

Spring AOP defaults to using standard JDK dynamic proxies for AOP proxies. This enables any interface (or set of interfaces) to be proxied. Spring AOP can also use CGLIB proxies. This is necessary to proxy classes, rather than interfaces.

**CGLIB** is used by default if a business object does not implement an interface.

### Q: What is Introduction?
Introductions enable an aspect to declare that advised objects implement any additional interface(s) which they don’t have in real, and to provide an implementation of that interface on behalf of those objects.

An introduction is made using the **@DeclareParents** annotation.

### Q: What is Joint point and Point cut?
**Join point** is a point of execution of the program, such as the execution of a method or the handling of an exception. In Spring AOP, **a join point always represents a method execution**. For example, all the methods defined inside your EmployeeManager interface cab be considered joint points if you apply any cross-cutting concern of them.

**Pointcut is a predicate or expression that matches join points.** Advice is associated with a pointcut expression and runs at any join point matched by the pointcut (for example, expression “execution(* EmployeeManager.getEmployeeById(..))” to match getEmployeeById() the method in EmployeeManager interface). The concept of join points as matched by pointcut expressions is central to AOP, and Spring uses the AspectJ pointcut expression language by default.


### Q: What is Weaving?
The Spring AOP framework supports only limited types of AspectJ pointcuts and allows aspects to apply to beans declared in the IoC container. If you want to use additional pointcut types or apply your aspects “to objects created outside the Spring IoC container“, you have to use the AspectJ framework in your Spring application and use it’s weaving feature.

Weaving is the process of linking aspects with other outsider application types or objects to create an advised object. This can be done at compile time (using the AspectJ compiler, for example), load time, or at runtime. Spring AOP, like other pure Java AOP frameworks, performs weaving at runtime only. In contrast, the AspectJ framework supports both compile-time and load-time weaving.

AspectJ compile-time weaving is done through a special AspectJ compiler called ajc. It can weave aspects into your Java source files and output woven binary class files. It can also weave aspects into your compiled class files or JAR files. This process is known as post-compile-time weaving. You can perform compile-time and post-compile-time weaving for your classes before declaring them in the Spring IoC container. Spring is not involved in the weaving process at all. For more information on compile-time and post-compile-time weaving, please refer to the AspectJ documentation.

AspectJ load-time weaving (also known as LTW) happens when the target classes are loaded into JVM by a class loader. For a class to be woven, a special class loader is required to enhance the bytecode of the target class. Both AspectJ and Spring provide load-time weavers to add load-time weaving capability to the class loader. You need only simple configurations to enable these load-time weavers.


## 📖 Spring MVC <div id="mvc"></div>

### Q. What is Spring MVC?
The Spring Web MVC framework provides **Model-View-Controller** architecture and ready components that can be used to develop flexible and loosely coupled web applications. The MVC pattern results in separating the different aspects of the application (input logic, business logic, and UI logic).

1) The **Model** encapsulates the application data and in general they will consist of POJO.
2) The **View** is responsible for rendering the model data and in general it generates HTML output that the client's browser can interpret.
3) The **Controller** is responsible for processing user requests and building an appropriate model and passes it to the view for rendering.

### Q. What is DispatcherServlet?
**DispatcherServlet** acts as **front controller** for Spring based web applications. It provides a mechanism for request processing where actual work is performed by configurable, delegate components. It is inherited from **javax.servlet.http.HttpServlet**, it is typically configured in the web.xml file.

<img src="https://static.wixstatic.com/media/f03846_de0bb4b9e92342ceb9b5a8d8ed2bc407~mv2.png/v1/fill/w_630,h_379,al_c,q_85,usm_0.66_1.00_0.01/f03846_de0bb4b9e92342ceb9b5a8d8ed2bc407~mv2.webp" height="400" width="650" />

<img src="https://terasolunaorg.github.io/guideline/1.0.1.RELEASE/en/_images/RequestLifecycle.png" height="500" width="700" />

### Q. How to configure DispatcherServlet in Spring?
The DispatcherServlet is like any other Servlet class and it has to be declared inside the deployment descriptor or web.xml file as shown below:

```XML
<web-app>

    <servlet>
        <servlet-name>example</servlet-name>
        <servlet-class>
            org.springframework.web.servlet.DispatcherServlet
        </servlet-class>
        <load-on-startup>1</load-on-startup>
    </servlet>

    <servlet-mapping>
        <servlet-name>example</servlet-name>
        <url-pattern>*.form</url-pattern>
    </servlet-mapping>

</web-app>
```
In the preceding example, all requests ending with .form will be handled by the example DispatcherServlet. 

### Q. What is HandlerMapping?
**HandlerMapping** is an interface that defines a mapping **between requests and handler objects**. While Spring MVC framework provides some ready-made implementations, the interface can be implemented by developers to provide customized mapping strategy.

### Q. What is HandlerAdapter?


### Q. What is ViewResolver?


### Q. What does <mvc:annotation-driven /> do?
**<mvc:annotation-driven />** tag defaults the basic components required for delegating the requests to your Controllers.

If this tag is not added to the XML, then you will have to manually define the beans for components like **HandlerAdapter, HandlerMapping, Binding Initializer, Request Message converters, etc**. This tag helps registering the following components.

**DefaultAnnotationHandlerMapping** - This is a HandlerMapping implementation which maps the HTTP requests to the handler methods defined using the ***@RequestMapping*** annotation.

**AnnotationMethodHandlerAdapter** - It is responsible for scanning the controllers to identify methods (and parameters) annotated with @MVC annotations. It scans and caches handler methods annotated with ***@RequestMapping***. Also handles the ***@RequestParam***, @***ModelAttribute***, ***@SessionAttributes*** and ***@InitBinder*** annotations.

**ConfigurableWebBindingInitializer** - The initializer for the Web Data Binder. Helps in declaratively configuring the Web Binder with validators, conversion services, property editors, etc.
LocalValidatorFactoryBean - Implements the validator interface and enables JSR303 validation. This is injected into ConfigurableWebBindingInitializer.

**FormattingConversionServiceFactoryBean** - A conversion factory that returns conversion services for basic objects like date and numbers. This factory is again injected into ConfigurableWebBindingInitializer.

**Message Converters:**

1) **ByteArrayHttpMessageConverter** - A HTTP request message converter that reads a HTTP message body and returns a byte stream. It can also read a byte stream and construct a response body. Used for receiving and sending documents like PDF, XLS, etc.
2) **StringHttpMessageConverter** - A HTTP request message converter that reads a plain text request body and binds it to a String object. And vice-versa with response.
3) **FormHttpMessageConverter** - A HTTP request message converter that reads a form encoded request body and binds it to a form Binding object.
4) **SourceHttpMessageConverter** - A HTTP request converter that converts a XML message body to/from Binding Object.

If these beans are defined in the XML instead of using <mvc:annotation-driven>, it would look something like this.

```XML
<beans xmlns:context="http://www.springframework.org/schema/context" xmlns:mvc="http://www.springframework.org/schema/mvc" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://www.springframework.org/schema/beans" xsi:schemalocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.0.xsd
                http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.0.xsd
                http://www.springframework.org/schema/mvc http://www.springframework.org/schema/mvc/spring-mvc-3.0.xsd">
 
 
 <bean class="org.springframework.web.servlet.mvc.annotation.DefaultAnnotationHandlerMapping">
  <property name="order" value="0">
 </property></bean>
 
 <bean class="org.springframework.web.servlet.mvc.annotation.AnnotationMethodHandlerAdapter">
  <property name="webBindingInitializer">
   <bean class="org.springframework.web.bind.support.ConfigurableWebBindingInitializer">
    <property name="validator" ref="validator">
   </property></bean>
  </property>
  <property name="messageConverters">
   <list>
    <bean class="org.springframework.http.converter.ByteArrayHttpMessageConverter">
    <bean class="org.springframework.http.converter.StringHttpMessageConverter">
    <bean class="org.springframework.http.converter.FormHttpMessageConverter">
    <bean class="org.springframework.http.converter.xml.SourceHttpMessageConverter">
   </bean></bean></bean></bean></list>
  </property>
 </bean>
 
 <bean class="org.springframework.validation.beanvalidation.LocalValidatorFactoryBean" id="validator">
 <bean class="org.springframework.format.support.FormattingConversionServiceFactoryBean" id="conversion-service">
 
</bean></bean></beans>
```

### Q. 


### Q. 


### Q. 

### Q. 