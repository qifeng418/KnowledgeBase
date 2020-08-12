[Web Application](#web)

[Servlet and Container](#servlet)

[Request](#request)

[Response](#response)

[ServletContext](#context)

[Cookies](#cookies)

[Session](#session)



## 📖 Web Application <div id="web"></div>

### Q: Web Server vs. Application Server?
A web server‘s fundamental job is to accept and fulfill requests from clients for static content from a website (HTML pages, files, images, video, and so on). The client is almost always a **browser** or **mobile application** and the request takes the form of a Hypertext Transfer Protocol (HTTP) message, as does the web server’s response.

An application server’s fundamental job is to provide its clients with access to what is commonly called **business logic**, which generates dynamic content; that is, it’s code that transforms data to provide the specialized functionality offered by a business, service, or application. An application server’s clients are often applications themselves, and can include web servers and other application servers. Communication between the application server and its clients might take the form of HTTP messages, but that is not required as it is for communication between web servers and their clients. Many other protocols are popular, including the variants of CGI (Common Gateway Interface).

### Q: What is a Web Client?
A web client is a software that helps in communicating with the server. Some of the most widely used web clients are Firefox, Google Chrome, Safari, etc. When we request something from the server (through URL), the web client takes care of creating a request and sending it to the server and then parsing the server response and present it to the user.

### Q: Java Web Application Directory Structure?
<img src="https://cdn.journaldev.com/wp-content/uploads/2013/08/WAR-directory-structure.png" height="400" width="600" />

### Q: What is Tomcat?
Apache Tomcat is an open-source implementation of the Java Servlet, JavaServer Pages, Java Expression Language and WebSocket technologies. Tomcat provides a "pure Java" HTTP web server environment in which Java code can run.

### Q: Is Tomcat a Web Server or a Web Container?
It's both a web server (supports HTTP protocol) and a web container (supports JSP/Servlet API, also called "servlet container" at times).

However, it's not really meant to function as a high performance web server, nor does it include some features typical of a web server. Tomcat is meant to be used in conjunction with the Apache web server, where Apache manages static pages, caching, redirection, etc. and Tomcat handles the container (web application) functions. You'll often hear the phrase "Apache Tomcat" together, which is both a proper attribution of the Tomcat project (as part of the Apache Foundation), but also appropriate as a label, as they're usually used together as a package.

### Q: Static webpage vs Dynamic webpage?
The webpages which are same for all the users are static webpages and the webpages that are dynamically generated based on the user’s request (that may be different for each user depending on the request) are known as dynamic webpages. Servlet is mainly used for dynamic webpages.

## 📖 Servlet <div id="servlet"></div>

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

There are many advantages of Servlet over CGI. The web container creates threads for handling the multiple requests to the Servlet. Threads have many benefits over the Processes. For example, they share a common memory area, lightweight, cost of communication between the threads are low. The advantages of Servlet are as follows:

1) **Better performance**: because it creates a thread for each request, not process.
2) **Portability**: because it uses Java language.
3) **Robust**: JVM manages Servlets, so we don't need to worry about the memory leak, garbage collection, etc.
4) **Secure**: because it uses java language.

### Q: What is a Servlet Container?
It provides the **runtime environment** for JavaEE applications. The client/user can request only a static WebPages from the server. If the user wants to read the web pages as per input then the servlet container is used in java.
The servlet container is the part of web server which can be run in a separate process. We can classify the servlet container states in three types:

1) **Standalone**: It is typical Java-based servers in which the servlet container and the web servers are the integral part of a single program. For example:- Tomcat running by itself
2) **In-process**: It is separated from the web server, because a different program runs within the address space of the main server as a plug-in. For example:- Tomcat running inside the JBoss.
3) **Out-of-process**: The web server and servlet container are different programs which are run in a different process. For performing the communications between them, web server uses the plug-in provided by the servlet container.

### Q: What are common tasks performed by Servlet Container?

**Communication Support**: Servlet Container provides easy way of communication between web client (Browsers) and the servlets and JSPs. Because of the container, we don’t need to build a server socket to listen for any request from the web client, parse the request and generate a response. All these important and complex tasks are done by container and all we need to focus is on business logic for the applications.

**Lifecycle and Resource Management**: Servlet Container takes care of managing the life cycle of servlet. From the loading of servlets into memory, initializing servlets, invoking servlet methods and to destroy them. The container also provides utility like JNDI for resource pooling and management.

