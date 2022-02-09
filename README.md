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
  1. ##### byte:
  - It has size of 1 byte(8 bits) and can store whole numbers from -128(-2<sup>8-1</sup>) to 127(2<sup>8-1</sup>-1).
  ```java
  byte smallNo = -30;   // byte, short are used when there are constraints on storage space
  ```
  2. ##### short:
  - It has size of 2 bytes(16 bits) and can store whole numbers from -32768(-2<sup>15</sup>) to 32767(2<sup>15</sup>-1).
  ```java
  short mediumNo = 4000;
  ```
  3. ##### int:
  - It has size of 4 bytes(32 bits) and can store whole numbers from -2<sup>31</sup> to 2<sup>31</sup>-1. It is prefered integer datatype.
  - By default, java assumes an integer literal as `int` datatype.
  ```java
  int normalNo = -327582;
  ```
  4. ##### long:
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
  5. ##### float:
  - It has size of 4 bytes and precision of 7 decimal digits.
  - Use **f** or **F** at the end of decimal literal to make it `float` type.
  ```java
  float lessPrecisePi = 3.14f;
  ```
  6. ##### double:
  - It has a size of 8 bytes and precision of 15 digits. `double` type is prefered over `float` and is the default type for decimals in java.
  ```java
  double Pi = 3.141_592_653_589;
  ```
  > Be careful when doing arithmetic operations on decimal types. Use `BigDecimal` type or equivalent value in integer types for precise applications such as banking, scientific etc.
  > Decimal literals can also be represented using scientific notation
  ```java
  float pi = 314e-2f;
  double pi = 3_141_592_653_589E-12;
  ```
  7. #### char:
  - It has size of 2 bytes. It is used to represent single 16 bit unicode character.
  - Use single quotes `''` to enclose char literal. Represent literals as 'A' or unicode escape like `\u0c05`(అ).
  - Range is `\u0000` to `\uffff`.
  ```java
  char ch1 = 'A';
  char ch2 = '\u0c05';
  char ch3 = 'అ';
  ```
  8. #### boolean:
  - It has size of 1 bit and represents only two values `true` or `false`. Used mostly for logical operations.
  - Java doesn't consider any other datatype as truthy or falsy values(which is the case in python or js).
  ```java
  boolean isAdult = true;
  ```
> Compiler assigns reasonable default values for variables that are declared but not initialized. But it is a bad programming practice to rely on this and local variables are not assigned any default values, also leads to compiler errors.

Datatype | Size | Default value
:--- | :---: | :---:
byte | 1 byte | 0
short | 2 bytes | 0
int | 4 bytes | 0
long | 8 bytes | 0L
float | 4 bytes | 0.0f
double | 8 bytes | 0.0
char | 2 bytes | '\u0000'
boolean | 1 bit | false
any object | NA | null

### Reference datatypes:
- All objects in java are considered to be reference type. Many reference types come packaged as part of java libraries. User can define their own reference datatype.
- Reference variable stores the address of the data. Data can be a complex structure which contains variables of other data types. Data is actually stored on heap.
- `null` is a special value that is used to indicate an object(reference) doesn't contain any value or is currently unavailable.
- We will use `String` object to illustrate properties of reference types. We can create new objects using `new` keyword. When we do this, some space is allocated for data in memory(instantiation) and initialize it by assigning some value.
```java
String firstName = new String("harsha");  // instantiation and initialization with value "harsha"
String firstName = "harsha";     // String in java can be created without using new keyword and should be enclosed in double quotes
```
- Be careful when comparing two reference variables or using them in assignement operations. `==` checks if addresses stored in reference variables are same. Use method `equals` to check if actual values are same.
```java
String name1 = "harsha";      // stores "harsha" on heap and address of that memory is stored in name1
String name2 = name1;         // copies the memory address stored in name1 and stores it in name2. So both name1 and name2 point to same data
String name3 = "harsha";      // creates new "harsha" on heap and address of that is stored in name3
// checks addresses
System.out.println(name1 == name2);  // prints true
System.out.println(name1 == name3);  // prints false
// checks values
System.out.println(name1.equals(name2));  // prints true
System.out.println(name1.equals(name3));  // prints true
```
