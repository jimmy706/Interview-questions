# Java interview questions

### Q1: What is Java?

> Difficulty : ⭐

Java is the high-level, object-oriented, robust, secure programming language, platform-independent, high performance, Multithreaded, and portable programming language. It was developed by James Gosling in June 1991. It can also be known as the platform as it provides its own JRE and API.

### Q2: List some features of Java?

> Difficulty : ⭐⭐

**1. OOPs concept:**

- Object oriented
- Inheritance
- Encapsulation
- Polymorphism
- Abstraction

**2. Platform independent:** A single program works on different platforms without any modification.
**3. High performance:** JIT (Just In Time compiler) enables high performance in Java. JIT converts the bytecode into machine language and then JVM starts the execution.
**4. Multi-threaded:** A flow of execution is known as a Thread. JVM creates a thread which is called main thread. The user can create multiple threads by extending the thread class or by implementing Runnable interface.

### Q3: What do you understand by Java virtual machine?

> Difficulty : ⭐⭐
> Java Virtual Machine is a virtual machine that enables the computer to run the Java program. JVM acts like a run-time engine which calls the main method present in the Java code. JVM is the specification which must be implemented in the computer system. The Java code is compiled by JVM to be a Bytecode which is machine independent and close to the native code.

### Q4: Difference between JDK, JRE, and JVM?

- **JVM(Java Virtual Machine):** A virtual machine that enables the computer to run the Java program.
- **JRE(Java Runtime Environment):** It is the implementation of JVM. The Java Runtime Environment is a set of software tools which are used for developing Java applications. It is used to provide the runtime environment.
- **JDK(Java Development Kit):** It is a software development environment which is used to develop Java applications and applets. It contains JRE + development tools.

### Q5: How many types of memory areas are allocated by JVM?

- **Class(Method) Area:** Class Area stores per-class structures such as the runtime constant pool, field, method data, and the code for methods.
- **Heap:** It is the runtime data area in which the memory is allocated to the objects
- **Stack:** Java Stack stores frames. It holds local variables and partial results, and plays a part in method invocation and return. Each thread has a private JVM stack, created at the same time as the thread. A new frame is created each time a method is invoked. A frame is destroyed when its method invocation completes.
- **Program Counter Register:** PC (program counter) register contains the address of the Java virtual machine instruction currently being executed.
- **Native Method Stack:** It contains all the native methods used in the application.
