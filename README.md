# Interview-Questions-and-Ans
******************************************************************************************************************************
******************************************************************************************************************************
Core Java                                                                           ******************************************
******************************************************************************************************************************
******************************************************************************************************************************
Difference between ArrayList and LinkedList
ArrayList uses a dynamic array and provides fast random access (O(1)), but insertion and deletion are slow due to shifting elements.
LinkedList uses a doubly linked list and allows faster insertion and deletion, but random access is slow (O(n)).
*****

HashMap vs ConcurrentHashMap
HashMap → ❌ Not thread-safe | ❌ Not synchronized | ✅ Allows 1 null key + multiple null values.
ConcurrentHashMap → ✅ Thread-safe | ❌ Not fully synchronized (uses internal locking) | ❌ No null key, no null value.
*****

HashMap vs Hashtable
HashMap → ❌ Not thread-safe | ❌ Not synchronized | ✅ Allows 1 null key & multiple null values
Hashtable → ✅ Thread-safe | ✅ Fully synchronized | ❌ No null key, no null value
*****

Abstract Class vs Interface
Abstract class → Can have constructor, instance variables, and abstract + non-abstract methods; supports single inheritance.
Interface → No constructor, methods are abstract by default (Java 8: default/static allowed); supports multiple inheritance.
*****

Why String is immutable?
For security, caching, and thread-safety.

String vs StringBuilder
String is immutable; StringBuilder is mutable & faster.

StringBuilder vs StringBuffer
StringBuilder is not thread-safe; StringBuffer is thread-safe.

*****
Checked Exception
Checked at compile time and mandatory to handle (IOException, SQLException, FileNotFoundException).

Unchecked Exception
Occurs at runtime and not mandatory to handle (NullPointerException, ArithmeticException, ArrayIndexOutOfBoundsException).

finally block
Always executes whether exception occurs or not (resource cleanup like file/DB close).
*****

Multithreading

Thread vs Runnable
Thread extends class; Runnable implements interface.

synchronized keyword
Allows only one thread at a time to access a resource.

Deadlock
Threads waiting for each other forever.
*****





******************************************************************************************************************************
******************************************************************************************************************************
Java 8                                                                              ******************************************
******************************************************************************************************************************
******************************************************************************************************************************
What are the features of Java 8?
Lambda Expressions, Stream API, Functional Interface, Default Methods, Optional Class, New Date and Time API.

What is a Lambda Expression?
Used to write anonymous functions and reduce boilerplate code.

What is a Functional Interface?
An interface with only one abstract method.

What is Stream API?
Used to process collections in a functional programming style.

What is Optional class?
Used to avoid NullPointerException.

What are Default Methods?
Methods with implementation inside an interface.

What is Method Reference?
A shorthand way to refer to a method using ::.

What is the new Date and Time API in Java 8?
An improved, immutable date-time API under java.time.

What is Parallel Stream?
Used to process data in parallel for better performance.

*****
Difference between map() and filter()
map() → Transforms each element and returns the same number of elements
filter() → Selects elements based on condition and may return fewer elements
map() → Used for data modification
filter() → Used for data selection
map() → Works with Function
filter() → Works with Predicate
*****



******************************************************************************************************************************
******************************************************************************************************************************
Spring Boot                                                                         ******************************************
******************************************************************************************************************************
******************************************************************************************************************************
What is @SpringBootApplication?
It is a combination of @Configuration, @EnableAutoConfiguration, and @ComponentScan.
*****

What is Dependency Injection (DI)?
Dependency Injection is a design principle where Spring provides required objects (dependencies) to a class instead of the class creating them itself.
This makes the code loosely coupled, easier to test, and easier to maintain

How Spring does DI
Using annotations like @Autowired, @Component, @Service, @Repository
*****

Difference between @Controller and @RestController
@Controller
Used for MVC web applications
Returns view names (JSP, Thymeleaf, HTML)
Needs @ResponseBody to return JSON
🧠 Used when UI pages are involved.

@RestController---@RestController = @Controller + @ResponseBody
Used for RESTful web services
Returns JSON/XML directly
@ResponseBody is not required
🧠 Used in microservices and APIs.
*****

ALL HTTP methods---
GET → Fetch data
POST → Create new data
PUT → Update entire data
PATCH → Update partial data
DELETE → Remove data
*****

What are the annotation we use in exception handling in spring boot?
@ExceptionHandler → Handles specific exceptions in a controller
@ControllerAdvice → Global exception handling for all controllers
@RestControllerAdvice → Global exception handling for REST APIs
@ResponseStatus → Defines HTTP status code for an exception
@ResponseBody → Returns exception response as JSON/XML
*****

What is Use of @Transactional annotation
Used to manage database transactions automatically
Ensures ACID properties (commit on success, rollback on failure)
If an exception occurs, transaction is rolled back automatically
*****
What is Actuator?
Provides health, metrics, and monitoring endpoints.

What is application.properties?
Used to configure application settings.

What is Spring Boot DevTools?
Provides auto-restart and faster development.

*****
Spring boot Annotaions---
@SpringBootApplication → Main annotation to start Spring Boot app

@Configuration → Defines configuration class

@EnableAutoConfiguration → Enables auto-configuration

@ComponentScan → Scans components in package

@Component → Marks a class as Spring bean

@Service → Business logic layer bean

