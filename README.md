# 📘 Interview Questions and Answers – Java Full Stack

A complete interview preparation repository covering **Core Java, Java 8, Spring Boot, Spring Security, SQL, Microservices, Unit Testing, Angular basics, and Real Project Discussion**.

---

## 📌 Table of Contents
1. Core Java  
2. Java 8  
3. Spring Boot  
4. Spring Security  
5. Unit Testing  
6. SQL  
7. Microservices  
8. Project Overview – Airline Employee Benefits System  
9. Mercedes 2nd Round Interview Questions  

---

## 🔹 Core Java

### Difference between ArrayList and LinkedList
**ArrayList**
- Uses dynamic array
- Fast random access → `O(1)`
- Slow insertion/deletion due to shifting

**LinkedList**
- Uses doubly linked list
- Slow random access → `O(n)`
- Faster insertion/deletion

---

### HashMap vs ConcurrentHashMap
**HashMap**
- ❌ Not thread-safe
- ❌ Not synchronized
- ✅ Allows 1 null key & multiple null values

**ConcurrentHashMap**
- ✅ Thread-safe
- ❌ Not fully synchronized (internal locking)
- ❌ No null key, no null value

---

### HashMap vs Hashtable
**HashMap**
- ❌ Not thread-safe
- ✅ Allows null key & values

**Hashtable**
- ✅ Thread-safe
- ❌ No null key, no null value

---

### Abstract Class vs Interface
**Abstract Class**
- Can have constructor
- Can have instance variables
- Abstract + non-abstract methods
- Supports single inheritance

**Interface**
- No constructor
- Java 8 supports default & static methods
- Supports multiple inheritance

---

### Why String is Immutable?
- Security
- Caching
- Thread-safety

---

### String vs StringBuilder vs StringBuffer
- **String** → Immutable  
- **StringBuilder** → Mutable, faster, not thread-safe  
- **StringBuffer** → Mutable, thread-safe  

---

### Checked vs Unchecked Exception
**Checked Exception**
- Checked at compile time
- Mandatory to handle  
- Example: `IOException`, `SQLException`

**Unchecked Exception**
- Occurs at runtime
- Not mandatory to handle  
- Example: `NullPointerException`, `ArithmeticException`

---

### finally Block
- Always executes
- Used for resource cleanup (DB, file close)

---

### Multithreading

**Thread vs Runnable**
- Thread → extends class
- Runnable → implements interface (preferred)

**synchronized**
- Allows only one thread at a time to access resource

**Deadlock**
- Threads wait forever for each other

---

## 🔹 Java 8

### Features of Java 8
- Lambda Expressions
- Stream API
- Functional Interface
- Default Methods
- Optional Class
- Date & Time API

---

### Lambda Expression
- Used to write anonymous functions
- Reduces boilerplate code

---

### Functional Interface
- Interface with only one abstract method

---

### Stream API
- Processes collections in functional style

---

### Optional Class
- Avoids `NullPointerException`

---

### Default Methods
- Methods with implementation inside interface

---

### Method Reference
- Shorthand using `::`

---

### Date & Time API
- Immutable API under `java.time`

---

### Parallel Stream
- Processes data in parallel

---

### map() vs filter()
| map() | filter() |
|-----|--------|
| Transforms data | Filters data |
| Same size output | Reduced output |
| Uses Function | Uses Predicate |

---

## 🔹 Spring Boot

### @SpringBootApplication
Combination of:
- `@Configuration`
- `@EnableAutoConfiguration`
- `@ComponentScan`

---

### Dependency Injection (DI)
Spring provides dependencies instead of creating them manually.
- Loose coupling
- Easy testing
- Easy maintenance

---

### @Controller vs @RestController
**@Controller**
- Used for MVC
- Returns views
- Needs `@ResponseBody` for JSON

**@RestController**
- Used for REST APIs
- Returns JSON/XML directly

---

### HTTP Methods
- GET → Fetch data  
- POST → Create  
- PUT → Update entire data  
- PATCH → Partial update  
- DELETE → Remove  

---

### Exception Handling Annotations
- `@ExceptionHandler`
- `@ControllerAdvice`
- `@RestControllerAdvice`
- `@ResponseStatus`

---

### Important HTTP Status Codes
- 200 OK
- 201 Created
- 400 Bad Request
- 401 Unauthorized
- 404 Not Found

---

### @Transactional
- Manages DB transactions
- Ensures ACID properties
- Auto rollback on exception

---

