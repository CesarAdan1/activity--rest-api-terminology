# REST API Terminology 

Fork and clone this repository. Then, push to github with all bad answers deleted and only the correct answers showing.

**1. What does it mean REST?**
Representational State Transfer

**2. Who coined the REST term?**
Roy Fielding

**3. In which protocol REST is based?**
Hypertext Transfer Protocol(HTTP)

/*RESOURCE = El concepto que se consume de la API*/

**4. What are the main building blocks of a REST Architecture?**
Resource — url in REST APIs.
Representations — Representation is the value/response of the Resource at a point in time based on the media-type.
Self Descriptive Messages — When server returns resource representation to the client then server should tell the client how to process the representation.
Hypermedia as the engine of application state —It means, once a client have initial response, then response should contains hyper links which allows a client to move to the next state of the application.

**5. Identifying a resource is easy; you know how to access it and you even know how to request for a specific format. Since REST is using HTTP protocol as a standing point, there are some actions related to resources: CRUD operations.**
GET---CONSULTAS
POST--ENVIAR NUEVO RESOURCE AL SERVIDOR(CREAR ALGO DESDE CERO)
PUT--CREAR ALGO(ACTUALIZAR)
DELETE--BORRAR UN DATO

Complete the below table:


|HTTP Verb|Proposed Action|
|---------|---------------| respuesta: ----
|GET| Write it here. |  COMUN ERROR: 201
|POST| Write it here. | COMUN ERROR: 201
|PUT| Write it here. | ERROR COMUN:  
|DELETE| Write it here. | ERROR COMUN : 404, 204, responder al body sin contenido.

301-- LA API TIENE OTRA UBICACIÓN
**6. Status Code**

Another interesting standard that REST can benefit from when based on HTTP is the usage of HTTP status codes.

+ What’s is a status code?

+ Explain with your own words, the meaning of next codes:

|Status Code|Description|
|-----------|-----------|
|404| It means that a request source was not found. |
401 -- The request was not authorized
|200| Todo funciona normal. |
|500| An error on the server was an unrecoverable application. |

**7. Status Code are grouped in five sets.**

Write what are their meaning.

|Group|Description|
|-----|-----------|
|1XX| (Informational): The request was received, continuing process. |
|2XX| (Successful): The request was successfully received, understood, and accepted. |
|3XX| (Redirection): Further action needs to be taken in order to complete the request. |
|4XX| (Client Error): The request contains bad syntax or cannot be fulfilled. |
|5XX| (Server Error): The server failed to fulfill an apparently valid request. |

**8. HTTP Status Codes and Their Related Interpretation**

There are the most common status codes in HTTP responses. Please, fill with the required description.

|Status Code|Meaning|
|-----------|-------|
|200| OK ----Successful |
|201| CREATED |
|204| NO CONTENT |
|301| MOVED PERMANENTLY |
|400| BAD REQUEST |
|401| UNAUTHORIZED | ERROR DE AUTENTICACIÓN
|403| FORBIDDEN | NO TIENES PERMISO
|404| NOT FOUND | HACEMOS UNA PETICIÓN AL ENDPOINT NO EXISTE
|405| METHOD NOT ALLOWED |
|500| INTERNAL SERVER ERROR | NO SE PUEDE CONTROLAR, CUANTO SE CAE UN SITIO, LO HACKEAN, SE CAE EL SERVIDOR. RESPONDER CON UN 500 PARA MOSTRAR AL USUARIO QUE SE CAYO EL SERVIDOR.

###### [To see the full list of HTTP status codes and their meaning, please refer to the RFC of HTTP 1.1](http://tools.ietf.org/html/rfc7231#section-6)

**9. How are called the points of contact between all client apps and the API?**
ENDPOINT 

**10. The following is a good example or bad example of a named access point? And why?**

_meant to list the books in a bookstore_
bad: because Iwe don't know what action1 is.

+ `GET /books/action1`

**11. Uniform Interface**

Easy-to-remember access points are important, but so is being consistent when defining them.

You have to “refactor” the next bad design of an API. **It’s not  a good practice to name the endpoints based on the actions taken instead of the resource handled.**

At a first glance, the might not seem that bad, but consider how poor the interface is going to become as new features and resources are added to the system. Each new addition to the system causes extra endpoints to the API’s interface.

To solve this problem, you can apply the REST style to the endpoints, and thanks to HTTP, you also have verbs to indicate actions.

|Old Style|REST Style| //Se optimizan los recursos
|---------|----------|
|`/getAllBooks`| GET /books |
|`/submitNewBook`| POST /books |
|`/updateAuthor`| PUT /authors/:id |
|`/getBooksAuthors`| GET /books/:id/authors| //primero se obtiene el libro y los autores de los libros en específico.
|`/getNumberOfBooksOnStock`| GET /books/| //se puede mandar la longitud del array.
|`/addNewImageToBook`| PUT /books/:id/cover| o /images
|`/getBooksImages`| GET /books/:id/images  |
|`/addCoverImage`| POST /books/:id/cover |  //crear un nuevo registro
|`/listBookCovers`| GET /books/:id | 

**12. What JSON does it mean?**
JavaScript Object Notation
Lenguaje para comunicarnos con los datos (responder y obtener datos).

Datos I/O == Manipulación de datos
**13. Anatomy of a `REQUEST`**

Make a `curl` request to _GitHub API_
request()
```sh
$ curl -X GET https://api.github.com
```

According to the responded request, answer what does it mean the next parts from the handler:

+ _`Content-Type`_. _Describes the content type for the message body
+ _`Status`_. _Status code
+ _`Date`_. _Contain the date and time at which the message was originated
+ _`Content-Length`_. _Indicates the size of the entity-body in bytes.


###### If response is not showing those parts, ask to google how to print them in console.

```sh
#  curl -i GET https://api.github.com
```
