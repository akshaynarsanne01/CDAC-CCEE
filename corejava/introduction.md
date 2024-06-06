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