**Multithreading Support**: Container creates a new thread for every request to the servlet and provides them request and response objects to the processing. So servlets are not initialized for each request and save time and memory.

**JSP Support**: JSPs doesn’t look like normal java classes but every JSP in the application is compiled by container and converted to Servlet and then container manages them like other servlets.
Miscellaneous Task: Servlet container manages the resource pool, perform memory optimizations, execute garbage collector, provides security configurations, support for multiple applications, hot deployment and several other tasks behind the scene that makes a developer life easier.

### Q: What is Servlet interface and what’s the use of it?
Servlet interface is an API for servlets. Every Servlet should either implement the servlet interface or extends the class which already implements the interface. **javax.servlet.GenericServlet** and **javax.servlet.http.HttpServlet** are the Servlet classes that implements Servlet interface, hence every servlet should either implement Servlet interface directly or by extending any of these classes.

### Q: Difference between GenericServlet and HTTPServlet?
1) GenericServlet is an abstract class which implements Servlet interface while HTTPServlet abstract class extends the GenericServlet class. In short: GenericServlet class is a parent class for HTTPServlet.
2) GenericServlet does not support any protocol. HTTPSeervlet support HTTP and HTTPS protocol.
3) GenericServlet cannot handle cookies and session while HTTPServlet can handle them.

### Q: What are protocols supported by GenericServlet?
GenericServlet abstract class is not specific to any protocol.

### Q: What are protocols supported by HTTPServlet?
HTTP and HTTPS protocols.

### Q: Life cycle of a servlet?
1) **Loading of Servlet class**: The servlet container finds the servlet class mentioned in web.xml file or annotation and loads it.
2) **Servlet instantiation**: The object of servlet class gets created in this phase.
3) **Initialization**: Servlet initialization by calling init() method.
4) **Servicing the request**: In this phase the servlet service the client request by calling the service() method.
5) **Destroy**: Last phase of servlet life cycle. The destroy() method free up the servlet instance so that it can be garbage collected.

### Q: When is Servlet loaded?
1) When servlet container receives the **first request** from client(browser).
2) Admin of the application manually loads the servlet.
3) When the webserver(in which the servlet is deployed) gets started.

### Q. What is the use of tag "load-on-startup"?
Tag **"load-on-startup"** is used for specifying the Servlet files which needs to be loaded during server startup. The servlet files specified in this element are loaded as soon as the server starts, it does not wait for the first request for loading them up. This is how it is specified in web.xml file.
```XML
<servlet>
   <servlet-name>MyServletNameHere</servlet-name>
   <servlet-class>ServletClassHere-FullyQualified</servlet-class>
   <load-on-startup>1</load-on-startup>
</servlet>
```
If more than one files are specified then the files will be loaded in the same order in which they have been specified in it.

### Q. What is Servlet lazy loading and how it can be avoided?
The Servlet container does not initialize the Servlet on server startup by default. It only initializes a servlet when the it receives the request from the client. This is called **lazy loading** of Servlet.

By specifying "load-on-startup" element for a Servlet we can avoid lazy loading. The servlet files specified in "load-on-startup" are loaded as soon as the web sever starts.

### Q. When the Servlet is unloaded?
1) Admin manually unloads the servlet.
2) Web server shut down.

### Q. Why do we need constructor in servlet even though we have a init() method?
init() method is used for initializing the servlet however constructor is required in order to instantiate the Servlet class. Servlet container instantiate the Servlet class.

### Q. Do we override service() method?
No, we do not override the service() method. We generally override the doPost(), doGet() method based on the requirement.

### Q. doGet() vs. doPost() methods?
1) In **doGet()**, the parameters are visible in the address bar, they get appended to the URL. In **doPost()** parameters are not visible in the address bar.
2) You can maximum transfer 1024 characters through **GET** request. **doPost()** doesn’t have any limitations.
3) **doGet()** is not good for sensitive data as the parameters do not get encrypted. In **doPost()** the parameters are encrypted hence it is more secure compared to doGet().
4) Method **doGet()** allow you to bookmark the resource. **doPost()** doesn’t allow bookmarks.
5) **doGet()** is faster compared to the **doPost()** method.

### Q. What are the new features added to Servlet 3?
1) Servlet Annotations
2) Web Fragments
3) Web components addition dynamically
4) Asynchronous Processing




## 📖 Request <div id="request"></div>

### Q: Explain Servlet chaining?
Servlet chaining is a concept where the request is processed in a chain of servlets. First Servlet processes the request partially and passes to the second one, then second servlet process it and passes to third one and so on. The last servlet returns the response to the client (browser).

