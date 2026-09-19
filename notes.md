# FAST API

## HTTP Request Methods

### HTTP defines a set of request methods to indicate the purpose of the request and what is expected if the request is successful. Although they can also be nouns, these request methods are sometimes referred to as HTTP verbs. Each request method has its own semantics, but some characteristics are shared across multiple methods, specifically request methods can be safe, idempotent, or cacheable.

- Get(`GET`) - Used to retrieve data from the server.
- Post(`POST`) - Used to send data to the server to create a new resource.
- Head(`HEAD`) - Similar to GET, but it only retrieves the headers and not the body of the response.
- Put(`PUT`) - Used to update an existing resource on the server.
- Delete(`DELETE`) - Used to delete an existing resource from the server.
- Connect(`CONNECT`) - Used to establish a network connection  from client to the server.
- Options(`OPTIONS`) - Used to retrieve the supported HTTP methods and other options for a resource.
- TRACE(`TRACE`) - Used to perform a diagnostic trace of the request-response chain.
- PATCH(`PATCH`) - Used to apply partial modifications to a resource.
- `https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Methods`

## CRUD Operations
- C- Create - Create a new resource on the server. (POST)
- R- Read - Retrieve data from the server. (GET)
- U- Update - Modify an existing resource on the server. (PUT/PATCH)
- D- Delete - Remove an existing resource from the server. (DELETE)


#### Status Codes
- Status codes are three-digit numbers returned by the server in response to an HTTP request. They indicate the outcome of the request and provide information about the status of the requested resource. 

##### Status codes are grouped into five categories based on their first digit:
- 1xx (Informational): The request was received, and the server is continuing to process it.
- 2xx (Successful): The request was successfully received, understood, and accepted.
- 3xx (Redirection): The request requires further action to be completed.
- 4xx (Client Error): The request contains bad syntax or cannot be fulfilled.
- 5xx (Server Error): The server failed to fulfill an apparently valid request. 
- `https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Status`

#### Payload 
-  payload refers to the actual data transmitted in the body of a request or response.
- in the context of HTTP requests, the payload is the data sent by the client to the server in a POST or   PUT request, or the data sent by the server to the client in a response.

### Database
- database is an organized collection of structured information, or data, stored  in a computer system. A database is usually controlled by a database management system (DBMS). Together, the data and the DBMS, along with the applications that are associated with them, are referred to as a database system, often shortened to just database.

### Database Management System (DBMS)
- A database management system (DBMS) is a software application that interacts with the user, other applications, and the database itself to capture and analyze data. A general-purpose DBMS is designed to allow the definition, creation, querying, update, and administration of databases.


## Postgres
- is a free and open source system used to store,manage and retrieve data. It is a relational database management system (RDBMS) that uses and extends the SQL language combined with many features that safely store and scale the most complicated data workloads.

### Postgres Datatypes
- Numeric - Numeric data types are used to store numeric values, such as integers and floating-point numbers. Examples include INTEGER, BIGINT, DECIMAL, NUMERIC, REAL, and DOUBLE PRECISION.
- Character - Character data types are used to store text or string values. Examples include CHAR, VARCHAR, and TEXT.
- Date/Time - Date/Time data types are used to store date and time values.  
- Sequence - Sequence data types are used to generate unique numeric values, often used for primary keys. Examples include SERIAL and BIGSERIAL.
- Boolean - Boolean data types are used to store true/false values. The BOOLEAN data type can have the values TRUE, FALSE, or NULL.


## Primary Key
- A primary key is a unique identifier for a record in a database table. It ensures that each record can be uniquely identified and accessed. A primary key must contain unique values and cannot contain NULL values. Each table can have only one primary key, which may consist of single or multiple columns.

#### unique constraint
- A unique constraint is a database constraint that ensures that the values in a specific column or combination of columns are unique across all rows in a table. It prevents duplicate values from being inserted into the specified column(s) and helps maintain data integrity.

#### Null Constraint
- A null constraint is a database constraint that specifies whether a column can accept NULL values or not.
#### Not Null Constraint
- A not null constraint is a database constraint that specifies that a column cannot accept NULL values.


### Psycopg
- Psycopg is a popular PostgreSQL database adapter for the Python programming language. It provides a way for Python applications to interact with PostgreSQL databases, allowing developers to execute SQL queries, manage transactions, and retrieve data from the database.
- In other words, psycopg converts only postgres datbase to python or fastapi.

## ORM
- ORM (Object-Relational Mapping/Mapper) is a programming technique that allows developers to interact with a relational database using object-oriented programming concepts. It provides a way to map database tables to classes and database records to objects, allowing developers to work with data in a more intuitive and abstract manner.

### What can ORM do?
- ORM allows developers to work with databases using high-level programming languages, such as Python, instead of writing raw SQL queries. It provides an abstraction layer that simplifies database operations and allows developers to focus on the application logic rather than the underlying database implementation.
- Queries can be made exclusively through python code. No SQL is required. The ORM will handle the translation of the python code into SQL queries and execute them against the database.


## SQLALCHEMY

- Sqlalchemy is one of the most popular python ORMs
- It is a standalone library and has no association with FastAPI. It can be used with any other python web frameworks or any python based application
- `https://www.sqlalchemy.org/`


## synchronize_session
- The synchronize_session parameter in FastAPI (via SQLAlchemy) controls how an in-memory ORM session updates its local cache after executing a bulk update() or delete() query directly on the database. 

## Schema Models
- Schema/pydantic models define the structure of a request and response 
- this ensure that when a user wants to create a post, the request will only go through if it has a "title" a "content" in the body

## sqlalchemy models
- responsible for defining the columns of our "posts" table within postgres
- is used to query,create,delete and update entries within the database 