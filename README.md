# Learning Kotlin 2.4

📖 **Read the tutorial: [https://stahe.github.io/en-kotlin-oct-2026/](https://stahe.github.io/en-kotlin-oct-2026/)**

This course teaches the [Kotlin](https://kotlinlang.org/) 2.4 language **through examples**: over two hundred programs (337 Kotlin files), commented line by line, with their execution results included. It starts with the basics of the language and covers coroutines, database access with JDBC and Hibernate, network programming, and web services with Spring Boot.

This is the Kotlin port of the course [Learning the Java Language 25](https://stahe.github.io/en-java-oct-2026/) (October 2026), which itself is a port of the [C# 14](https://stahe.github.io/csharp-oct-2026/) course—a rewrite of a 2008 C# course: same outline, same examples, same overarching theme, but written in today’s Kotlin. All programs compile **without errors or warnings** using Kotlin 2.4.20 (warnings treated as errors) and were run on JDK 25; the results reproduced in the course are those from these runs.

| Java 25 Course (2026) | Kotlin 2.4 Course (2026) |
|---|---|
| Java 25 (LTS), JDK 25 | Kotlin 2.4.20, JDK 25 |
| compact source files (`java Prog.java`) | high-level `main` functions, `kotlinc`, IntelliJ IDEA green triangle |
| Maven projects (`pom.xml`) | Gradle projects in Kotlin DSL (`build.gradle.kts`), Gradle 9.8 wrapper |
| `null`, wrapper classes, and `Optional` | `null` safety in the type system (`?.`, `?:`, `!!`) |
| accessors, records, no operator overloading | properties, data classes, operator overloading, extension functions |
| controlled exceptions, `try` with resources | all uncontrolled exceptions, `use` |
| Stream API | collection operations, sequences |
| functional interfaces, lambdas | functional types, lambdas, `inline` functions, delegated properties |
| `CompletableFuture`, virtual threads | **coroutines**: `suspend`, `launch` / `async`, structured concurrency, `Flow`, `Channel` |
| JUnit 6, Spring Framework 7 | JUnit 6 and `kotlin.test`, Spring Framework 7 (`kotlin-spring` plugin) |
| Jackson 3 | Jackson 3 with data classes |
| JDBC, MySQL Connector/J, HikariCP | the same, using Kotlin idioms |
| Hibernate 7 | Hibernate 7 with the `kotlin-jpa` (no-arg) and all-open plugins |
| `HttpClient`, `Socket` / `ServerSocket` | the same classes, in Kotlin |
| Spring Boot 4 | Spring Boot 4 in Kotlin |

## Course Outline

| Chapter | Content |
|---|---|
| Installation | JDK 25, IntelliJ IDEA / VS Code, the `kotlinc` compiler, Gradle (wrapper, Kotlin DSL), multi-module projects |
| Language Basics | types, `val` / `var`, type inference, string templates, raw strings, `null` safety, conversions, arrays, operators, `when`, ranges and loops, exceptions, `use`, enums, default and named parameters, local functions, `Pair`, and destructuring |
| Classes, Interfaces, Data Classes | primary constructors, properties, `object` and `companion object`, inheritance, sealed classes, operator overloading, indexers, value classes, extension functions, interfaces, abstract classes, generics and variance, packages, data classes, smart type casting |
| Commonly Used Kotlin Classes | strings, arrays, read-only and mutable collections, functional operations, **sequences**, text and binary files, JSON with Jackson 3, regular expressions (`Regex`) |
| Layered Architectures | [DAO] / [business logic] / [UI], multi-project Gradle builds, **JUnit 6** and `kotlin.test` unit tests, **dependency injection** with Spring |
| Functional types, lambdas, and events | functional types, lambdas, function references, `fun interface`, closures, composition, `inline` functions, listeners, observable delegated properties |
| Execution threads | `thread { }`, **virtual threads**, `synchronized`, `@Volatile`, `ReentrantLock`, `Condition`, atomic operations, semaphores, concurrent collections, `ExecutorService`, fork/join, `ThreadLocal`, `ScopedValue` |
| Asynchronous programming | **coroutines**: `suspend` functions, `runBlocking`, `launch`, `async` / `await`, dispatchers, structured concurrency, exceptions, cancellation and timeouts, `Flow`, `Channel`, `CompletableDeferred`, limited parallelism, coroutines and virtual threads |
| Database Access with JDBC | MySQL, MySQL Connector/J, `DataSource`, and HikariCP, parameterized queries and SQL injection, transactions, batches, JDBC with virtual threads and coroutines |
| **Hibernate** | Kotlin entities, `SessionFactory` / `Session`, CRUD, HQL and Criteria API, relationships, migrations, optimistic concurrency, native SQL, Spring ORM, and `@Transactional` |
| Web Programming | TCP/IP, IPv6, TCP clients and servers (one virtual thread per client), HTTP, `HttpClient`, SMTP with Jakarta Mail |
| Web Services | REST / JSON with **Spring Boot 4** in Kotlin, Kotlin console clients, JavaScript web client, Node.js client |

## The Common Thread: A Tax Calculator in 9 Versions

Throughout the course, version by version, we build an application for **calculating income tax**:

- **Version 1**: a single program; **Version 2**: classes and interfaces; **Version 3**: data read from a text or JSON file;
- **versions 4 and 5**: a layered architecture, organized into Gradle subprojects, tested with JUnit, and integrated via dependency injection with Spring;
- **versions 6 and 7**: data stored in a MySQL database, retrieved using JDBC and then Hibernate;
- **version 8**: a TCP server for tax calculation and its client;
- **version 9**: a Spring Boot REST web service, its console client, and its web client.

## Technologies

Kotlin 2.4.20 · JDK 25 · Gradle 9.8 (Kotlin DSL) · IntelliJ IDEA · kotlinx.coroutines 1.11 · JUnit 6 · Spring Framework 7 · Jackson 3 · MySQL 8 · MySQL Connector/J 9 · HikariCP · Hibernate ORM 7.4 · Jakarta Persistence 3.2 · Spring Boot 4.1 · Laragon

## Prerequisites

- Previous programming experience in any language.
- A [JDK 25](https://adoptium.net) (Eclipse Temurin or another distribution) and [IntelliJ IDEA](https://www.jetbrains.com/idea/) (Kotlin is built-in). Gradle does not need to be installed: each chapter folder contains its own wrapper (`gradlew`). If JDK 25 is not installed, Gradle will download it automatically (using the `foojay-resolver-convention` plugin). [Laragon](https://laragon.org) for MySQL (chapters on databases). Installation instructions are provided in the course.

## Author

This course and its code were written by **Claude**, the AI from [Anthropic](https://www.anthropic.com) (October 2026), at the request of Serge Tahé, based on his Java 25 course.

Reviewer: [Serge Tahé](https://stahe.github.io)