### Q. What is ServletRequest Hierarchy?
<img src="https://cdn.journaldev.com/wp-content/uploads/2013/08/Servlet-Hierarchy.png" height="280" width="500" />

**ServletRequest, HttpServletRequest, ServletResponse, HttpServletResponse** are all interfaces, in Tomcat container, there is a class **RequestFacade** that implements HttpServletRequest.

### Q. What are the info included in a Request?
[Reading: HTTP (HyperText Transfer Protocol)
Basics](https://www.ntu.edu.sg/home/ehchua/programming/webprogramming/HTTP_Basics.html)
1) Request Line
2) Request Headers
3) A blcnk line
4) Request Body
<img src="https://www.ntu.edu.sg/home/ehchua/programming/webprogramming/images/HTTP_RequestMessageExample.png" height="250" width="600" />

### Q. Differences between URI and URL?
URI: Uniform Resource Identifier. It is an identifier of a specific resource. Like a page, or book, or a document.

URL: Uniform Resource Locator. It is a special type of identifier that also tells you how to access it, such as HTTPs, FTP, etc.—like https://www.google.com.

Basically, being more specific is better, and a “URL” is a specific type of URI that provides an access method/location.

<img src="https://danielmiessler.com/images/url-uri-miessler-2019-white-e1576768407702.png.webp" height="400" width="400" />

### Q. What are the methods for getting Request Line?
Take above request as example.

```java
1) String getMethod() {Return "GET"}
2) String getContextPath() {Return "/doc"}
3) String getServletPath() {Return "/test"}
4) String getQueryStirng() {Return "name=Jason"}
5) String getRequestURI() {Return "/doc/test"}
6) StringBuffer getRequestURL() {Return ":http://localhost/doc/test"}
7) String getProtocol {Return "HTTP/1,1"}
8) String getRemoteAddr {Return ""}
```

### Q. What are the methods for getting Request Headers?

```java 
// get header according to header name
1) String getHeader(Stirng name)
// get all headers
2) Enumeration<String> getHeaderNames()
```

### Q. What are the methods for getting Request Body?
Only **POST** has Request Body.

```java
// get Stream object
BufferedReader getReader() // get character input stream
ServletInputStream getInputStream() // get byte input stream
```

### Q. What are the methods for getting request parameters?
```java
String getParameter(String name)
Stirng[] getParameterValues(Stirng name) // multiple values for one name
Enumeration<String> getParameterNames()
Map<String, String[]> getParameterMap()
```

### Q. How to forward a request?

```java
RequestDispatcher getRequestDispatcher(String path).forward()
```
When we use forward() method, the url doesn't change. Also, it can only forward to resources within internal server. **The forward is only one request**.

### Q. How to share data in Request?
```java
setAttribute(String name, Object obj)
Object getAttribute(String name)
removeAttribute(String name)
```

### Q. How to get ServletContext using Request?
```java
ServletContext servletContext = request.getServletContext();
```

## 📖 Response <div id="response"></div>

### Q. What are the info included in a Response?
1) Status Line
2) Response Headers
3) A blcnk line
4) Response Body
<img src="https://www.ntu.edu.sg/home/ehchua/programming/webprogramming/images/HTTP_ResponseMessageExample.png" height="250" width="600" />

### Q. Explain HTTP status code?
1) **1xx** Informational response
2)	**2xx** Success
3)	**3xx** Redirection
4)	**4xx** Client errors
5)	**5xx** Server errors

### Q. How to set status code?
```java
setStatus(int sc)
```

### Q. How to set Header?
```java
setHeader(String name, String value)
```
### Q. How to set Body?
```java
// character output stream
PrintWriter getWriter()
// byte outpurt stream
ServletOutputStream getOutputStream()
```

### Q. How to redirect in Response?
```java
response.setStatus(302);
response.setHeader("location", "/project/response2");

// another easy way
response.sendRedirect("/project/response2");
```

### Q. Differences between forward() and sendRedirect()?
<img src="https://i.stack.imgur.com/a3pCn.png" height="500" width="600" />

**Brief answer**
1) In **forward()** the same request is forwarded to the another resource. In **sendRedirect()** new request is send to the redirected resource.
2) **forward()** is taken care by the Servlet container while **sendRedirect()** is handled by the browser.
3) In **forward()** the URL remains same on web browser. In **sendRedirect()** the URL changes in the web browser address bar.
4) **forward()** is faster compared to **sendRedirect()**.

