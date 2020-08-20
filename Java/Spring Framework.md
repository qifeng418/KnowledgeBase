[Spring](#spring)

[Spring IoC](#ioc)

[Spring AOP](#aop)

[Spring MVC](#mvc)


## 📖 Spring <div id="spring"></div>

### Q: What is Spring?

Spring is an open source development framework for enterprise Java. The core features of the Spring Framework can be used in developing any Java application, but there are extensions for building web applications on top of the Java EE platform. Spring framework targets to make J2EE development easier to use and promote good programming practice by enabling a POJO-based programming model.

### Q. Describe Spring Ecosystem?
<img src="https://www.softmelt.com/upload/images/Article/Java/springsystem.png" height="500" width="980" />

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

<img src="https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/05/ioc-2.png" height="240" width="300" />

At the core of the Spring Framework, lies the Spring container. The container creates the object, wires them together, configures them and manages their complete life cycle. The Spring container makes use of Dependency Injection to manage the components that make up an application. The container receives instructions for which objects to instantiate, configure, and assemble by reading the configuration metadata provided. This metadata can be provided either by XML, Java annotations or Java code.

### Q. What are Beans in Spring?
In Spring, the objects that form the backbone of your application and that are **managed by the Spring IoC container** are called beans. A bean is an object that is instantiated, assembled, and otherwise managed by a Spring IoC container. Otherwise, a bean is simply one of many objects in your application.

<img src="https://docs.spring.io/spring/docs/3.2.x/spring-framework-reference/html/images/singleton.png" height="320" width="550" />

### Q. What are Bean Factory and ApplicationContext?
<img src="https://images0.cnblogs.com/blog2015/285763/201508/091224415652965.jpg" height="1000" width="1500" />

Spring makes use of Java POJO classes and configuration metadata to produce a fully configured and executable system or application. There are two types of IoC containers:

**Bean Factory**:

It is an interface defined in **org.springframework.beans.factory.BeanFactory**. It provides the basic support for Dependency Injection. It is based on **factory design pattern** which creates the beans of any type. BeanFactory follows **lazy-initialization** technique which means beans are loaded as soon as bean factory instance is created but the beans are created only when getBean() method is called. The XmlBeanFactory is the implementation class for the BeanFactory interface. To use the BeanFactory, you need to create the instance of XmlBeanFactory class as shown below.

```Java
BeanFactory beanFactory = new XmlBeanFactory(new ClassPathResource("beans.xml"));
```

**ApplicationContext**:

It is an interface defined in **org.springframework.context.ApplicationContext**. It is the advanced Spring container and is built on top of the BeanFactory interface. ApplicationContext supports the features supported by Bean Factory but also provides some additional functionalities. ApplicationContext follows **eager-initialization** technique which means instance of beans are created as soon as you create the instance of Application context. The ClassPathXmlApplicationContext class is the implementation class of ApplicationContext interface. You need to instantiate the ClassPathXmlApplicationContext class to use the ApplicationContext as shown below.

```Java
ApplicationContext context = new ClassPathXmlApplicationContext("beans.xml"); 
```

**Conclusion**:

The ApplicationContext includes all the functionality of the BeanFactory. It is generally recommended to use the former. There are some limited situations, such as in mobile applications, where memory consumption might be critical. In those scenarios, it would be justifiable to use the more lightweight BeanFactory. However, in most enterprise applications, the ApplicationContext is what you will want to use.

### Q. What is IoC?
**Inversion of Control** is a principle in software engineering by which the control of objects or portions of a program is transferred to a container or framework. It's most often used in the context of object-oriented programming.

By contrast with traditional programming, in which our custom code makes calls to a library, IoC enables a framework to take control of the flow of a program and make calls to our custom code. To enable this, frameworks use abstractions with additional behavior built in. If we want to add our own behavior, we need to extend the classes of the framework or plugin our own classes.

Inversion of Control can be achieved through various mechanisms such as: Strategy design pattern, Service Locator pattern, Factory pattern, and **Dependency Injection (DI)**.

### Q. What are the advantages of IoC?
1) **Decoupling** the execution of a task from its implementation
making it easier to switch between different implementations
greater modularity of a program.
2) Greater ease in testing a program by **isolating** a component or mocking its dependencies and allowing components to communicate through contracts.

### Q: What is Dependency Injection?
Dependency Injection (DI) is a design pattern used to implement IoC. It allows the creation of dependent objects outside of a class and provides those objects to a class through different ways. Using DI, we move the creation and binding of the dependent objects outside
 of the class that depends on them.

It bastically means that you do not create your objects but describe how they should be created. You don't directly connect your components and services together in code but describe which services are needed by which components in a configuration file. A container (the IOC container) is then responsible for hooking it all up.

### Q. What are the ways of creating Beans using XML in Spring?

1) Use default constructor
```XML
	<bean id="factory" class="com.qifeng.factory.Factory"></bean>
```

2) Use method in another class
```XML
    <bean id="factory" class="com.qifeng.factory.Factory"></bean>
	<bean id="service" factory-bean="com.qifeng.factory.Factory" factory-method="getService"></bean>
```