@Repository → DAO layer and exception translation

@Autowired → Injects dependency automatically

@Qualifier → Resolves bean conflict

@Primary → Sets default bean

@Controller → MVC controller for views

@RestController → REST controller for APIs

@RequestMapping → Maps request to controller method

@GetMapping → Handles GET request

@PostMapping → Handles POST request

@PutMapping → Handles PUT request

@PatchMapping → Handles PATCH request

@DeleteMapping → Handles DELETE request

@RequestBody → Reads request body

@PathVariable → Reads URL path value

@RequestParam → Reads query parameter

@ExceptionHandler → Handles exceptions locally

@ControllerAdvice → Global exception handling

@RestControllerAdvice → Global REST exception handling

@Transactional → Manages database transactions

@Entity → Maps class to database table

@Id → Primary key

@GeneratedValue → Auto-generates ID

@Table → Maps entity to table

@Column → Maps field to column

@EnableScheduling → Enables scheduled tasks

@Scheduled → Runs method on schedule

*****











******************************************************************************************************************************
******************************************************************************************************************************
SQL                                                                                 ******************************************
******************************************************************************************************************************
******************************************************************************************************************************
What is Indexing in SQL?
Indexing in SQL is a way to speed up data retrieval from a database table—just like an index in a book helps you quickly find a topic without reading every page.
Instead of scanning the whole table row by row, the database uses an index to jump directly to the required data.
*****

What is a primary key?
A column (or combination) that uniquely identifies each row and does not allow NULL.
*****

What is a foreign key?
A key that links one table to another table’s primary key.
*****

Difference between UNIQUE and PRIMARY KEY
UNIQUE allows one NULL
PRIMARY KEY does not allow NULL
*****

What is a JOIN in SQL?
A JOIN is used to combine rows from two or more tables based on a related column (usually a primary key and foreign key).
**
Types of joins
INNER JOIN
LEFT JOIN
RIGHT JOIN
FULL JOIN
SELF JOIN
*****

What is Normalization in SQL?
Normalization is the process of organizing data in a database to reduce redundancy and improve data integrity by dividing data into smaller related tables.
*****

What is ACID Property?
ACID is a set of properties that ensure reliable and consistent database transactions.
ACID stands for:Atomicity, Consistency, Isolation, Durability

Atomicity
A transaction is all or nothing.
If any part fails, the entire transaction is rolled back.
🧠 Example: Money debit + credit must both succeed.

Consistency
A transaction moves the database from one valid state to another.
Database rules and constraints are always maintained.

Isolation
Multiple transactions run independently without affecting each other.
Intermediate data is not visible to other transactions.

Durability
Once a transaction is committed, it is permanently saved.
Data remains safe even after system failure.
*****











******************************************************************************************************************************
******************************************************************************************************************************
Microservices                                                                       ******************************************
******************************************************************************************************************************
******************************************************************************************************************************
What is Microservices Architecture?
An architecture where an application is split into small, independent services.

Monolithic vs Microservices?
Monolithic → single deployable unit; Microservices → independent services.

Advantages of Microservices?
Scalability, independent deployment, fault isolation.

Disadvantages of Microservices?
Complexity, network latency, monitoring difficulty

Synchronous vs Asynchronous communication?
Synchronous → waits for response; Asynchronous → event-based, non-blocking.
*****

How do Microservices communicate with each other?
Microservices communicate with each other using **REST APIs or gRPC** for synchronous communication.
They also use **message brokers like Kafka or RabbitMQ** for asynchronous, event-driven communication.
Service discovery and load balancers help services find and communicate with each other dynamically.
*****

Common Microservices Design Patterns (with explanation)
1️⃣ API Gateway Pattern
Acts as a single entry point for all client requests.
Handles authentication, routing, logging, and rate limiting.

2️⃣ Circuit Breaker Pattern 
The Circuit Breaker pattern is used to prevent a microservice from repeatedly calling another service that is failing.

How Circuit Breaker works (States)
1. Closed State
Requests flow normally
Failures are monitored
2. Open State
Failure threshold exceeded
Requests are blocked immediately
Fallback response is returned
3. Half-Open State
After some time, limited requests are allowed
If success → switch to Closed
If failure → back to Open

3️⃣Saga Pattern  
The Saga pattern is used to manage distributed transactions across multiple microservices.
Saga pattern maintains data consistency by using compensating transactions instead of rollback.

Why Saga Pattern is needed?
No shared database
No global rollback
Each service commits independently
Saga ensures data consistency using compensating transactions.

How Saga works
Each step:
Executes a local transaction
Publishes an event
Next service continues the flow
If a step fails:
Previously completed steps are undone using compensating actions

Real-life Example
Order → Payment → Inventory → Shipping
If Payment fails:
Order is cancelled
Inventory reservation is rolled back

4️⃣ Service Discovery Pattern
Automatically finds service instances at runtime.
Avoids hardcoding service URLs.

5️⃣ Database per Service Pattern
Each microservice has its own database.
Prevents tight coupling between services.

6️⃣ Event-Driven Pattern
Services communicate using events via message brokers.
Supports asynchronous and loosely coupled systems.


******************************************************************************************************************************
******************************************************************************************************************************
Angular                                                                             ******************************************
******************************************************************************************************************************
******************************************************************************************************************************

Angular updated 


