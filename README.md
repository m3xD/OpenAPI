# OpenAPI and GRPC

## 1. Overview of OpenAPI
### API: Application Programming Interface
- It's a method for 2 computer applications to speak each other.
- Focus on RESTful Webservice.
### RESTful Web service
- Representation: XML or JSON.
- Stateless (HTTP).
- Verb - HTTP Methods: GET, PUT, POST, DELETE.
- Terminology: 
    * Idempotence: apply method multiple times without changing a result.
- Methods:
    * GET: Read data
        * Idempotent
        * Safe operation
    * PUT : Insert (if not found) or update (if exits)
        * Idempotent (update multiple time will not effect result)
        * Not safe operation
    * POST: Insert new object
        * Non-Idempotent
        * Not safe operation
    * DELETE: Delete an object
        * Idempotent
        * Not safe operation
- HTTP Status codes:
    * 100 series are informational in nature
    * 200 series indicate successful request
    * 300 series are redirection
    * 400 series are client errors
    * 500 series are sever errors