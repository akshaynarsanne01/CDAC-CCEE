# Core java

#### Why JAVA ?
- Platform or architechture independant ( write once run anywhere ).
- Simple and Robust
- Secure
- Automatic memory management.
- Inherent multi thread support.
- Object oriented support 
    - Encapsulation
    - Inheritance
    - Polymorphysm
    - Abstraction
- Excellent I/O support
- Inherent networking support for TCP/IP, UDP/IP programming & for urls
- Supports Functional programming and many more.

```java
public class HelloWorld{
    public static void main (String [] args){
        System.out.println("Hello world");
    }
}
```
Steps without IDE

1. Create Folder (any name).
2. Create 2 sub folders src and bin
- src for java sourse files
- bin is for .class files which are executables
3. Write java file under src
4. how to compile
- open cmd and go to src 
- javac -d ..\bin HelloWorld.java
5. how to execute
- cd ..\bin
- java HelloWorld

### Naming conventions 
- class, interfaces , enum first word should start with the upper case and then follow camel case notation
e.g: HelloWorld

- data members/ methods( functions ) should start with lower case and then follow camel case notation
e.g: calculateSalary

- Constants : All uppercase
e.g: PI

- **Rules on Identifiers :**
  - Identifiers must start with a letter a currency character ($) or a connecting caracter such as underscrores ( _ )
  - Can't use java keyword as an identifier
  - Are case sensitive
- **Legal Access Specifiers for data members and methods :**
  - *private* : visible within the same class
  - *default* (package private ): no access modifier - visible within same package
  - *protected* : accessible within the same package and accessible to sub classes via inheritance
  - *public* accesssible from anywhere
- **Legal class level access specifiers :**
  - *default* : current package only
  - *public* : accessile from anywhere

##### Create a Java program that accepts two numbers as command-line arguments, adds them, and displays the result.

```java
public class AddNumbers {
    public static void main(String[] args) {
        // Check if exactly 2 command line arguments are provided
        if (args.length != 2) {
            System.out.println("Error: Please provide exactly two numbers as arguments.");
            return;
        }
        int num1 = Integer.parseInt(args[0]);
        int num2 = Integer.parseInt(args[1]);

        int sum = num1 + num2;

        System.out.println("The sum of " + num1 + " and " + num2 + " is " + sum + ".");
    }
}
```
##### How to accept input from user ? 
- Introduce Scanner class
- What is Scanner
  - A simple text scanner which can parse primitive types and strings using regular expressions.
  - It has inherent small ~1k buffer
  - can parse console input , text file, socket , string
- Steps
  1. Import the Scanner Class
To use the Scanner class in your Java program, you must import it from the java.util package. You can import the entire package or just the Scanner class.

    ```java
    import java.util.*;         // Imports all classes from java.util package
    // or
    import java.util.Scanner;   // Imports only the Scanner class
    ```
  2. Create an Instance of the Scanner Class You need to create a instance of the Scanner class to read input from various sources such as files, input streams, and strings. For reading from standard input  (console), you can use the System.in input stream.

  ```java
  Scanner sc = new Scanner(System.in);  // Creates a new Scanner instance to read from standard input
  ```
  - Constructor: The Scanner class constructor takes an InputStream as an argument.
  ```java
  public Scanner(InputStream in)
  ```
  - Standard Input: System.in is the standard input stream, typically used for reading input from the console.
  3. Check the Data Type of Input The Scanner class provides several methods to check if the next token in the input can be interpreted as a specific data type. This helps in validating the input before reading it.
    ```java
    public boolean hasNextInt()
    public boolean hasNextByte()
    public boolean hasNextLong()
    ```
  4. Read and Parse Data
  The Scanner class provides various methods to read and parse different types of data from the input. These methods throw an InputMismatchException if the input does not match the expected type.
    ```java
    public int nextInt() throws InputMismatchException
    public double nextDouble() throws InputMismatchException
    public String next() throws InputMismatchException
    public boolean nextBoolean() throws InputMismatchException
    public String nextLine() throws InputMismatchException
    ```
  5. Close the Scanner
