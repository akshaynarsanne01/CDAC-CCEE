### FEATURES OF C++
- C++ is a general-purpose programming language that was developed as an enhancement of the C Language to include an Object Oriented-Paradigm.  It is an imperative and compiled language.
  ### C++ has a number of features, including:
  - Object-Oriented Programming
  - Simple and popular
  - High-Level Language
  - Strongly typed
  - Case-sensitive
  - Memory Management (Dynamic Memory Allocation)
  - Multi-threading support

### INTRODUCTION
- C++ is derived from C Language. It is a Superset of C. 
- Earlier C++ was known as C with classes. 
- In C++, the major change was the addition of classes and a mechanism for inheriting class  objects into other classes. 
- Most C Programs can be compiled in C++ compiler. 
- C++ expressions are the same as C expressions. 
- All C operators are valid in C++. 

### STRUCTURE OF CPP PROGRAM
- ***Comments(documentation)***
- ***Preprocessor Statements/ Header File  Inclusion***
- ***Function Declaration***
- ***Global Variable Declaration***
- ***Extern Variable Declaration***
- ***Structure / Class Declaration***
- ***Function definitions***
### HELLO WORLD IN CPP
```cpp
#include<iostream>
using namespace std;
int main(){
int a;
cin>>a; //cin is object of istream
cout<<"Hello world !""<<endl; //cout is  object of ostream
return 0;
}
```
- Compilation: on Linux Platform 
                - g++  Hello.cpp 
- After compilation it will produce a.out file
                - Execution: ./a.out

### 
 

 ``` >> ``` called as extraction or input operator
 ``` << ``` is called as insertion operator or output operator
 ``` using namespace std ``` is used to specify namespace
 ``` return 0 ``` tell OS that program execution is graceful
## COMPILATION PROCESS : 
![image](https://github.com/akshaynarsanne01/CDAC-CCEE/assets/147087536/8c5bb5ac-9703-4ffb-90b1-e8b4e8c25fa6)

### PROGRAM MEMROY 

![image](https://github.com/akshaynarsanne01/CDAC-CCEE/assets/147087536/d1fea15f-61f2-449c-886b-8b2e979de639)

When we run a program ,os allocates part of memory for that program and then copies executable from disk to memory.

The C compiler divides this area in 4 parts
 - Stack
 - Heap
 - Code Area/Segment
 - Data Area/Segment
    - Initialized data
    - Uninitialized data

  #### CODE SEGMENT
  - Fixed in nature because size of program is known at load time.
  - It is reserved for executable code of program.
  - This is read only memory area we can not change it during execution.
  - Only Pointers to functions can access this area.

  #### DATA SEGMENT
  - Fixed in nature because size of programs data is known at load time.
  - It is contains internal and external static variables, global variables, initialized array and structures and constant strings.
  - Initialized Data Area:
    - On Initialization static and global variables are stored at initialized data area. All others variables gets stored in uninitialized data area.
  - Uninitialized Data Area:
    - In uninitialized data area variables get initialized to 0 nut in initialized area they are initialized with their respective values.
    - Static and global variables known as load time variables.
   
  #### Stack Segment

  The stack segment is a region of memory used for dynamic memory allocation in a last-in, first-out (LIFO) manner. It is typically used for:
  
  - **Function call management:** Including storing return addresses, arguments, and local variables.
  - **Automatic memory management:** Memory is automatically allocated when a function is called and deallocated when the function returns.
  
  ##### Characteristics of the Stack:
  - **Size:** The stack size is usually limited and smaller compared to the heap.
  - **Speed:** Access to stack memory is faster due to its LIFO nature.
  - **Lifetime:** Variables on the stack are short-lived and exist only during the execution of the function in which they are declared.
  - **Usage:** Ideal for temporary variables, function parameters, and return addresses.
  
  ##### Example:
  ```cpp
  void function() {
      int localVariable = 10; // Allocated on the stack
  }
  ```

  #### HEAP SECTION
  The heap section is a region of memory used for dynamic memory allocation, where blocks of memory can be allocated and freed in an arbitrary order. This section is essential for managing memory for data structures whose size may not be known at compile time or may need to persist beyond the scope of a function.
  
  ##### Characteristics of the Heap:
  - **Size:** The heap is generally larger than the stack and can grow as needed, constrained only by the system's available memory.
  - **Speed:** Access to the heap is slower compared to the stack due to its unordered nature and the overhead of managing dynamic memory.
  - **Lifetime:** Memory allocated on the heap persists until it is explicitly deallocated, allowing it to exist beyond the function scope in which it was allocated.
  - **Usage:** The heap is used for large data structures, dynamic arrays, and objects that need to be accessed across multiple functions or have a lifetime beyond the current function.
  
  #### Dynamic Memory Allocation:
  In C++, dynamic memory allocation on the heap is done using the `new` and `delete` operators.
  
  ##### Allocation:
  - **Single Object:** To allocate memory for a single object, use the `new` operator.
      ```cpp
      int* ptr = new int; // Allocates an integer on the heap
      *ptr = 10;          // Assigns value to the allocated integer
      ```
  - **Array of Objects:** To allocate memory for an array of objects, use the `new[]` operator.
      ```cpp
      int* array = new int[10]; // Allocates an array of 10 integers on the heap
      ```
  
  #### Deallocation:
  - **Single Object:** To deallocate memory for a single object, use the `delete` operator.
      ```cpp
      delete ptr; // Deallocates the integer from the heap
      ```
  - **Array of Objects:** To deallocate memory for an array of objects, use the `delete[]` operator.
      ```cpp
      delete[] array; // Deallocates the array from the heap
      ```
  
  ### Example:
  ```cpp
  #include <iostream>
  
  void function() {
      // Allocating a single integer on the heap
      int* singleValue = new int;
      *singleValue = 20;
      std::cout << "Single value: " << *singleValue << std::endl;
      
      // Deallocating the single integer
      delete singleValue;
  
      // Allocating an array of integers on the heap
      int* array = new int[5];
      for (int i = 0; i < 5; ++i) {
          array[i] = i * 10;
      }
      for (int i = 0; i < 5; ++i) {
          std::cout << "Array[" << i << "] = " << array[i] << std::endl;
      }
  
      // Deallocating the array
      delete[] array;
  }
  
  int main() {
      function();
      return 0;
  }
  ```

### THE C++ STRING CLASS
- Must #include <string> to create and use string objects
- Can define string variables in programs
  ``` string name; ```
- Can assign values to string variables with the assignment operator
  ``` name = “Kareena";```
- Can display them with cout
  ``` cout << name; ``` 
- Can input string with cin
  ``` cin >>name; ```
