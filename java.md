# Java Notes  
 
## Table of Contents  
1. [Core Java](#core-java)  
   - [Data Types](#data-types)  
   - [OOP Concepts](#oop-concepts)  
   - [Collections Framework](#collections-framework)  
2. [Advanced Java](#advanced-java)  
   - [Multithreading and Concurrency](#multithreading-and-concurrency)  
   - [JVM Internals](#jvm-internals)  
   - [Functional Programming (Streams and Lambda)](#functional-programming-streams-and-lambda)  
3. [Spring Framework](#spring-framework)  
   - [Core Spring](#core-spring)  
   - [Spring Boot](#spring-boot)  
4. [Databases and Persistence](#databases-and-persistence)  
   - [JDBC](#jdbc)  
   - [Hibernate](#hibernate)  
   - [JPA](#jpa)  
5. [System Design](#system-design)  
6. [Practice Questions](#practice-questions)  
 
---
 
## Core Java  
 
### Data Types  
- **Primitive Types:** byte, short, int, long, float, double, char, boolean  
- **Non-Primitive Types:** String, Arrays, Classes  
 
```java
// Example: Primitive data type
int number = 42;
```
 
### OOP Concepts  
- **Encapsulation:** Protect data using access modifiers.  
- **Inheritance:** Achieving reusability by inheriting parent class properties.  
- **Polymorphism:** Overloading and overriding methods.  
- **Abstraction:** Hiding implementation details using interfaces and abstract classes.  
 
---
 
## Advanced Java  
 
### Multithreading and Concurrency  
- **Thread Lifecycle:** NEW, RUNNABLE, BLOCKED, WAITING, TIMED_WAITING, TERMINATED  
- **Synchronization:** Ensures thread safety.  
- **Executors Framework:** Efficient thread management.  
 
```java
// Example: Runnable implementation
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread is running.");
    }
}
```
 
---
 
## Spring Framework  
 
### Core Spring  
- Dependency Injection (DI)  
- Application Context  
 
### Spring Boot  
- Creating REST APIs  
- Working with annotations: @RestController, @RequestMapping  
 
---
 
## System Design  
 
- **Common Design Patterns:** Singleton, Factory, Observer, etc.  
- **Scalability Strategies:** Caching, Load Balancing, Database Sharding.  
 
---
 
## Practice Questions  
 
1. Write a program to reverse a string.  
2. Implement a singleton class.  
3. Solve producer-consumer problem using synchronization.
