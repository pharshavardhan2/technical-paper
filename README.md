# Basic Datatypes and data structures in Java
## Datatypes:
- Datatype describes the values that can be stored by the variable and the type of operations that can be done on it. All datatypes in java can be grouped into two categories.
  1. Primitive datatypes
  2. Reference datatypes
### Primitive datatypes:
- A variable of primitive datatype stores the actual value. All values of primitive datatypes are stored in stack.
- Primitive datatypes are predefined in Java language specification i.e, we cannot create new primitive types.
- Each datatype has a size prededined in JVM.
- When we assign a primitive variable to another variable of same type, the actual value is copied to new variable.
```java
int marks1 = 90;
int marks2 = marks1;     // here java checks the value contained in marks1, and creates a new value 90 and stores it in marks2
```
- There are eight primitive datatypes in java.
  #### Integer types:
  ##### byte:
  - It has size of 1 byte(8 bits) and can store whole numbers from -128(-2<sup>8-1</sup>) to 127(2<sup>8-1</sup>-1).
  ```java
  byte smallNo = -30;   // byte, short are used when there are constraints on storage space
  ```
  ##### short:
  - It has size of 2 bytes(16 bits) and can store whole numbers from -32768(-2<sup>15</sup>) to 32767(2<sup>15</sup>-1).
  ```java
  short mediumNo = 4000;
  ```
  ##### int:
  - It has size of 4 bytes(32 bits) and can store whole numbers from -2<sup>31</sup> to 2<sup>31</sup>-1. It is prefered integer datatype.
  - By default, java assumes an integer literal as `int` datatype.
  ```java
  int normalNo = -327582;
  ```
  ##### long:
  - It has size of 8 bytes(64 bits) and can store whole numbers from -2<sup>63</sup> to 2<sup>63</sup>-1.
  - Use **L** or **l** at the end of integer literal to make it a `long` type.
  ```java
  long bigNo = -3858385997358L;
  ```
  > Use underscore( \_ ) to separate digits of big number to make it more readable.
  ```java
  long bigNo = -385_385_903_883L;
  ```
  #### Decimal types:
  - Used to represent decimal values. As there are infinite decimal numbers in any given range, no storage space is enough to represent all values. 
  - Java uses IEEE 754 floating point representation. Precision represents the maximum number of digits that can be represented after decimal point.
  - You can learn more about range of values [here](https://docs.oracle.com/javase/specs/jls/se7/html/jls-4.html#jls-4.2.3).
  ##### float:
  - It has size of 4 bytes and precision of 7 decimal digits.
  - Use **f** or **F** at the end of decimal literal to make it `float` type.
  ```java
  float lessPrecisePi = 3.14f;
  ```
  ##### double:
  - It has a size of 8 bytes and precision of 15 digits. `double` type is prefered over `float` and is the default type for decimals in java.
  ```java
  double Pi = 3.141_592_653_589;
  ```