3) Use static method in another class
```XML
	<bean id="service" class="com.qifeng.factory.Factory" factory-method="getService"></bean>
```

### Q. Explain Bean scopes?
| Scope	| Description |
| -- | -- |
| singleton | Scopes a single bean definition to **a single object** instance per Spring IoC container. |
| prototype | Scopes a single bean definition to **any number of object** instances. |
| request | Scopes a single bean definition to the lifecycle of **a single HTTP request**; that is each and every HTTP request will have its own instance of a bean created off the back of a single bean definition. Only valid in the context of a web-aware Spring ApplicationContext. |
| session | Scopes a single bean definition to the lifecycle of **a HTTP Session**. Only valid in the context of a web-aware Spring ApplicationContext. |
| global session | Scopes a single bean definition to the lifecycle of **a global HTTP Session**. Typically only valid when used in a portlet context. Only valid in the context of a web-aware Spring ApplicationContext. |
|  |  |

### Q. Explain life cycle of Beans in Spring?
When a bean is instantiated, it may be required to perform some initialization to get it into a usable state. Similarly, when the bean is no longer required and is removed from the container, some cleanup may be required.

```XML
	<bean id="factory" class="com.qifeng.factory.Factory"
        init-method = "init"
        destroy-method = "destroy">
    </bean>
```

### Q: What are the different types of IoC (dependency injection)?
**Constructor-based dependency injection** − Constructor-based DI is accomplished when the container invokes a class constructor with a number of arguments, each representing a dependency on other class.

**Setter-based dependency injection** − Setter-based DI is accomplished by the container calling setter methods on your beans after invoking a no-argument constructor or no-argument static factory method to instantiate your bean.

### Q. How to use Constructor-based DI to inject data of Beans?
```XML
	<bean id="service" class="com.qifeng.service.serviceImpl" >
        <constructor-arg name="name" value="Jason"></constructor-arg>
        <constructor-arg name="age" value="25"></constructor-arg>
        <constructor-arg name="birthday" ref="now"></constructor-arg>
    </bean>
    <bean id="now" class="java.Util.Date"></bean>
```

### Q. How to use Setter-based DI to inject data of Beans?
```XML
	<bean id="service" class="com.qifeng.service.serviceImpl" >
        <property name="name" value="Jason"></property>
        <property name="age" value="25"></property>
        <property name="birthday" ref="now"></property>
    </bean>
    <bean id="now" class="java.Util.Date"></bean>
```

### Q. How to inject complex data type(List, Map, Set)?
```XML
	<bean id="service" class="com.qifeng.service.serviceImpl" >
        <property name="myArr">
            <array>
                <value>AAA</value>
                <value>BBB</value>
            </array>
        </property>

        <property name="myList">
            <list>
                <value>AAA</value>
                <value>BBB</value>
            </list>
        </property>

        <property name="mySet">
            <set>
                <value>AAA</value>
                <value>BBB</value>
            </set>
        </property>

        <property name="myMap">
            <map>
                <entry key="keyA" value="AAA"></entry>
                <entry key="keyB" value="BBB"></entry>
            </map>
        </property>
    </bean>
```