**requestDispatcher - forward() method**

1) When we use the **forward** method, the request is transferred to another resource within the same server for further processing.
2) In the case of **forward**, the web container handles all processing internally and the client or browser is not involved.
3) When **forward** is called on the **requestDispatcherobject**, we pass the request and response objects, so our old request object is present on the new resource which is going to process our request.
4) Visually, we are not able to see the **forwarded** address, it is transparent.
5) Using the **forward()** method is faster than sendRedirect.
6) When we redirect using forward, and we want to use the same data in a new resource, we can use request.**setAttribute()** as we have a request object available.

**SendRedirect**
1) In case of **sendRedirect**, the request is transferred to another resource, to a different domain, or to a different server for further processing.
2) When you use **sendRedirect**, the container transfers the request to the client or browser, so the URL given inside the sendRedirect method is visible as a new request to the client.
3) In case of **sendRedirect** call, the old request and response objects are lost because it’s treated as new request by the browser.
4) In the address bar, we are able to see the new **redirected** address. It’s not transparent.
5) **sendRedirect** is slower because one extra round trip is required, because a completely new request is created and the old request object is lost. Two browser request are required.
6) But in **sendRedirect**, if we want to use the same data for a new resource we have to store the data in session or pass along with the URL.

## 📖 ServletContext <div id="context"></div>


### Q. What is MINE type?


### Q: What is ServletConfig?
**ServletConfig** is an object containing some initial parameters or configuration information created by Servlet Container and passed to the servlet during initialization. ServletConfig is **for a particular servlet**, that means one should store servlet specific information in web.xml and retrieve them using this object.

### Q: What is ServletContext?
**ServletContext** is the object created by Servlet Container to share initial parameters or configuration information to **the whole application**. All the servlets in the web application can access the ServletContext. It has the web-application information & resources which are common and accessible to all the servlets present in the web application.

### Q: ServletConfig vs. ServletContext?
ServletConfig and ServletContext, both are objects created at the time of servlet initialization and used to provide some initial parameters or configuration information to the servlet. But, the difference lies in the fact that information shared by ServletConfig is for a specific servlet, while information shared by ServletContext is available for all servlets in the web application.

| ServletConfig | ServletContext |
| --- | --- |
| ServletConfig is servlet specific |	ServletContext is for whole application |
| Parameters of servletConfig are present as name-value pair in <init-param> inside <servlet> |	Parameters of servletContext are present as name-value pair in <context-param> which is outside of <servlet> and inside <web-app> |
| ServletConfig object is obtained by getServletConfig() method |	ServletContext object is obtained by getServletContext() method |
| Each servlet has got its own ServletConfig object | ServletContext object is only one and used by different servlets of the application |
| Use ServletConfig when only one servlet needs information shared by it | Use ServletContext when whole application needs information shared by it |


## 📖 Cookies <div id="cookies"></div>

### Q. What is Coolies in Servelt?

### Q. How Servlet maintains session using cookies?
Cookie is a small piece of information, which is sent by a servlet to the Web browser. Cookies gets stored in the browser and returned back to the server when needed. A cookie has a name, a single value, and few other attributes.

Q 30. Why using cookies for session tracking is a bad practice?
There are several disadvantages of using cookies for session tracking. Few of them are:
1) Since cookies are stored on client-side (in the client’s browser), It will not be available if client browser clears or disables the cookies.
2) Implementing cookies for session tracking is much more difficult compared to other session management mechanism.
3) Cookies only work for HTTP protocol.




## 📖 Session <div id="session"></div>

### Q. What are the different types of session tracking mechanism supported by Servlets?
1) URL rewriting
2) Hidden Form Fields
3) Cookies
4) Secure Socket Layer(SSL) Sessions

### Q. How URL rewriting maintains session?
In URL rewriting method, the session tracking data has been appended at the end of the URL to track the session.

### Q. How to invalidate a session in servlet?
By calling session.invalidate() method.

### Q. What is <session-timeout> ?
The element <session-timeout> is used for specifying the timeout of a Session. This is how it is defined in the web.xml file.
```XML
<session-config>
       <session-timeout>35</session-timeout>
</session-config>
```
It would set the session timeout to 25 minutes.




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

Q 13. What is deployment descriptor?
web.xml file of a web application is known as deployment descriptor. It is usually placed inside WEB-INF folder of application. It has the information like Servlet name, Servlet mapping etc. This file tells the Servlet container which Servlet class needs to be called for the given URL pattern.