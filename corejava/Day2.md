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

## Garbage Collection in Java

Garbage Collection (GC) identifies and deletes unused objects from the heap memory, freeing space occupied by unreferenced objects.

### Key Concepts

- **Garbage:** Unreferencable objects (number of references = 0).
- **Automatic GC:** Prevents memory leaks by automatically reclaiming memory.
- **JVM Threads:** 
  - Main thread (executes `main()` sequentially).
  - GC thread (daemon thread running in the background).

### Explicit GC Request

Use the `System` class API:
```java
System.gc(); // Requests JVM to run GC
```

## Java Packages

### Overview

If no package statement is added, `javac` will place the class in the default, anonymous package.

### Creating User-Defined Packages

#### Syntax

Use the `package` keyword. It must appear only once at the top of the source file.
```java
package tester;
class TestBox { ... }

package com.cdac.tester;
class TestBox { ... }

package com.cdac.core;
class Box { ... }
```

### Purpose
- Packages group functionally similar classes together, providing:

1. Functional separation.
2. Resolution of duplicate class names.
3. Finer control over access specifiers.

```java
// File: com/cdac/core/Box.java
package com.cdac.core;
public class Box {
    private double length, width, height;

    public Box(double length, double width, double height) {
        this.length = length;
        this.width = width;
        this.height = height;
    }
    
    // Additional methods will be added here
}

// File: com/cdac/tester/CreateBox.java
package com.cdac.tester;
import com.cdac.core.Box;

public class CreateBox {
    public static void main(String[] args) {
        Box box = new Box(10, 20, 30);
        // Testing Box functionalities
    }
}
```

## Day 2 Codes
```java
import java.util.Scanner;
class TestBox {
 public static void main(String[] args) 
 {
	 int data=100;
    //sc : ref , RHS : object
	Scanner sc=new Scanner(System.in);
	System.out.println("Enter Box dims : w d h");
	Box b;//b : ref type var : class type , local var
	//local var : mem allotted on stack , no of bytes decided by JVM
	//System.out.println(b);//javac err !!!!
	b=new Box(sc.nextDouble(),sc.nextDouble(),sc.nextDouble());//Box class loaded in method area n instance created on heap
	System.out.println(b);//no err ! o/p : NameOfClass@address => hash code
	//display dims
	System.out.println(b.getBoxDimensions());
	//display vol
	System.out.println("Volume "+b.getVolume());
	Box b2=b;//copy of refs
	System.out.println(b2.getBoxDimensions());//same as above
	b=null;//b is no longer referring to box object
//	How many objects are marked for GC ? 0
//System.out.println(b.getBoxDimensions());//java.lang.NullPointerException (NPE)
	System.out.println("cntd....");
	System.out.println(b2.getBoxDimensions());
	System.out.println("cntd again....");
	b2=null;
	//	How many objects are marked for GC ? 1
	//System.out.println(b2.getBoxDimensions()); NPE
	//System.out.println("cntd again 2");
	sc.close();
 }
}
```
```java
class Box {
//state : non static data members : mem allocated in heap upon instance creation . Inited to def. values
//tight encap.
private double width;
private double depth;
private double height;
//how to init state of the object ? using parameterized ctor
 Box(double w,double d,double height)
 {
    width=w;
	depth=d;
	//this => current / invoker object reference
	this.height=height;
 }
 //add a method : To return Box details (i.e dimensions of the Box) in a String form 
 String getBoxDimensions() {
	 //this : OPTIONAL , added only for the understanding !
	  return "Box Dims are "+this.width+" "+this.depth+" "+this.height;
 }
 //add instance method to return computed volume of the box.
 double getVolume() {
	  return width*depth*height;
 }
}
```

```java
class TestBox2 {
 public static void main(String[] args) 
 {
	 int data=100;    
	Box b1=new Box(10,20,30);
	Box b2=b1; //any objs marked for GC ? none 
	b2=new Box(1,2,3);//b2 --> 2nd box obj
	//any objs marked for GC ? NO
	b1=null; //any objs marked for GC ? YES --1st box (10,20,30) 
	b2=null; //any objs marked for GC ? 2
	
 }
}
```

```java
class TestPrimitiveTypeConversions
{
  public static void main(String[] args)
  {
	   byte b1=10;
	//   byte b2=128;//javac error : lossy conversion int --> byte
	byte b2=20;
	  byte b3=(byte)(b1+b2);//RHS : int --> byte
	  b1 += 15;//b1 =(byte) (b1+15) : type casting done implicitly by javac
	//  b1 = b1+15; //javac err !
	  double d1=123.456;
	  float f1=12.34f; //no javac err
	  long l1=12345678;
	  f1=l1;//no javac err
	  l1=f1;//javac err
  }
}
```