### Q: Constructor Injection vs. Spring Setter?
1) The fundamental difference between setter and constructor injection, as their name implies, is How dependency is injected.  Setter injection in Spring uses setter methods like setDependency() to inject dependency on any bean managed by Spring's IOC container. On the other hand, constructor injection uses the constructor to inject dependency on any Spring-managed bean.

2) Because of using the setter method, setter Injection in more readable than constructor injection in Spring configuration file usually applicationContext.xml. Since the setter method has name like setReporotService() by reading Spring XML config file you know which dependency you are setting. While in constructor injection, since it uses an index to inject the dependency, it's not as readable as setter injection and you need to refer either Java documentation or code to find which index corresponds to which property.

3) Another difference between setter vs constructor injection in Spring and one of the drawbacks of setter injection is that it does not ensures dependency Injection. You can not guarantee that certain dependency is injected or not, which means you may have an object with incomplete dependency. On the other hand, constructor Injection does not allow you to construct an object until your dependencies are ready.

4) One more drawback of setter Injection is Security. By using setter injection, you can override certain dependency which is not possible with constructor injection because every time you call the constructor, a new object is gets created.

5) One of our reader Murali Mohan Reddy pointed out one more difference between Setter and Constructor Injection in Spring, where later can help if there is a circular dependency between two object A and B.

### Q. What are the Annotations use in Spring IoC?
@Configuration

@Import

**@ComponentScan**: Configures component scanning directives for use with @Configuration classes. Here we can specify the base packages to scan for spring components.

**@Component**: Indicates that an annotated class is a “component”. Such classes are considered as candidates for auto-detection when using annotation-based configuration and classpath scanning.

**@Service**: Indicates that an annotated class is a “Service”. This annotation serves as a specialization of @Component, allowing for implementation classes to be autodetected through classpath scanning.

**@Repository**: Indicates that an annotated class is a “Repository”. This annotation serves as a specialization of @Component and advisable to use with DAO classes.

**@Autowired**: Spring @Autowired annotation is used for automatic injection of beans. Spring @Qualifier annotation is used in conjunction with Autowired to avoid confusion when we have two of more bean configured for same type.

@Qualifier

@Resource

@Scope

@PostConstruct

@PreDestroy

@Bean

@PropertySource: provides a simple declarative mechanism for adding a property source to Spring’s Environment. There is a similar annotation for adding an array of property source files i.e @PropertySources.


### Q. What is AnnotationConfigApplicationContext?



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

### Q. Advantages of Spring MVC?
**Separate roles** - The Spring MVC separates each role, where the model object, controller, command object, view resolver, DispatcherServlet, validator, etc. can be fulfilled by a specialized object.

**Light-weight** - It uses light-weight servlet container to develop and deploy your application.

**Powerful Configuration** - It provides a robust configuration for both framework and application classes that includes easy referencing across contexts, such as from web controllers to business objects and validators.

**Rapid development** - The Spring MVC facilitates fast and parallel development.

**Reusable business code** - Instead of creating new objects, it allows us to use the existing business objects.

**Easy to test** - In Spring, generally we create JavaBeans classes that enable you to inject test data using the setter methods.

**Flexible Mapping** - It provides the specific annotations that easily redirect the page.

### Q. What is deployment descriptor?
The **deployment descriptor** is a file named **web.xml**. It resides in the app's WAR under the **WEB-INF/** directory. The file is an XML file whose root element is ```<web-app>```.

A web application's deployment descriptor describes the classes, resources and configuration of the application and how the web server uses them to serve web requests. When the web server receives a request for the application, it uses the deployment descriptor to **map the URL of the request to the code** that ought to handle the request.

### Q. What are ApplicationContext and WebApplicationContext?
Both **ApplicationContext** and **WebApplicationContext** are the **spring containers** where WebApplicationContext is child of the ApplicationContext interface.

