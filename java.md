# Java Interview Notes  
 
## Table of Contents  
1. [Core Java](#core-java)
    - [Data Types](#data-types)  
    - [OOP Concepts](#oop-concepts)  
        - [Encapsulation](#encapsulation)  
        - [Inheritance](#inheritance)  
        - [Polymorphism](#polymorphism)  
        - [Abstraction](#abstraction)  
    - [Collections Framework](#collections-framework)  
        - [List](#list)  
        - [Set](#set)  
        - [Map](#map)  
    - [Exception Handling](#exception-handling)  
    - [Multithreading](#multithreading)  
    - [Java 8 Features](#java-8-features)
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
 
## Data Types  
 
### Primitive Data Types  
- **byte:** 8-bit integer, range -128 to 127.  
- **short:** 16-bit integer, range -32,768 to 32,767.  
- **int:** 32-bit integer, range -2^31 to 2^31-1.  
- **long:** 64-bit integer, range -2^63 to 2^63-1.  
- **float:** 32-bit floating-point.  
- **double:** 64-bit floating-point.  
- **char:** 16-bit Unicode character.  
- **boolean:** true/false.  
 
```java
// Example of primitive types
int number = 42;
boolean isActive = true;
char initial = 'A';
```
 
### Non-Primitive Data Types  
- **String:** Immutable sequence of characters.  
- **Array:** Fixed-size collection of elements of the same type.  
 
```java
// Example: String and Array
String name = "John";
int[] numbers = {1, 2, 3, 4, 5};
```
 
---
 
## OOP Concepts  
 
### Encapsulation  
- Wrapping data (variables) and methods together.  
- Use private fields and public getters/setters.  
 
```java
class Person {
    private String name;
    public String getName() {
        return name;
    }
    public void setName(String name) {
    this.name = name;
    }
}
```
 
### Inheritance  
- Allows a child class to inherit properties and methods from a parent class.  
 
```java
class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}
 
class Dog extends Animal {
    void bark() {
        System.out.println("This dog barks.");
    }
}
```
 
### Polymorphism  
- **Method Overloading:** Same method name, different parameter lists.  
- **Method Overriding:** Child class provides specific implementation of a method in the parent class.  
 
```java
// Overloading
class Calculator {
    int add(int a, int b) {
        return a + b;
    }
 
    double add(double a, double b) {
        return a + b;
    }
}
 
// Overriding
class Parent {
    void display() {
        System.out.println("Parent class");
    }
}
 
class Child extends Parent {
    @Override
    void display() {
        System.out.println("Child class");
    }
}
```
 
### Abstraction  
- Hides implementation details; only shows functionality.  
- Achieved using **abstract classes** and **interfaces**.  
 
```java
// Abstract class
abstract class Shape {
    abstract void draw();
}
 
class Circle extends Shape {
    void draw() {
        System.out.println("Drawing a circle.");
    }
}
 
// Interface
interface Vehicle {
    void drive();
}
 
class Car implements Vehicle {
    public void drive() {
        System.out.println("Driving a car.");
    }
}
```
 
---
 
## Collections Framework  
 
### List  
- Ordered, allows duplicate elements.  
- Implementations: **ArrayList**, **LinkedList**.  
 
```java
import java.util.ArrayList;
import java.util.List;
 
List<String> list = new ArrayList<>();
list.add("Apple");
list.add("Banana");
System.out.println(list); // [Apple, Banana]
```
 
### Set  
- Unordered, no duplicate elements.  
- Implementations: **HashSet**, **LinkedHashSet**, **TreeSet**.  
 
```java
import java.util.HashSet;
 
Set<String> set = new HashSet<>();
set.add("Apple");
set.add("Apple"); // Duplicate ignored
System.out.println(set); // [Apple]
```
 
### Map  
- Key-value pairs, no duplicate keys.  
- Implementations: **HashMap**, **LinkedHashMap**, **TreeMap**.  
 
```java
import java.util.HashMap;
 
Map<String, Integer> map = new HashMap<>();
map.put("Apple", 1);
map.put("Banana", 2);
System.out.println(map); // {Apple=1, Banana=2}
```
 
---
 
## Exception Handling  
- Used to handle runtime errors.  
- Keywords: **try**, **catch**, **finally**, **throw**, **throws**.  
 
```java
try {
    int result = 10 / 0; // Throws ArithmeticException
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero.");
} finally {
    System.out.println("Execution completed.");
}
```
 
---
 
## Multithreading  
 
### Basics  
- **Thread:** Lightweight sub-process.  
- **Runnable:** Interface to define thread behavior.  
 
```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running.");
    }
}
 
MyThread t1 = new MyThread();
t1.start();
```
 
---
 
## Java 8 Features  
 
### Streams  
- Sequence of elements supporting aggregate operations.  
 
```java
import java.util.Arrays;
import java.util.List;
 
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
numbers.stream()
       .filter(n -> n % 2 == 0)
       .forEach(System.out::println); // 2, 4
```
 
### Lambdas  
- Concise way to represent anonymous methods.  
 
```java
interface Calculator {
    int add(int a, int b);
}
 
Calculator calc = (a, b) -> a + b;
System.out.println(calc.add(5, 3)); // 8
```
 
### Functional Interfaces  
- Interfaces with a single abstract method.  
- Example: **Runnable**, **Comparator**, **Predicate**.  
 
```java
import java.util.function.Predicate;
 
Predicate<Integer> isEven = x -> x % 2 == 0;
System.out.println(isEven.test(4)); // true
```  
 
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
