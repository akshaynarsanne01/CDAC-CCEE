# OPERATORS
Operators are the symbols that tells compiler to perform certain mathematical or logical on data and variables

### Types of operator
  - Unary operators (One operand)
  - Binary operators(Two operands)
  - Ternary operators(Three operands)
###  Operators are classified in to following groups:
  - Arithmetic Operators
  - Relational Operators
  - Logical Operators
  - Assignment  Operator
  - Increment and Decrement Operators
  - Conditional Operators
  - Bitwise Operators
  - Special Operators
  - Shorthand Operators

## ARITHMATIC OPEARTORS
| Operator | Meaning                      |
|----------|------------------------------|
| +        | Addition and unary plus      |
| -        | Subtraction and unary minus  |
| *        | Multiplication and dereferencing |
| /        | Division                     |
| %        | Modulo division (remainder)  |

- % operator cannot be used on floating point data.
- During % the sign of answer is sign of first operand
   ``` 14%-3 =2 , -14%3 = -2 ```

## RELATIONAL OPEARTORS
Compares two quantities

Result is either one(non zero or zero( true or false)

| Operator | Meaning                |
|----------|------------------------|
| <        | Less than              |
| <=       | Less than or equal to  |
| >        | Greater than           |
| >=       | Greater than or equal to|
| ==       | Equal to               |
| !=       | Not equal to           |

- used in decision control strucures and loops

## Logical Operators

| Operator | Meaning                |
|----------|------------------------|
| &&       | Logical AND            |
| \|\|     | Logical OR             |
| !        | Logical NOT            |

| Op1   | Op2   | AND (&&) | OR (\|\|) | NOT (!Op1) |
|-------|-------|----------|-----------|------------|
| false | false | false    | false     | true       |
| false | true  | false    | true      | true       |
| true  | false | false    | true      | false      |
| true  | true  | true     | true      | false      |

## Shorthand Operators

| Operator | Meaning               | Example          |
|----------|-----------------------|------------------|
| +=       | Addition assignment   | a += b => a = a + b |
| -=       | Subtraction assignment| a -= b => a = a - b |
| *=       | Multiplication assignment | a *= b => a = a * b |
| /=       | Division assignment   | a /= b => a = a / b |
| %=       | Modulus assignment    | a %= b => a = a % b |
| ^=       | Exponentiation assignment | a ^= b => a = a ^ b |
| &=       | Bitwise AND assignment| a &= b => a = a & b |
| >>=      | Right shift assignment| a >>= b => a = a >> b |
| <<=      | Left shift assignment | a <<= b => a = a << b |
| !=       | Not equal assignment  | a != b => a = a ! b |

## Increment operators (unary)
Increment(++) Prefix operator
  - ++a  => a= a+1 or a+=1;
  - First 1 is added to variable the it is used in expression.
  - Ex.  a=5;     b= ++a;
	Here first a becomes 6 and then 6 is assigned to b
Increment(++) Postfix operator
  - a ++ => a= a+1 or a+=1;
  - First old value is used in expression and then1 is added to variable.
  - Ex.  a=5;      b= a++;
	Here first 5 is assigned to b and the value of a is incremented.

## Decrement opearators (unary)
Decrement(--) Prefix operator
  - --a  => a= a-1 or a-=1;
  - First 1 is added to variable the it is used in expression.
  - Ex.  a=5;    b= --a;
	Here first a becomes 4 and then 4 is assigned to b
Decrement(--) Postfix operator
  - a -- => a= a-1 or a--=1;
  - First old value is used in expression and then1 is added to variable.
  - Ex.  a=5;      b= a--;
		Here first 5 is assigned to b and the value of a is decremented.

# Postfix and Prefix Increment/Decrement Operators in C/C++

In C/C++, expressions can utilize both postfix and prefix increment/decrement operators. However, it's important to understand their behavior and limitations:

## Postfix Operator

The postfix increment/decrement operator evaluates the expression using the original value of the variable and then increments/decrements it.

```c
int x, y = 3;
x = y++; // Results in compile-time error: "lvalue required"
```

In the example above, `y++` is attempting to increment the value of `y` after it's used in the assignment to `x`. However, since postfix increment can't be applied to the result of an expression (it requires an lvalue), it results in a compile-time error.

## Prefix Operator

In contrast, the prefix increment/decrement operator first increments/decrements the value of the variable and then evaluates the expression using the changed value.

```c
int x, y = 3;
x = ++y; // Valid expression, x will be 4 and y will be 4
```

Here, `++y` increments `y` to 4, and then assigns that value to `x`.

## Limitation with Floats

It's important to note that postfix and prefix operators cannot be used with floating-point numbers. They are limited to integral types.

These operators are powerful tools for manipulating variables in C/C++ programs, but their usage should be understood to avoid unexpected behavior or compilation errors.

## CONDITIONAL OPEARTOR ( ? : )
### Ternary Operator (`?:`) in C/C++

The ternary operator, also known as the conditional operator, is a concise way of expressing conditional statements in C/C++.

## Syntax

```c
variable = condition ? expr1 : expr2;
int x = 10, y = 20, result;

// Using ternary operator
result = (x > y) ? x : y; // result will be 20

// Equivalent to:
// if (x > y)
//     result = x;
// else
//     result = y;

```

- Limitation of ? :
  After ? Or : one statement can occur.

## BITWISE OPEARTORS :
- Used in device drivers programming.
- Used to manipulate data at bit level.
- Only applicable for int & char data types
### Bitwise Operations Table

## Bitwise Operators

| Operator | Meaning                |
|----------|------------------------|
| &        | Bitwise AND            |
| \|       | Bitwise OR             |
| ~        | One’s complement (NOT) |
| >>       | Right shift            |
| <<       | Left shift             |
| ^        | Bitwise XOR            |

- -ve numbers are stored in 2’s compliment form of +ve number.
- In bitwise AND,OR,Ex-Or both the operands should be of same data type(int or char)
- Truth Table for Bitwise AND,OR & Ex-OR


| Op1 | Op2 | &   | \|  | ^   |
|-----|-----|-----|-----|-----|
| 0   | 0   | 0   | 0   | 0   |
| 0   | 1   | 0   | 1   | 1   |
| 1   | 0   | 0   | 1   | 1   |
| 1   | 1   | 1   | 1   | 0   |


### Complement (`~`) Operator

The complement (`~`) operator is a unary operator in C/C++ that performs bitwise negation. It flips each bit of the operand.

- `0` becomes `1`.
- `1` becomes `0`.

### Right Shift (`>>`) Operator

The right shift (`>>`) operator is a binary operator in C/C++ used to shift the bits of a number to the right by a specified number of positions.

- `Op >> n;`
- All bits are shifted to the right by `n` positions or bits.
- The rightmost `n` bits will be lost, and the leftmost vacated `n` bits will be filled with `0`.
- Equivalent to dividing by `2^n`.
- For example, `32 >> 1` gives `16`.

### Left Shift (`<<`) Operator

The left shift (`<<`) operator is a binary operator in C/C++ used to shift the bits of a number to the left by a specified number of positions.

- `Op << n;`
- All bits are shifted to the left by `n` positions or bits.
- The leftmost `n` bits will be lost, and the rightmost vacated `n` bits will be filled with `0`.
- Equivalent to multiplying by `2^n`.
- For example, `16 << 1` gives `32`.

These operators are fundamental in bitwise operations and are commonly used for various purposes such as optimization, manipulation of data structures, and implementing algorithms.

## SPECIAL OPEARTORS
| Operator | Meaning                     |
|----------|-----------------------------|
| ,        | Comma operator              |
| sizeof() | Size of operator            |
| & , *    | Pointer related operators   |
| . , ->   | Structure related operators |

- Comma(,) operator
- Used to link expressions together, expr evaluated from left to right and value of rightmost expr is total value of expr.
      EX. Value =(x=10,y=5,x+y); then value =15;

- Left side of , is always evaluated as void ,i.e value of rightmost expr becomes value of ,separated expression.
### sizeof( ) operator
- Compile time operator. i.e value is evaluated at compile time only and value it produces is treated as a constant within your program.
- Returns no of bytes the operand occupies.
- Operand may be variable, constant, data type qualifier.
- Ex. m= sizeof(int);  result : m=4
- It is generally used to generate portable code that depends on size of built in datatypes.

### Assignment operator (=) 
Assigns result of expression to variable.
    Ex . v = expr; here v must be varibale
    Ex.  a+b = expr;   //Lvalue required error
  Here a+b is not variable, so it can not store value.
### New operator (new )
Used to allocate memory dynamically
    Ex.  int *p = new int;
### Delete operator ( delete)
Use to release/free memory dynamically
    Ex. delete p;