ApplicationContext (i.e. Root Application Context):

In Spring Mvc, for every web application, applicationContext.xml file used as the root context configuration. Spring loads this file and creates the ApplicationContext for **whole application**. File applicationContext.xml is loaded by **ContextLoaderLoaderLinstner** which is configured into web.xml file as the context configuration. The default location and name of the Root Application Context are under WEB-INF folder and applicationContext.xml respectively and throw FileNotFoundException if it could not find this file in this location. Otherwise we have to declare explicitly the context configuration file name in web.xml using the contextConfigLocation param. There will be only one application context per web application.

WebApplicationContext:

WebApplicationContext, in Spring, is web aware ApplicationContext i.e it has **Servlet Context information**. In single web application there can be multiple WebApplicationContext. That means **each DispatcherServlet associated with single WebApplicationContext**. The WebApplicationContext configuration file *-servlet.xml is specific to the DispatcherServlet and a web application can have more than one DispatcherServlet configured to handle the requests and each DispatcherServlet would have a separate *-servlet.xml file to configure. But, applicationContext.xml will be common for all the servlet configuration files. By default DispatcherServlet loads file name servletName-servlet.xml from your webapps WEB-INF folder. If you want to change the name of that file name or change the location, add init-param with contextConfigLocation as param name.

<img src="https://i1.wp.com/www.dineshonjava.com/wp-content/uploads/2017/02/ApplicationContext-vs-WebApplicationContext.png?w=530&ssl=1" height="230" width="500" />

<img src="https://docs.spring.io/spring/docs/3.2.x/spring-framework-reference/html/images/mvc-contexts.gif" height="450" width="600" />

### Q. What is ContextLoaderListener?
ContextLoaderListener creates a **root web-application-context** for the web-application and puts it in the ServletContext. This context can be used to load and unload the spring-managed beans ir-respective of what technology is being used in the controller layer(Struts or Spring MVC).

### Q. What is DispatcherServlet?
**DispatcherServlet** acts as **front controller** for Spring based web applications. It provides a mechanism for request processing where actual work is performed by configurable, delegate components. It is inherited from **javax.servlet.http.HttpServlet**, it is typically configured in the web.xml file.

DispatcherServlet acts as a Servlet, but it does more than just that. It is completely integrated with the Spring **IoC container** so it allows you to use every feature that Spring has.

After receiving an HTTP request, DispatcherServlet consults the **HandlerMapping** (configuration files) to call the appropriate Controller. The Controller takes the request and calls the appropriate service methods and set model data and then returns view name to the DispatcherServlet.

The DispatcherServlet will take help from **ViewResolver** to pick up the defined view for the request. Once the view is finalized, the DispatcherServlet passes the model data to the view which is finally rendered on the browser.

<img src="https://static.wixstatic.com/media/f03846_de0bb4b9e92342ceb9b5a8d8ed2bc407~mv2.png/v1/fill/w_630,h_379,al_c,q_85,usm_0.66_1.00_0.01/f03846_de0bb4b9e92342ceb9b5a8d8ed2bc407~mv2.webp" height="400" width="650" />

<img src="https://terasolunaorg.github.io/guideline/1.0.1.RELEASE/en/_images/RequestLifecycle.png" height="500" width="700" />

### Q. How to configure DispatcherServlet in Spring?
The DispatcherServlet is like any other Servlet class and it has to be declared inside the deployment descriptor or web.xml file as shown below:

```XML
<web-app>
    <servlet>
		<servlet-name>dispatcherServlet</servlet-name>
		<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
		
		<init-param>
			<param-name>contextConfigLocation</param-name>
			<param-value>classpath:springmvc.xml</param-value>
		</init-param>
		
		<load-on-startup>1</load-on-startup>	
	</servlet>

	<servlet-mapping>
		<servlet-name>dispatcherServlet</servlet-name>
		<url-pattern>*.form</url-pattern>
	</servlet-mapping>
</web-app>
```
In the preceding example, all requests ending with .form will be handled by the example DispatcherServlet. 


