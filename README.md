# REST API Terminology 

Fork and clone this repository. Then, push to github with all bad answers deleted and only the correct answers showing.

**1. What does it mean REST?**
 Representational State Transfer

**2. Who coined the REST term?**
	Roy Fielding

**3. In which protocol REST is based?**
	Protocolo HTTP
 


**4. What are the main building blocks of a REST Architecture?**

	Resources (URI, which goes after the slash in the endpoint of an API)

**5. Identifying a resource is easy; you know how to access it and you even know how to request for a specific format. Since REST is using HTTP protocol as a standing point, there are some actions related to resources: CRUD operations.**

Complete the below table:


|HTTP Verb|Proposed Action|
|---------|---------------|
|GET| solicita consultar a los recursos. |
|POST| Inserta nuevos recursos. |
|PUT| Actualiza recursos |
|DELETE| Borra recursos |

**6. Status Code**

Another interesting standard that REST can benefit from when based on HTTP is the usage of HTTP status codes.

+ What’s is a status code?

+ Explain with your own words, the meaning of next codes:

|Status Code|Description|
|-----------|-----------|
|404| es un error que nos indica que la página no se existe en el servidor |
|200| Nos indica que la petición asido exitosa. |
|500|Error del lado del servidor al intentar crear el recurso, |

**7. Status Code are grouped in five sets.**

Write what are their meaning.

|Group|Description|
|-----|-----------|
|1XX| Petición recibida. |
|2XX| Indican que la carga ha ido bien. |
|3XX| Indican una redirección |
|4XX| Se refieren a errores de cliente |
|5XX| Se refiere a los errores del servidor. |

**8. HTTP Status Codes and Their Related Interpretation**

There are the most common status codes in HTTP responses. Please, fill with the required description.

|Status Code|Meaning|
|-----------|-------|
|200| Respuesta estándar para peticiones correctas. |
|201| La petición ha sido completada y ha resultado en la creación de un nuevo recurso. |
|204|La petición se ha completado con éxito pero su respuesta no tiene ningún contenido |
|301| Esta y todas las peticiones futuras deberían ser dirigidas a la URI dada |
|400| La solicitud contiene sintaxis errónea y no debería repetirse.|
|401| cuando la autentificación es posible pero ha fallado o aún no ha sido provista.|
|403| el servidor rehúsa responderla dado que el cliente no tiene los privilegios para hacerla. |
|404| el servidor web no encuentra la página o recurso solicitado |
|405| Una petición fue hecha a una URI utilizando un método de solicitud no soportado por dicha URI. |
|500| Error del lado del servidor al intentar crear el recurso. |

###### [To see the full list of HTTP status codes and their meaning, please refer to the RFC of HTTP 1.1](http://tools.ietf.org/html/rfc7231#section-6)

**9. How are called the points of contact between all client apps and the API?**

Enpoind

**10. The following is a good example or bad example of a named access point? And why?**

_meant to list the books in a bookstore_

+ `GET /books/action1`

Esta Mal, porque no sabemos que es la action1
**11. Uniform Interface**

Easy-to-remember access points are important, but so is being consistent when defining them.

You have to “refactor” the next bad design of an API. **It’s not  a good practice to name the endpoints based on the actions taken instead of the resource handled.**

At a first glance, the might not seem that bad, but consider how poor the interface is going to become as new features and resources are added to the system. Each new addition to the system causes extra endpoints to the API’s interface.

To solve this problem, you can apply the REST style to the endpoints, and thanks to HTTP, you also have verbs to indicate actions.

|Old Style|REST Style|
|---------|----------|
|`/getAllBooks`|GET/books|
|`/submitNewBook`| POST/books |
|`/updateAuthor`| PUT/autor/:id |
|`/getBooksAuthors`| GET /books/:id/authors|
|`/getNumberOfBooksOnStock`| GET /books |
|`/addNewImageToBook`| PUT /books/:id/cover |
|`/getBooksImages`| GET /books/:id/cover |
|`/addCoverImage`| POST /books/:id/cover_image |
|`/listBookCovers`| GET /books/:id |

**12. What JSON does it mean?**

	Javascript Object Notation

**13. Anatomy of a `REQUEST`**

Make a `curl` request to _GitHub API_

```sh
$ curl -X GET https://api.github.com
```

According to the responded request, answer what does it mean the next parts from the handler:

+ _`Content-Type`_. _Tipo de Media_
+ _`Status`_. Status Code
+ _`Date`_. _Contiene la fecha y hora en la que genera un mensaje
+ _`Content-Length`_. _Indica el tamaño de bytes.


###### If response is not showing those parts, ask to google how to print them in console.

curl -i GET https://api.github.com
