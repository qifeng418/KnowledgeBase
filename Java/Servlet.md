## 📖 Web Application

### Q: Web Server vs. Application Server?
A web server‘s fundamental job is to accept and fulfill requests from clients for static content from a website (HTML pages, files, images, video, and so on). The client is almost always a **browser** or **mobile application** and the request takes the form of a Hypertext Transfer Protocol (HTTP) message, as does the web server’s response.

An application server’s fundamental job is to provide its clients with access to what is commonly called **business logic**, which generates dynamic content; that is, it’s code that transforms data to provide the specialized functionality offered by a business, service, or application. An application server’s clients are often applications themselves, and can include web servers and other application servers. Communication between the application server and its clients might take the form of HTTP messages, but that is not required as it is for communication between web servers and their clients. Many other protocols are popular, including the variants of CGI (Common Gateway Interface).

### Q: What is a Web Client?
A web client is a software that helps in communicating with the server. Some of the most widely used web clients are Firefox, Google Chrome, Safari, etc. When we request something from the server (through URL), the web client takes care of creating a request and sending it to the server and then parsing the server response and present it to the user.

### Q: Java Web Application Directory Structure?
<img src="https://cdn.journaldev.com/wp-content/uploads/2013/08/WAR-directory-structure.png" height="400" width="600" />

### Q: What is Tomcat?
Apache Tomcat is an open-source implementation of the Java Servlet, JavaServer Pages, Java Expression Language and WebSocket technologies. Tomcat provides a "pure Java" HTTP web server environment in which Java code can run.



## 📖 Servlet

### Q: What is servlet?
Java Servlets are server-side Java program modules that process and answer client requests and implement the servlet interface. It helps in enhancing Web server functionality with minimal overhead, maintenance and support.

A servlet acts as an intermediary between the client and the server. As servlet modules run on the server, they can receive and respond to requests made by the client. Request and response objects of the servlet offer a convenient way to handle HTTP requests and send text data back to the client.

### Q: Disadvantages of CGI?
CGI(Common Gateway Interface) technology enables the web server to call an external program and pass HTTP request information to the external program to process the request. For each request, it starts a new process.
<img src="https://static.javatpoint.com/images/cgi.JPG" height="300" width="700" />

There are many problems in CGI technology:

1) If the number of clients increases, it takes more time for sending the response.
2) For each request, it starts a process, and the web server is limited to start processes.
3) It uses platform dependent language e.g. C, C++, perl.

### Q: Advantages of Servlet?
<img src="https://static.javatpoint.com/images/servlet.JPG" height="300" width="500" />

There are many advantages of Servlet over CGI. The web container creates threads for handling the multiple requests to the Servlet. Threads have many benefits over the Processes such as they share a common memory area, lightweight, cost of communication between the threads are low. The advantages of Servlet are as follows:

1) Better performance: because it creates a thread for each request, not process.
2) Portability: because it uses Java language.
3) Robust: JVM manages Servlets, so we don't need to worry about the memory leak, garbage collection, etc.
4) Secure: because it uses java language.

### Q: Static webpage vs Dynamic webpage?
The webpages which are same for all the users are static webpages and the webpages that are dynamically generated based on the user’s request (that may be different for each user depending on the request) are known as dynamic webpages. Servlet is mainly used for dynamic webpages.

### Q: What is a Servlet Container?
It provides the **runtime environment** for JavaEE applications. The client/user can request only a static WebPages from the server. If the user wants to read the web pages as per input then the servlet container is used in java.
The servlet container is the part of web server which can be run in a separate process. We can classify the servlet container states in three types:

1) Standalone: It is typical Java-based servers in which the servlet container and the web servers are the integral part of a single program. For example:- Tomcat running by itself
2) In-process: It is separated from the web server, because a different program runs within the address space of the main server as a plug-in. For example:- Tomcat running inside the JBoss.
3) Out-of-process: The web server and servlet container are different programs which are run in a different process. For performing the communications between them, web server uses the plug-in provided by the servlet container.

### Q: What are common tasks performed by Servlet Container?
Servlet containers are also known as web container, for example, Tomcat. Some of the important tasks of servlet container are:

