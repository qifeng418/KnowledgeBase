[](#)

[](#)

[](#)

[](#)

### Q. What are main differences between API and Web Service?
1) All Web services are APIs but not all APIs are Web services.
2) Web services might not contain all the specifications and cannot perform all the tasks that APIs would perform.
3) A Web service uses only three styles of use: **SOAP, REST and XML-RPC** for communication whereas API may be exposed to in multiple ways.
4) A Web service always needs a network to operate while APIs don’t need a network for operation.

### Q. What is SOAP?
**SOAP (Simple Object Access Protocol)** is a messaging protocol specification for exchanging structured information in the implementation of web services in computer networks. Its purpose is to provide extensibility, neutrality, verbosity and independence.

### Q. What is REST?
REST stands for **Representational State Transfer**. REST is an **architectural style** of developing web services which take advantage of the ubiquity of HTTP protocol and leverages HTTP method to define actions.

In the REST architectural style, ***every component is a resource***. Data and functionality are accessed using **Uniform Resource Identifiers (URIs)**, typically links on the Web. The resources are acted upon by using a set of simple, well-defined operations. The REST architectural style constrains an architecture to a client/server architecture and is designed to use a stateless communication protocol, typically HTTP. In the REST architecture style, clients and servers exchange representations of resources by using a standardized interface and protocol.

### Q. What Are RESTful Web Services?
Web services developed using REST style are known as RESTful web services.

Web Services that follow below principles are viewed as RESTful applications.

1) **Resource identification through URI**: A RESTful web service exposes a set of resources that identify the targets of the interaction with its clients. Resources are identified by URIs, which provide a global addressing space for resource and service discovery.

2) **Uniform interface**: Resources are manipulated using a fixed set of four create, read, update, delete operations: **PUT, GET, POST,** and **DELETE**. PUT creates a new resource, which can be then deleted by using DELETE. GET retrieves the current state of a resource in some representation. POST transfers a new state onto a resource.

3) **Self-descriptive messages**: Resources are decoupled from their representation so that their content can be accessed in a variety of formats, such as **HTML, XML, plain text, PDF, JPEG, JSON**, and others. Metadata about the resource is available and used, for example, to control caching, detect transmission errors, negotiate the appropriate representation format, and perform authentication or access control.

4) **Stateful interactions through hyperlinks**: Every interaction with a resource is stateless, that is, request messages are self-contained. Stateful interactions are based on the concept of explicit state transfer. Several techniques exist to exchange state, such as **URI rewriting, cookies, and hidden form fields**. State can be embedded in response messages to point to valid future states of the interaction.

### Q. What are the most commonly used HTTP methods supported by REST?
**GET** is only used to request data from a specified resource. Get requests can be cached and bookmarked. It remains in the browser history and has length restrictions. GET requests should never be used when dealing with sensitive data.

**POST** is used to send data to a server to create/update a resource. POST requests are never cached and bookmarked and do not remain in the browser history.

**PUT** replaces all current representations of the target resource with the request payload.

**DELETE** removes the specified resource.

**HEAD** asks for a response identical to that of a GET request, but without the response body.

**OPTIONS** is used to describe the communication options for the target resource.

### Q. 

### Q. 

### Q. 

### Q. 
### Q. 