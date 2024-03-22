# OpenAPI

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

## 2. Defining a microservice with OpenAPI 
![Structure of OpenAPI 3.0](openapi3structure.png)
### Info
- Cung cấp metadata về API
- Trường title và version là bắt buộc
- Ví dụ:
    ```
    info:
        version: 1.o
        title: OpenAPI Course
    ```
- [Thông tin thêm về Info Object](https://github.com/OAI/OpenAPI-Specification/blob/main/versions/3.1.0.md#info-object)

### Servers
- Cung cấp thông tin đến server đích
- Là một object không bắt buộc
- Có thể thêm tùy ý số lượng servers
- Ví dụ: 
    ```
    severs
    -   url: <link>
        description: <something>
    ```
- [Thông tin thêm về Sever Object](https://github.com/OAI/OpenAPI-Specification/blob/main/versions/3.1.0.md#server-object)

## Path
- Tập hợp các operation
- Ví dụ:
    ```
    path:
        v1/x:
            get:
                responses:
                    '200':
                        description: OK
    ```
- [Thông tin thêm về Path Object](https://github.com/OAI/OpenAPI-Specification/blob/main/versions/3.1.0.md#paths-object)

## 3. Define HTTP verbs
## GET

```
get:
   parameters:
   summary:
   description:
   tags:
   operationId:
   response:
      '201':
         description:
         content:
            application/json:
               schema: <define schema>
      
```

## POST and PUT
```
post:
   parameters:
   summary:
   description:
   tags:
   operationId:
   requestBody:
      required:true
      content:
         application/json:
            schema: <define schema>
   response:
      '201':
         description:
         content:
            application/json:
               schema: <define schema>
```

## Delete:
```
delete:
   parameters:
   summary:
   description:
   tags:
   operationId:
   response:
      '201':
         description:
         content:
            application/json:
               schema: <define schema>
```