Communication Support: Servlet Container provides easy way of communication between web client (Browsers) and the servlets and JSPs. Because of the container, we don’t need to build a server socket to listen for any request from the web client, parse the request and generate a response. All these important and complex tasks are done by container and all we need to focus is on business logic for the applications.
Lifecycle and Resource Management: Servlet Container takes care of managing the life cycle of servlet. From the loading of servlets into memory, initializing servlets, invoking servlet methods and to destroy them. The container also provides utility like JNDI for resource pooling and management.
Multithreading Support: Container creates a new thread for every request to the servlet and provides them request and response objects to the processing. So servlets are not initialized for each request and save time and memory.
JSP Support: JSPs doesn’t look like normal java classes but every JSP in the application is compiled by container and converted to Servlet and then container manages them like other servlets.
Miscellaneous Task: Servlet container manages the resource pool, perform memory optimizations, execute garbage collector, provides security configurations, support for multiple applications, hot deployment and several other tasks behind the scene that makes a developer life easier.

### Q: Life cycle of a servlet?
1) Loading of Servlet class: The servlet container finds the servlet class mentioned in web.xml file or annotation and loads it.
2) Servlet instantiation: The object of servlet class gets created in this phase.
3) Initialization : Servlet initialization by calling init() method.
4) Servicing the request: In this phase the servlet service the client request by calling the service() method.
5) Destroy: Last phase of servlet life cycle. The destroy() method free up the servlet instance so that it can be garbage collected.

### Q: Why we use Servlets?
1) To process the input data submitted by user.
2) Generate and return the dynamic response to the user based on the request.
3) Ideal programming language for interacting with database based on the user’s request.
4) A servlet can handle multiple request simultaneously which makes them a perfect choice for the high performing applications.

Q 5. Why Servlet is better than CGI?
1) Servlet responses faster than CGI because it uses the multithreading concept to service each request. CGI performance is not that good as it creates a new object for each request while servlet allots a new thread for each request.
2) Learning and implementing servlet is quite easier compared to CGI.
3) Memory consumption is low in servlet compared to CGI.

### Q: When is Servlet loaded?
1) When servlet container receives the **first request** from client(browser).
2) Admin of the application manually loads the servlet.
3) When the webserver(in which the servlet is deployed) gets started.

### Q: What is Servlet interface and what’s the use of it?
Servlet interface is an API for servlets. Every Servlet should either implement the servlet interface or extends the class which already implements the interface. **javax.servlet.GenericServlet** and **javax.servlet.http.HttpServlet** are the Servlet classes that implements Servlet interface, hence every servlet should either implement Servlet interface directly or by extending any of these classes.

### Q: What is ServletConfig?
ServletConfig is an object containing some initial parameters or configuration information created by Servlet Container and passed to the servlet during initialization. ServletConfig is **for a particular servlet**, that means one should store servlet specific information in web.xml and retrieve them using this object.

### Q: What is ServletContext?
ServletContext is the object created by Servlet Container to share initial parameters or configuration information to **the whole application**. All the servlets in the web application can access the ServletContext. It has the web-application information & resources which are common and accessible to all the servlets present in the web application.

### Q: ServletConfig vs ServletContext?
ServletConfig and ServletContext, both are objects created at the time of servlet initialization and used to provide some initial parameters or configuration information to the servlet. But, the difference lies in the fact that information shared by ServletConfig is for a specific servlet, while information shared by ServletContext is available for all servlets in the web application.

| ServletConfig | ServletContext |
| --- | --- |
| ServletConfig is servlet specific |	ServletContext is for whole application |
| Parameters of servletConfig are present as name-value pair in <init-param> inside <servlet> |	Parameters of servletContext are present as name-value pair in <context-param> which is outside of <servlet> and inside <web-app> |
| ServletConfig object is obtained by getServletConfig() method |	ServletContext object is obtained by getServletContext() method |
| Each servlet has got its own ServletConfig object | ServletContext object is only one and used by different servlets of the application |
| Use ServletConfig when only one servlet needs information shared by it | Use ServletContext when whole application needs information shared by it |

### Q: Difference between GenericServlet and HTTPServlet?
1) GenericServlet is an abstract class which implements Servlet interface while HTTPServlet abstract class extends the GenericServlet class. In short: GenericServlet class is a parent class for HTTPServlet.
2) GenericServlet does not support any protocol. HTTPSeervlet support HTTP and HTTPS protocol.
3) GenericServlet cannot handle cookies and session while HTTPServlet can handle them.

Q 12. Difference between forward() and sendRedirect()?
1) In forward() the same request is forwarded to the another resource. In sendRedirect() new request is send to the redirected resource.
2) forward() is taken care by the Servlet container while sendRedirect() is handled by the browser.
3) In forward() the URL(uniform resource locator) remains same on web browser. In sendRedirect() the URL changes in the web browser address bar.
4) forward() is faster compared to sendRedirect().