### Actuator
- Health, metrics, monitoring endpoints

---

### application.properties
- Configuration file

---

### Spring Boot DevTools
- Auto restart
- Faster development

---

## 🔹 Spring Security

### Authentication vs Authorization
- Authentication → Who you are
- Authorization → What you can access

---

### JWT Parts
1. Header
2. Payload
3. Signature

---

### Password Encoding
- Converts password into secure hash

---

### CSRF
- Attack using authenticated browser
- Disabled in JWT (stateless)

---

### OAuth2
- Authorization framework
- Secure third-party access

---

### JWT Flow
- Token generated after login
- Sent with every request
- Server validates token

---

### Access Token & Refresh Token
- Access Token → Short-lived
- Refresh Token → Generates new access token
- Prevents frequent logout

---

### Stateful vs Stateless Authentication
| Stateful | Stateless |
|-------|----------|
| Server stores session | No session stored |
| Session ID | JWT |
| Hard to scale | Easy to scale |

---

## 🔹 Unit Testing

### Unit Testing in Spring Boot
- Tests individual components
- No full context loading

---

### Tools Used
- JUnit
- Mockito

---

### Benefits
- Early bug detection
- Better code quality
- Faster development

---

### JUnit Annotations
- `@Test`
- `@BeforeEach`
- `@AfterEach`
- `@BeforeAll`
- `@AfterAll`
- `@Disabled`

---

### Mockito vs JUnit
**JUnit**
- Runs test cases
- Assertions & execution

**Mockito**
- Mocks dependencies
- Isolates testing

---

## 🔹 SQL

### Indexing
- Improves query speed
- Avoids full table scan

---

### Keys
- Primary Key → Unique, no NULL
- Foreign Key → Reference to another table

---

### UNIQUE vs PRIMARY KEY
- UNIQUE → Allows NULL
- PRIMARY KEY → No NULL

---

### JOIN
Combines rows from multiple tables.

Types:
- INNER
- LEFT
- RIGHT
- FULL
- SELF

---

### Normalization
- Reduces redundancy
- Improves data integrity

---

### ACID Properties
- Atomicity
- Consistency
- Isolation
- Durability

---

## 🔹 Microservices

### What is Microservices Architecture?
Application split into small independent services.

---

### Monolithic vs Microservices
- Monolithic → Single deployable unit
- Microservices → Independent services

---

### Advantages
- Scalability
- Independent deployment
- Fault isolation

---

### Disadvantages
- Complexity
- Network latency
- Monitoring difficulty

---

### Communication
- REST / gRPC (Synchronous)
- Kafka / RabbitMQ (Asynchronous)

---

### Design Patterns
- API Gateway
- Circuit Breaker
- Saga Pattern
- Service Discovery
- Database per Service
- Event Driven Architecture

---

## 🔹 Project – Airline Employee Benefits Management System

### Project Overview
Enterprise web application for airline HR teams to manage employee benefits, dependents, documents, and payments.

---

### Tech Stack
- Java 8
- Spring Boot
- Hibernate
- MySQL
- Spring Security (JWT, OAuth2)
- AWS S3
- Stripe
- Angular
- Docker & CI/CD

---

### Team Size
- 3 Backend Developers
- 2 Frontend Developers
- 2 QA Engineers
- 1 DevOps Engineer

---

### Duration – 3 Years
- Year 1: MVP development
- Year 2–3: Enhancements, security, payments, performance, production support

---

### Microservices
- 10–12 microservices
- ~90–120 APIs

---

### My Role
- Backend / Full Stack Developer
- REST APIs
- Security (JWT)
- Stripe integration
- AWS S3
- Production support

---

## 🔹 Mercedes – 2nd Round Interview Questions

### Arrays
- Fast access using index
- Continuous memory allocation
- `O(1)` access time

---

### ArrayList – Dynamic Nature
- Uses internal array
- Resizes when full
- GC removes unused arrays

---

### Set
- Stores unique values
- HashSet → No order
- LinkedHashSet → Insertion order
- TreeSet → Sorted

---

### Hash Collision
- Limited hashCode range
- Multiple keys can map to same bucket
- Too many collisions degrade performance

---

### OAuth2 with Spring Security
- Spring Boot as Resource Server
- Cognito as Authorization Server
- JWT validation
- Role-based access

---

### JWT Limitations
- Contains limited data
- Extra data fetched from DB or UserInfo endpoint

---

## ✅ Author
**Manas Kashyap**  
Java | Spring Boot | Microservices | Full Stack Developer
