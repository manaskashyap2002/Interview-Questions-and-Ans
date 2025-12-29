# Interview-Questions-and-Ans

## Core Java  
### Difference between ArrayList and LinkedList
**ArrayList** uses a dynamic array and provides fast random access (O(1)), but insertion and deletion are slow due to shifting elements.

**LinkedList** uses a doubly linked list and allows faster insertion and deletion, but random access is slow (O(n)).

### HashMap vs ConcurrentHashMap
**HashMap**→ ❌ Not thread-safe ❌ Not synchronized | ✅ Allows 1 null key + multiple null values.

**ConcurrentHashMap** → ✅ Thread-safe | ❌ Not fully synchronized (uses internal locking) | ❌ No null key, no null value.

### HashMap vs Hashtable
**HashMap** → ❌ Not thread-safe | ❌ Not synchronized | ✅ Allows 1 null key & multiple null values
**Hashtable** → ✅ Thread-safe | ✅ Fully synchronized | ❌ No null key, no null value

### Abstract Class vs Interface
**Abstract class** → Can have constructor, instance variables, and abstract + non-abstract methods; supports single inheritance.
**Interface** → No constructor, methods are abstract by default (Java 8: default/static allowed); supports multiple inheritance.

### Why String is immutable?
For security, caching, and thread-safety.

### String vs StringBuilder
String is immutable; StringBuilder is mutable & faster.

## StringBuilder vs StringBuffer
- StringBuilder is not thread-safe;
- StringBuffer is thread-safe.

### Checked Exception
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

Q.Important HTTP Response Status Codes
200 OK
201 Created
400 Bad Request
401 Unauthorized
404 Not Found
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

****************
Spring Security
****************
Q. What is Authentication?
Authentication verifies who the user is (username and password validation).
Q. What is Authorization?
 Authorization checks what the user is allowed to access (roles and permissions).
*****

Q. What are the main parts of JWT (JSON Web Token)
Header::---Contains information about the token type and the algorithm used to sign the token.
Payload::---Contains the user data and claims like user id, role, and token expiry.
Signature::---Used to verify that the token is authentic and has not been tampered with.
*****

What is Password Encoding?
Password encoding converts passwords into a secure hashed format to protect user credentials.
*****

What is CSRF (Cross-Site Request Forgery)?
CSRF is a security attack where a hacker forces a logged-in user’s browser to send a request to a trusted website without the user’s knowledge.
Because the user is already authenticated, the server trusts the request and executes it.
*****

Q.Why CSRF is disabled in JWT?
JWT is stateless and does not rely on cookies, so CSRF protection is not required.
*****

Q. What is OAuth2?
OAuth2 is an authorization framework that allows secure third-party access without sharing credentials.
*****

Q. How JWT works?
JWT works by generating a signed token after successful authentication.
The client sends this token with every request.
The server validates the token instead of using sessions.
This makes authentication stateless and scalable.
*****


Q:In a banking application, JWT expiry time is 10 minutes. If the token expires, the user gets logged out. Is there any way to avoid this and keep the user logged in without re-login?
Answer:
Yes. We use Access Token and Refresh Token.
The access token is short-lived (10 minutes). When it is about to expire, a new access token is generated using the refresh token. This extends the session automatically without logging the user out.
*****

Stateful vs Stateless Authentication – 3 Main Differences
1️⃣ Session Storage
Stateful: Server stores user session
Stateless: Server does not store session

2️⃣ Authentication Method
Stateful: Uses session ID
Stateless: Uses token (JWT)

3️⃣ Scalability
Stateful: Hard to scale
Stateless: Easy to scale
******




****************
Unit Testing
****************
What is Unit Testing in Spring Boot?
Unit testing in Spring Boot is the process of testing individual components (like service or repository methods) independently, without starting the full application.
*****

Q.How it is done in Spring Boot?
Uses JUnit for writing test cases
Uses Mockito to mock dependencies
Does not load the full Spring context
*****

Q.What are the benefits of Unit Testing?
Early bug detection
Better code quality
Easier maintenance
Faster development
*****

Q.What is JUnit?
JUnit is a testing framework for Java used to write and run unit test cases.
It helps developers check whether individual methods or classes work as expected.

Main Annotations Used in JUnit
1️⃣ @Test
Marks a method as a test case.

2️⃣ @BeforeEach
Runs before each test method.
Used for test setup.

3️⃣ @AfterEach
Runs after each test method.
Used for cleanup.

4️⃣ @BeforeAll
Runs once before all test methods.
Used for global setup.

5️⃣ @AfterAll
Runs once after all test methods.
Used for global cleanup.

6️⃣ @Disabled
Disables a test method or class.
*****

Q.What is Mockito?
Mockito is a mocking framework used in unit testing.
It creates fake objects for dependencies so that individual components can be tested independently.
*****

Q.Mockito vs JUnit?
JUnit
Used to write and run test cases
Defines test methods and assertions
Controls test execution

Mockito
Used to mock dependencies
Creates fake objects for testing
Helps test classes in isolation
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








******************************************************************************************************************************
******************************************************************************************************************************
Project                                                                             ******************************************
******************************************************************************************************************************
******************************************************************************************************************************

PROJECT OVERVIEW (WITH TEAM CONTEXT)
Q1. Explain your project in detail.
Answer:
The Airline Employee Benefits Management System is an enterprise-grade web application used by airline HR teams to manage employee benefits, dependents, documents, and payments.
The project was developed over 3 years by an 8-member cross-functional team. The backend was built using Java 8, Spring Boot, Hibernate, and MySQL, following a microservices architecture.
Security was implemented using Spring Security with JWT and OAuth2. AWS S3 was used for secure document storage, Stripe for payment processing, Angular for the frontend, and Docker with CI/CD for deployments.