### Q. What is HandlerMapping?
**HandlerMapping** is an interface that defines a mapping **between requests and handler objects**. While Spring MVC framework provides some ready-made implementations, the interface can be implemented by developers to provide customized mapping strategy.

### Q. What is HandlerAdapter?
The **HandlerAdapter** is basically an interface which facilitates the handling of HTTP requests in a very flexible manner in Spring MVC.

It's used in conjunction with the **HandlerMapping**, which maps a method to a specific URL.

The **DispatcherServlet** then uses a HandlerAdapter to invoke this method. The servlet doesn't invoke the method directly – it basically serves as a bridge between itself and the handler objects, leading to a loosely coupling design.

### Q. What is ViewResolver?
The ViewResolver maps view names to actual views.

And the Spring framework comes with quite a few view resolvers e.g. **InternalResourceViewResolver**, **XmlViewResolver**, **ResourceBundleViewResolver** and a few others.

Take InternalResourceViewResolver class as example, it defines **prefix** and **suffix** properties to resolve the view component.

```XML
<bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
    <property name="prefix" value="/WEB-INF/views/" />
    <property name="suffix" value=".jsp" />
</bean>
```
So with above view resolver configuration, if controller method return “login” string, then the “/WEB-INF/views/login.jsp” file will be searched and rendered.

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

### Q. What is the Purpose of @EnableWebMVC?
The **@EnableWebMvc** annotation's purpose is to enable Spring MVC via Java configuration. It's equivalent to <mvc: annotation-driven /> in an XML configuration. This annotation imports Spring MVC Configuration from WebMvcConfigurationSupport. It enables support for @Controller-annotated classes that use @RequestMapping to map incoming requests to a handler method.

### Q. Annotation @Controller explanation?
The **@Controller** is a Spring MVC annotation to define a Controller, but in reality, it's just a stereotype annotation. You can even create a controller without @Controller by annotating the Spring MVC Controller classes using the **@Component** annotation. The real job of request mapping to handler method is done using the **@RequestMapping** annotation.

### Q. @Autowired vs. @Inject vs. @Resource?
**@Autowired** – Defined in the ***package org.springframework.bean.factory*** and part of Spring framework.

**@Inject** – Defined in the ***javax.inject*** package. In order to access the @Inject annotation, the javax.inject library has to be declared as a Maven dependency.

**@Resource** – Defined in the ***javax.annotation*** package and this annotation is part of the JSR-250 annotation collection and is packaged with Java EE.

@Autowired and @Inject annotation behave identically. These two annotations use ***AutowiredAnnotationBeanPostProcessor*** to inject dependencies. (**Order**: Matches by Type --> Restricts by Qualifiers -->
Matches by Name)

@Resource uses ***CommonAnnotationBeanPostProcessor*** to inject dependencies. (**Order**: Matches by Name --> Matches by Type --> Restricts by Qualifiers)

### Q. Annotation @RequestMapping explanation?
**@RequestMapping** maps HTTP requests to handler methods of MVC and REST controllers.

The @RequestMapping annotation can be applied to **class-level** and/or **method-level** in a controller. The class-level annotation maps a specific request path or pattern onto a controller. We can then apply additional method-level annotations to make mappings more specific to handler methods.

```Java
@RestController
@RequestMapping("/home")
public class IndexController {
    @RequestMapping(value = "/fetch/{id}", method = RequestMethod.GET)
    String getDynamicUriValue(@PathVariable String id) {
        System.out.println("ID is " + id);
        return "Dynamic URI parameter fetched";
    }
    @RequestMapping(value = "/fetch/{id:[a-z]+}/{name}", method = RequestMethod.GET)
    String getDynamicUriValueRegex(@PathVariable("name") String name) {
        System.out.println("Name is " + name);
        return "Dynamic URI parameter fetched using regex";
    }
}
```

### Q. What are the composed annotations of @RequestMapping?
Spring 4.3 introduced method-level variants, also known as composed annotations of @RequestMapping. The composed annotations better express the semantics of the annotated methods. They act as wrapper to@RequestMapping and have become the standard ways of defining the endpoints.