Q 13. What is deployment descriptor?
web.xml file of a web application is known as deployment descriptor. It is usually placed inside WEB-INF folder of application. It has the information like Servlet name, Servlet mapping etc. This file tells the Servlet container which Servlet class needs to be called for the given URL pattern.

Q 14. doGet() Vs doPost() methods?
1) In doGet(), the parameters are visible in the address bar, they get appended to the URL. In doPost() parameters are not visible in the address bar.
2) You can maximum transfer 1024 characters through GET request. doPost() doesn’t have any limitations.
3) doGet() is not good for sensitive data as the parameters do not get encrypted. In doPost() the parameters are encrypted hence it is more secure compared to doGet().
4) Method doGet() allow you to bookmark the resource. doPost() doesn’t allow bookmarks.
5) doGet() is faster compared to the doPost() method.

Q 15. What is the use of <load-on-startup>?
<load-on-startup> is used for specifying the Servlet files which needs to be loaded during server startup. The servlet files specified in this element are loaded as soon as the server starts, it does not wait for the first request for loading them up. This is how it is specified in web.xml file.

<servlet>
   <servlet-name>MyServletNameHere</servlet-name>
   <servlet-class>ServletClassHere-FullyQualified</servlet-class>
   <load-on-startup>1</load-on-startup>
</servlet>
If more than one files are specified then the files will be loaded in the same order in which they have been specified in it.

Q 20. What are the different types of session tracking mechanism supported by Servlets?
1) URL rewriting
2) Hidden Form Fields
3) Cookies
4) Secure Socket Layer(SSL) Sessions

Q 21. How URL rewriting maintains session?
In URL rewriting method, the session tracking data has been appended at the end of the URL to track the session.

Q 22. Explain Servlet chaining?
Servlet chaining is a concept where the request is processed in a chain of servlets. First Servlet processes the request partially and passes to the second one, then second servlet process it and passes to third one and so on. The last servlet returns the response to the client (browser).

Q 23. How to invalidate a session in servlet?
By calling session.invalidate() method.

Q 24. What are the main functions of Servlet container?
1) Servlet life cycle management
2) Maintains the interaction between servlet and webserver.
3) Providing multithreading support for processing more than one request simultaneously.
4) Managing of deployment descriptor web.xml file.

Q 25. What is <session-timeout> ?
The element <session-timeout> is used for specifying the timeout of a Session. This is how it is defined in the web.xml file.

<session-config>
       <session-timeout>35</session-timeout>
</session-config>
It would set the session timeout to 25 minutes.

Q 26. What is Servlet lazy loading and how it can be avoided?
The Servlet container does not initialize the Servlet on server startup by default. It only initializes a servlet when the it receives the request from the client. This is called lazy loading of Servlet.
By specifying <load-on-startup> element for a Servlet we can avoid lazy loading. The servlet files specified in <load-on-startup> are loaded as soon as the web sever starts.

Q 27. Why do we need constructor in servlet even though we have a init() method?
init() method is used for initializing the servlet however constructor is required in order to instantiate the Servlet class. Servlet container instantiate the Servlet class.

Q 28. When the Servlet is unloaded?
1) Admin manually unloads the servlet.
2) Web server shut down.

Q 29. How Servlet maintains session using cookies?
Cookie is a small piece of information, which is sent by a servlet to the Web browser. Cookies gets stored in the browser and returned back to the server when needed. A cookie has a name, a single value, and few other attributes.

Q 30. Why using cookies for session tracking is a bad practice?
There are several disadvantages of using cookies for session tracking. Few of them are:
1) Since cookies are stored on client-side (in the client’s browser), It will not be available if client browser clears or disables the cookies.
2) Implementing cookies for session tracking is much more difficult compared to other session management mechanism.
3) Cookies only work for HTTP protocol.

Q 31. How do I get the server info in Servlets?
Use this:

getServletContext().getServerInfo()
Q 32. How to get the client’s IP address in Servlets?
Using this:

request.getRemoteAddr()
Q 33. Why we use filters in Servlet?
We use filters for:
1) Security checks
2) Modifying the request or response
3) Data compression
4) Logging and auditing
5) Response compression

Q 34. What all protocols are supported by HTTPServlet?
HTTP and HTTPS protocols.

Q 35. What all protocols are supported by GenericServlet?
GenericServlet abstract class is not specific to any protocol.

Q 36. What are the new features added to Servlet 3?
1) Servlet Annotations
2) Web Fragments
3) Web components addition dynamically
4) Asynchronous Processing

Q 37. Do we override service() method?
No, we do not override the service() method. We generally override the doPost(), doGet() method based on the requirement.