It is a good practice to close the Scanner instance after you are done with it to release any underlying resources. This is especially important when working with file or network input streams.
    ```java
    sc.close();  // Closes the Scanner instance
    ```
#### Basic rules
- Java compiler doesn't allow accessing of uninitialized data members.
- Java src file can have more than one non public class ( i.e default )
- Files with no public classes ( default scoped ) can have a name that doesnot match with any of the classes in the file.
  -- e.g : Test.java
  -- class A{}
  -- class C{}
- There can only one public class per sourse code file.
- if there is public class in file name must match with the class name.

#### What is unicode 
- Unicode is a universal character encoding standard designed to uniquely and consistently represent characters from all written languages worldwide. Unlike ASCII, which is limited to 128 characters and does not support many scripts like Japanese or Devanagari, Unicode aims to encompass all characters across writing systems. Initially using 16-bit encoding, it has expanded to accommodate a vast range of characters, supporting diverse languages and symbols.

### Data Types in Java

1. primitive data types 
boolean,char,byte,short,long,float,double

2. reference types
class type , array type , interface type

   Pointers vs java references
   Pointer arithmatic is not allowed in java.
   reference --- holds internal representation of address (equivalent to object pointer in c++)
# Conversions Regarding Primitive Types in Java

## Automatic Conversions (Widening)

### Overview

Automatic conversions, also known as widening or promotion, are implicit type conversions handled by the Java compiler. These conversions occur when a value of a smaller data type is assigned to a larger data type, and no explicit casting is required.

### Examples

- `byte` → `short` → `int` → `long` → `float` → `double`
- `char` → `int`

For instance, converting `long` to `float` is an automatic conversion because the `float` data type can hold a larger range of values compared to the `long` data type.

### Rules for Automatic Conversions

1. **Source and Destination Compatibility:**
   - The source and destination types must be compatible.
   - The destination data type must be able to store a larger magnitude of values than the source data type.

2. **Specific Promotions:**
   - Any arithmetic operation involving `byte` or `short` is automatically promoted to `int`.
   - Arithmetic operations involving `int` and `long` are promoted to `long`.
   - Arithmetic operations involving `long` and `float` are promoted to `float`.
   - Arithmetic operations involving `byte`, `short`, and `float` or `double` are promoted to `double`.

### Examples of Automatic Promotions

```java
byte a = 10;
int b = a;            // byte to int (automatic)
float c = b;          // int to float (automatic)
double d = c;         // float to double (automatic)

char e = 'A';
int f = e;            // char to int (automatic)
```

## Narrowing Conversions (Type-Casting) in Java

### Overview

Narrowing conversions, also known as type-casting, are explicit conversions performed by the programmer in Java. These conversions occur when a value of a larger data type is assigned to a smaller data type. Due to potential loss of information, such as precision or range, explicit casting is required.

### Examples

Narrowing conversions require the programmer to specify the target data type explicitly. Here are some common examples:

- `double` → `int`
- `float` → `long`
- `double` → `float`

### Example of Type-Casting

Below is a simple Java code snippet demonstrating type-casting with various data types:

```java
double x = 10.99;
int y = (int) x;      // double to int (narrowing, explicit cast required)

float z = (float) x;  // double to float (narrowing, explicit cast required)
long w = (long) z;    // float to long (narrowing, explicit cast required)
```
## Data Type Ranges
| Data Type | Description                                                    | Range                                              |
|-----------|----------------------------------------------------------------|----------------------------------------------------|
| byte      | 8-bit signed two's complement integer                          | -128 to 127                                        |
| short     | 16-bit signed two's complement integer                         | -32,768 to 32,767                                  |
| int       | 32-bit signed two's complement integer                         | -2,147,483,648 to 2,147,483,647                    |
| long      | 64-bit signed two's complement integer                         | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| float     | Single-precision 32-bit IEEE 754 floating point               | 1.40129846432481707e-45 to 3.40282346638528860e+38 |
| double    | 8-byte IEEE 754 double-precision floating point               | 4.94065645841246544e-324 to 1.79769313486231570e+308 |
| boolean   | Typically 1-bit, true or false values only                    | true or false                                      |
| char      | 16-bit unsigned Unicode character (UTF-16)                    | 0 to 65,535                                        |
