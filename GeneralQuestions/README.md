# Interviews practice

## 1. General questions:
- Tell me a bit about yourself
- Why are you leaving your last job?
- Describe your ideal environment as a developer
- Why do you want to work for us? 
## 2. Question about experiences:
- What programming language or framework you're familiar with?
- Tell me about a project you completed successfully. Why do you consider it a success?
- Can you tell me briefly about some projects you’ve worked on and the approach you took from start to finish?
-  What online resources do you use to help you do your job? 

## 3. General tech questions:
-  What is MVC model?
> Difficulty : ⭐
<details>
    <summary>
        Answer
    </summary>
    <p>
MVC Pattern stands for Model-View-Controller Pattern. This pattern is used to separate application's concerns.

**Model** - Model represents an object or JAVA POJO carrying data. It can also have logic to update controller if its data changes.

**View** - View represents the visualization of the data that model contains.

**Controller** - Controller acts on both model and view. It controls the data flow into model object and updates the view whenever data changes. It keeps view and model separate.
    </p>
</details>

#### What is design pattern?
> Difficulty : ⭐⭐

<details>
    <summary>
        Answer
    </summary>
    <p>
        Design patterns represent the best practices used by experienced object-oriented software developers. Design patterns are solutions to general problems that software developers faced during software development. These solutions were obtained by trial and error by numerous software developers over quite a substantial period of time.
    </p>
</details>

#### What is http protocol?


> Difficulty : ⭐⭐

<details>
    <summary>
        Answer
    </summary>
    <p>
        HTTP is a protocol which allows the fetching of resources, such as HTML documents. It is the foundation of any data exchange on the Web and it is a client-server protocol, which means requests are initiated by the recipient, usually the Web browser. A complete document is reconstructed from the different sub-documents fetched, for instance text, layout description, images, videos, scripts, and more.
    </p>
</details>
 
#### What is an API? Give examples

> Difficulty : ⭐⭐⭐

<details>
    <summary>
        Answer
    </summary>
    <p>
         An API(Application programming interfaces) is a set of programming code that enables data transmission between one software product and another. It also contains the terms of this data exchange.
    </p>
</details>

#### What is OOP?

> Difficulty : ⭐⭐
<details>
    <summary>
        Answer
    </summary>
    <p>
        Object Oriented programming (OOP) is a programming paradigm that relies on the concept of classes and objects. It is used to structure a software program into simple, reusable pieces of code blueprints (usually called classes), which are used to create individual instances of objects. There are many object-oriented programming languages including JavaScript, C++, Java, and Python.
    </p>
</details>

#### List OOP principles?
> Difficulty : ⭐⭐

OOP based on 4 main principles:
- Encapsulation
- Abstraction
- Inheritance
- Polymorphism

#### What is the HTTP request methods?
> Difficulty : ⭐
<details>
    <summary>
        Answer
    </summary>
    <p>
       An HTTP request is an action to be performed on a resource identified by a given Request-URL. Request methods are case-sensitive, and should always be noted in upper case. There are various HTTP request methods, but each one is assigned a specific purpose.
    </p>
</details>

#### What Are the Various Types of HTTP Request Methods?
> Difficulty : ⭐

- **GET**: GET is used to retrieve and request data from a specified resource in a server.
- **HEAD**: The HEAD technique requests a reaction that is *similar to that of GET* request, but *doesn’t have a message-body in the response*.
- **POST**: POST requests are utilized to send data to a server to create or update a resource.
- **PUT**: PUT is similar to POST as it is used to send data to the server to create or update a resource. The difference between the two is that PUT requests are idempotent. This means that if you call the same PUT requests multiple times, the results will always be the same.
- **DELETE**: the DELETE request method is used to delete resources indicated by a specific URL.

#### Difference between GET and POST method in HTTP
> Difficulty : ⭐

GET carries request parameter appended in URL string while POST carries request parameter in message body which makes it more secure way of transferring data from client to server in http protocol.

#### What's the difference between a POST and a PUT HTTP REQUEST?
> Difficulty : ⭐⭐

 An HTTP PUT is supposed to accept the body of the request, and then store that at the resource identified by the URI.

 An HTTP POST is more general. It is supposed to initiate an action on the server. That action could be to store the request body at the resource identified by the URI, or it could be a different URI, or it could be a different action.


#### What is REST API (RESTful API)?
> Difficulty : ⭐

A RESTful API is an architectural style for an application program interface (API) that uses HTTP requests to access and use data. That data can be used to GET, PUT, POST and DELETE data types, which refers to the reading, updating, creating and deleting of operations concerning resources.

#### What is REST?
> Difficulty : ⭐⭐

Representational state transfer (REST) is a software architectural style which uses a subset of HTTP. It is commonly used to create interactive applications that use Web services. A Web service that follows these guidelines is called RESTful. Such a Web service must provide its Web resources in a textual representation and allow them to be read and modified with a stateless protocol and a predefined set of operations. This approach allows interoperability between the computer systems on the Internet that provide these services. REST is an alternative to, for example, SOAP as way to access a Web service.

#### Describe JSON format?
> Difficulty : ⭐

When exchanging data between a browser and a server, the data can only be text. JSON is text, and we can convert any JavaScript object into JSON, and send JSON to the server.

#### What is AJAX?
> Difficulty : ⭐

**AJAX** stand for Asynchronous JavaScript And XML. Is a combination of:
-  A browser built-in XMLHttpRequest object (to request data from a web server)
-  JavaScript and HTML DOM (to display or use the data)
Example:
```javascript
function loadDoc() {
 var xhttp = new XMLHttpRequest();
    xhttp.onreadystatechange = function() {
        if (this.readyState == 4 && this.status == 200) {
        // Typical action to be performed when the document is ready:
        document.getElementById("demo").innerHTML = xhttp.responseText;
        }
    };
    xhttp.open("GET", "filename", true);
    xhttp.send();
}
```

You can also use **fetch** provides a more powerful and flexible feature set.
```javascript
function loadDoc() {
    fetch("url", {
        method: 'GET',
        header: {

        }
    })
    .then(response => {

    })
    .catch(err => {
        
    })
    
}
```

#### Explain CORS?
> Difficulty : ⭐⭐

Cross-Origin Resource Sharing (CORS) is an HTTP-header based mechanism that allows a server to indicate any other origins (domain, scheme, or port) than its own from which a browser should permit loading of resources. CORS also relies on a mechanism by which browsers make a “preflight” request to the server hosting the cross-origin resource, in order to check that the server will permit the actual request. In that preflight, the browser sends headers that indicate the HTTP method and headers that will be used in the actual request.

The CORS mechanism supports secure cross-origin requests and data transfers between browsers and servers. Modern browsers use CORS in APIs such as XMLHttpRequest or Fetch to mitigate the risks of cross-origin HTTP requests.

sd