For example, **@GetMapping** is a composed annotation that acts as a shortcut for **@RequestMapping(method =RequestMethod.GET)**.

The method level variants are:
```Java
@GetMapping
@PostMapping
@PutMapping
@DeleteMapping
@PatchMapping
```

### Q. Annotation @RequestParam explanation?
**@RequestParam** is a Spring MVC annotation that is used to extract a request parameter or query parameters from the URL in the Controller's handler method.

```Java
public String personDetail(@RequestParam("id") long id){
  ....
  return "personDetails";
}
```
The @RequestParam annotation also supports data type conversion, e.g. you can see here a String is converted to log automatically, but it can also result in an exception if query parameter is not present or in case of type mismatch. You can also make the parameter optional by using requried=false, e.g. ***@RequestParam (value="id", required=false)***

### Q. Annotation @RequestBody and @ResponseBody explanation?
**@RequestBody** and **@ResponseBody** annotations are used to bind the HTTP request/response body with a domain object in method parameter or return type. Behind the scenes, these annotation uses **HTTP Message converters** to convert the body of HTTP request/response to domain objects.

Example of @RequestBody:
```Java
@PostMapping("/url")
public urlBo getUrlByPhoneNumber(@RequestBody String json,HttpServetRequest request){
    UrlBo ub=new Gson().fromJson(json,UrlBo.class);
    ....
}
```

Example of @ResponseBody:
```Java
@RequestMapping("/getList")
@ResponseBody
public Map<String,Object> getStudentList(HtppServletRequest request){
    Map<String,Object> map=new HashMap<String,Object>();
    Dto dto=getParamAsDto(request);
    List li=studentAction.getList(dto.get("age"));
    map.put("studentInfo",li);
}
}
```

**@PathVariable**


**@RequestHeader**

**@CoolieValue**

**@ModelAttribute**

**@SessionAttribute**

### Q. How to do Validation Using Spring MVC?
Spring MVC supports **JSR-303** specifications by default. We need to add JSR-303 and its implementation dependencies to our Spring MVC application. Hibernate Validator, for example, is one of the JSR-303 implementations at our disposal.

JSR-303 is a specification of the Java API for bean validation.Properties of a bean meet specific criteria, using annotations such as **@NotNull**, **@Min**, and **@Max**.

Spring offers the **@Validator** annotation and the **BindingResult class**. The Validator implementation will raise errors in the controller request handler method when we have invalid data. Then we may use the BindingResult class to get those errors.

Besides using the existing implementations, we can make our own. To do so, we create an annotation that conforms to the JSR-303 specifications first. Then, we implement the Validator class. Another way would be to implement Spring's Validator interface and set it as the validator via **@InitBinder** annotation in Controller class.

### Q. What is Model?
The model can supply attributes used for rendering views. To provide a view with usable data, we simply add this data to its Model object. Additionally, maps with attributes can be merged with Model instances.

```Java
@GetMapping("/showViewPage")
public String passParametersWithModel(Model model) {
    Map<String, String> map = new HashMap<>();
    map.put("spring", "mvc");
    model.addAttribute("message", "Baeldung");
    model.mergeAttributes(map);
    return "viewPage";
}
```

### Q. What is ModelMap?
Just like the Model interface above, ModelMap is also used to pass values to render a view. The advantage of ModelMap is it gives us the ability to pass a collection of values and treat these values as if they were within a Map.

```Java
@GetMapping("/printViewPage")
public String passParametersWithModelMap(ModelMap map) {
    map.addAttribute("welcomeMessage", "welcome");
    map.addAttribute("message", "Baeldung");
    return "viewPage";
}
```

### Q. What is ModelAndView?
This interface allows us to pass all the information required by Spring MVC in one return.

```Java
@GetMapping("/goToViewPage")
public ModelAndView passParametersWithModelAndView() {
    ModelAndView modelAndView = new ModelAndView("viewPage");
    modelAndView.addObject("message", "Baeldung");
    return modelAndView;
}
```

### Q. What is a MultipartResolver and when its used?
