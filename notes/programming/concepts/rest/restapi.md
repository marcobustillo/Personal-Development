# REST
What is REST?
**REST, or REpresentational State Transfer**, is an architectural style for providing standards between computer systems on the web, making it easier for systems to communicate with each other. REST-compliant systems, often called RESTful systems, are characterized by how they are stateless and separate the concerns of client and server. We will go into what these terms mean and why they are beneficial characteristics for services on the Web.

## Communication Between Client and Server
**In the REST architecture**, clients send requests to retrieve or modify resources, and servers send responses to these requests. Let’s take a look at the standard ways to make requests and send responses.

### Making Requests
**REST** needs the client to make a request to the server in order to retrieve, modify data on the server.
**REQUEST** generally consists of the following:
- An HTTP verb, which defines what kind of operation to perform
- A Header, which allows the client to pass along information about the request
- A path to a resource(generally this is the link)
- A body.

#### HTTP Verbs
There 4 basic HTTP verbs in REST.
- **GET**: retrieve a specific resource by id or collection of resource.
- **POST**: create a new resource
- **PUT**: update a specific resource(by id)
- **DELETE**: remove a specific resource(by id)

## Response Codes
Reponses alert the client about the information of the request

Status Code | Meaning
200 (OK)	| This is the standard response for successful HTTP requests.
201 (CREATED)	| This is the standard response for an HTTP request that resulted in an item being successfully created.
204 (NO CONTENT) | This is the standard response for successful HTTP requests, where nothing is being returned in the response body.
400 (BAD REQUEST) | The request cannot be processed because of bad request syntax, excessive size, or another client error.
403 (FORBIDDEN) | The client does not have permission to access this resource.
404 (NOT FOUND) | The resource could not be found at this time. It is possible it was deleted, or does not exist yet.
500 (INTERNAL SERVER ERROR) | The generic answer for an unexpected failure if there is no more specific information available.

For each HTTP Verbs, there are expected status codes a server should return upon success:
- **GET**: return 200(OK)
- **POST**: return 201(CREATED)
- **PUT**: return 200(OK)
- **DELETE**: return 204 (NO CONTENT) If the operation fails, return the most specific status code possible corresponding to the problem that was encountered.

## Examples of Requests and Responses
### GET
- Get all Users
```javascript
GET http://www.sampleserver.com/api/getusers
Accept: application/json
```
A possible header would look like
```javscript
Status Code: 200(OK)
Content-type: application/json
```

- Get Specific User
```javascript
GET http://www.sampleserver.com/api/getusers?userid=bob&age=10
Accept: application/json
```
A possible header would look like
```javscript
Status Code: 200(OK)
Content-type: application/json
```

### POST
- Create a new user
```javascript
POST http://www.sampleserver.com/api/createuser
Body:{
  "user":{
    "name":"you",
    "age":"20"
  }
}
```
The server then generates an id for that object and returns it back to the client, with a header like:
```javascript
201 (CREATED)
Content-type: application/json
```

### PUT
```javascript
PUT http://www.sampleserver.com/api/updateuser/1
Body:{
  "user":{
    "name":"you",
    "age":"21"
  }
}
```
A possible response header would have Status Code: 200 (OK), to notify the client that the item with id 1 has been modified.

### DELETE
```javascript
DELETE http://www.sampleserver.com/api/deleteuser/1
```
The response would have a header containing Status Code: 204 (NO CONTENT), notifying the client that the item with id 1 has been deleted, and nothing in the body.

## Practice REST
To create a successful REST API server we need to follow these steps:
- what kinds of request we would want to make
- what kind of responses should the server return
- what kind of content type of each responses should be
- what kind of model should we pass and receive

### Possible Models
Model we would pass
```javascript
  {
    "user":{
      "id":<Integer>,
      "username":<String>,
      "password":<String>
    }
  }
```

Model we will receive
```javascript
{
  "data":{
    token:"29jaijf9u8234mkamdasd"
  }
}
```

### Possible Requests/Reponses
- **GET**
  Request | Accept | Response | Content-type
  GET /index.html | Accept: text/html | Response - 200(OK)
  Request- GET /style.css | Accept: text/css | Response- 200 (OK) | Content-type: text/css
  Request- GET /users | Accept:application/json | Response- 200 (OK) | Content-type: application/json
  Request- GET /users/:id | Accept: application/json | Response- 200 (OK) | Content-type: application/json
  Request- GET /users/:id/photos/:id | Accept: application/json | Response- 200 (OK) | Content-type: image/png
- **POST**
  Request | Response | Content-type
  Request- POST /users | Response- 201 (CREATED) | Content-type: application/json
  Request- POST /users | Response- 201 (CREATED) | Content-type: application/json
  Request- POST /users/:id/photos | Response- 201 (CREATED) | Content-type: application/json
- **PUT**
  Request | Response
  Request- PUT /users/:id | Response- 200 (OK)
  Request- PUT /users/:id | Response- 200 (OK)
  Request- PUT /users/:id/photos/:id | Response- 200 (OK)
- **DELETE**
  Request | Response
  Request- DELETE /users/:id | Response- 204 (NO CONTENT)
  Request- DELETE /users/:id/photos/:id | Response- 204 (NO CONTENT)