Q2. Why did the project take 3 years?
Answer:
This was a long-running enterprise product, not a one-time development.
In the first year, our 8-member team delivered the MVP covering core onboarding and benefits.
Over the next two years, different team members worked in parallel on payments, security, compliance, performance tuning, and production support, which required continuous development and enhancements.

Q3. What was your team size and role distribution?
Answer:
The team consisted of 8 members:
3 Backend Developers (Java / Spring Boot)
2 Frontend Developers (Angular)
2 QA Engineers
1 DevOps Engineer

Q4. What was your role in the team?
Answer:
I worked as a Java Backend / Full-Stack Developer within the backend team.
I was responsible for developing REST APIs, implementing security, integrating Stripe payments and AWS S3, and collaborating with frontend, QA, and DevOps team members during releases.

🏗️ MICROSERVICES & ARCHITECTURE (WITH TEAM INVOLVEMENT)
Q5. How many microservices were there?
Answer:
The system was designed with 10–12 microservices, each owned by specific backend developers.
Responsibilities were clearly divided so that each backend developer handled 2–3 microservices, improving ownership and code quality.

Q6. How many APIs did your system have?
Answer:
Each microservice exposed around 5–12 REST APIs, so overall the system had approximately 90–120 APIs, developed and maintained collaboratively by the backend team.

Q7. How did the team manage microservice communication?
Answer:
Backend developers implemented REST-based communication for core flows, while DevOps and backend teams collaborated on async communication for audit logs and notifications.

🔐 SECURITY (TEAM RESPONSIBILITY)
Q8. Who implemented security?
Answer:
Security was primarily handled by the backend team.
I personally worked on JWT token handling, role-based access control, and Spring Security configurations, while the team reviewed and tested security flows.

Q9. How did the team handle token expiry issues?
Answer:
After feedback from QA and production monitoring, the backend team introduced refresh tokens to avoid frequent logouts while maintaining security.

💳 PAYMENTS (STRIPE – TEAM COLLABORATION)
Q10. Who worked on payments?
Answer:
Stripe integration was implemented by the backend team.
I specifically worked on payment initiation, webhook handling, refunds, and transaction logging, while QA tested multiple failure scenarios.

📂 DOCUMENT MANAGEMENT (AWS S3)
Q11. Who handled document management?
Answer:
The backend team implemented AWS S3 integration, while QA verified access controls and HR validation workflows.
I worked on secure upload/download APIs and S3 lifecycle policies.

🔄 WORKFLOWS & PRODUCTION SUPPORT
Q12. How did the team handle production issues?
Answer:
Production issues were handled collaboratively. Backend developers investigated logs, QA reproduced issues, and DevOps managed deployments and rollbacks.

📈 DEPLOYMENT & DEVOPS
Q13. Who handled deployments?

Answer:
A dedicated DevOps engineer handled CI/CD pipelines, but backend developers, including me, supported Dockerization and environment configuration.




******************************************************************************************************************************
******************************************************************************************************************************
Mercedz 2nd roundInterview Questions                                                ******************************************
******************************************************************************************************************************
******************************************************************************************************************************

Core Java
Arrays – Why we use them
Arrays are used mainly to store multiple values of the same type in one variable and to access data fast using index. If the size is already known, arrays are efficient because memory is allocated once.

Why array indexing is fast
Arrays store data in continuous memory. Java calculates the memory address directly using the index, so access time is O(1). No loop or search is required.

Java Collections
ArrayList – How it is dynamic
ArrayList uses an internal array. When the array becomes full, Java creates a bigger array, copies the old data, and continues. This resizing does not happen every time, so performance stays good.
Memory waste in ArrayList and how Java handles it
During resizing, old arrays become unused. Java’s Garbage Collector removes these unused arrays, so memory is freed. If size is known, we can set initial capacity to reduce resizing.

ArrayList vs LinkedList – Retrieval
ArrayList is faster for retrieval because it supports index-based access (O(1)). LinkedList must traverse node by node, so retrieval is O(n).
Insertion in the middle (ArrayList vs LinkedList)
If we insert an element in the middle:
ArrayList is slower because elements must be shifted.

LinkedList is faster because it only updates references.
So LinkedList is better for frequent insert/delete in the middle.

Set
Why we use Set
Set is used to store unique values. It automatically avoids duplicates and is useful for checking existence.
Set implementations
HashSet – fast, no order
LinkedHashSet – maintains insertion order
TreeSet – stores data in sorted order

HashMap
Why hash collision happens
Hash collision happens because hashCode range is limited, but objects are many. Two keys can produce the same hash value.

Why hash collision should be reduced
Collisions slow down performance. HashMap must use equals() to find the correct key. Too many collisions can degrade performance from O(1) to O(n). Proper hashCode() and equals() reduce collisions.

Spring Boot + Security
OAuth 2.0 with Spring Security – High-level steps
Add Spring Security and OAuth dependencies
Choose OAuth provider (example: AWS Cognito)
Configure SecurityFilterChain to secure APIs
Validate JWT tokens
Apply role or scope-based access
Test end-to-end flow
Spring Boot acts as a Resource Server, and Cognito acts as the Authorization Server.

Where to put security annotations
Config level: SecurityFilterChain (global rules)
Class level: When all APIs need same access
Method level: For fine-grained control (most common)
Project level: Enable method security once

JWT does not contain all information
JWT contains only basic identity data. Extra user details are fetched from Cognito UserInfo endpoint or our own database using userId or email.
JWT usage and reuse
JWT is issued for a specific purpose and can be reused until it expires. After expiry, a new token is required. JWT reuse is controlled by expiry, roles, and scopes.


