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
    

