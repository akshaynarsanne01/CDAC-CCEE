## JVM-ARCHITEHTURE

<img width="869" alt="JVM-architecture" src="https://github.com/akshaynarsanne01/CDAC-CCEE/assets/147087536/2c7d9e8e-e34f-4e24-a354-bbc6ceb96bba">

# Java Virtual Machine (JVM) Internal Components

Java Virtual Machine (JVM) is the cornerstone of Java's platform independence, responsible for executing Java bytecode. It comprises several internal components to manage the execution of Java programs efficiently.

## 1. Class Loader Subsystem

JVM's class loader subsystem performs three essential tasks:

- **Loading**: Loads `.class` files into memory.
- **Verification**: Verifies bytecode instructions for security and correctness.
- **Allocation**: Allots memory required for the program's execution.

## 2. Runtime Data Area

The runtime data area is the memory resource utilized by JVM, divided into five parts:

- **Method Area (Metaspace in Java SE 8)**: Stores class code and method code.
- **Heap**: Objects are created on the heap.
- **Java Stacks**: Execute Java methods, containing frames for method execution.
- **Program Counter Registers**: Store memory addresses of instructions to be executed.
- **Native Method Stacks**: Execute native methods written in languages other than Java (e.g., C).

## 3. Native Method Interface

The Native Method Interface connects native method libraries (C header files) with JVM for executing native methods.

## 4. Native Method Library

The Native Method Library holds information about native libraries used in the program.

## 5. Execution Engine

The Execution Engine consists of an interpreter and JIT (Just-In-Time) compiler, responsible for converting bytecode into machine code. JVM optimizes the execution by deciding which parts to interpret and which to compile using JIT. HotSpot represents the block of code executed by the JIT compiler.

# Encapsulation in Java

Encapsulation is the bundling of data and methods into a single unit, providing a protective shield to prevent outside access to the data. It involves hiding the internal state of an object and restricting access to it only through methods.

### Advantages of Encapsulation:

1. **Data Hiding**: Ensures security by hiding the implementation details.
2. **Increased Flexibility**: Allows defining read-only, write-only, or read-write variables.
3. **Reusability**: Enhances reusability and facilitates adapting to new requirements.
4. **Easy Testing**: Simplifies testing of code by isolating implementation details.

### Basic Unit of Encapsulation: Class

A class serves as a blueprint for creating objects, encapsulating data and methods common to all objects of the same type. Class declaration includes:

- Access specifiers (public or default)
- Class name (camel case, begins with a capital letter)
- Superclass (if any)
- Interfaces implemented (if any)
- Body enclosed in braces

### Object

An object represents a real-life entity, encapsulating state, behavior, and identity. It consists of:

- **State**: Attributes or instance variables representing properties of the object.
- **Behavior**: Methods representing actions performed on the object's data.
- **Identity**: Unique identifier enabling interaction with other objects.

#### Creating an Object

The `new` operator instantiates a class, allocating memory and invoking the class constructor. Constructors, special methods with the same name as the class, initialize object state. If no constructor is explicitly defined, a default constructor is provided.

#### Usage of `this` Keyword

The `this` keyword is used to:
1. Unhide instance variables from method local variables.
2. Invoke another overloaded constructor in the same class, avoiding duplication through constructor chaining.

