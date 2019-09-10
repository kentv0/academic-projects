Java Programming
======
Table of Contents
======
[History of Java](#history-of-java)

[Object Oriented](#object-oriented)

History of Java
======

Basic Java
======
Data Types
------
Data types specify size and the type of values that can be stored in an identifier. Java classifies data types into two categories:
1. Primitive Data Type
2. Non-Primitive Data Type
### 1. Primitive Data Type
* A primitive data type can be of eight types: ```char``` ```boolean``` ```byte``` ```short``` ```int``` ```long``` ```float``` ```double```
* Once a primitive data type is declared, it can ONLY change its value and NEVER its type.
* These eight primitive data type can be put into four groups
    * #### Integer
        ```byte``` : 1 byte(8-bits) integer data type. Value range from -128 to 127. Default value zero.
        
        ```short``` : 2 bytes(16-bits) integer data type. Value range from -32768 to 32767. Default value zero.
        
        ```int``` : 4 bytes(32-bits) integer data type. Value range from -2147483648 to 2147483647. Default value zero.
        
        ```long``` : 8 bytes(64-bits) integer data type. Value range from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807. Default value zero.
    * #### Floating-Point Number
        ```float``` : 4 bytes(32-bits) float data type. Default value ```0.0f```.
        
        ```double``` : 8 bytes(64-bits) float data type. Default value ```0.0d```.
    * #### Characters
        ```char``` : 2 bytes(16-bits) unsigned unicode character. Range 0 to 65,535.
    * #### Boolean
        ```boolean``` :  special type for representing true/false values. They are defined constant of the language.
### 2. Non-Primitive (Reference) Data Type
* A reference data type is used to refer to an object. A reference variable is declare to be of a specific type and that type can never be changed.

Identifiers
------
* All Java components require names. Name used for classes, methods, interfaces and variables are called Identifier. Identifier must follow some rules. Here are the rules:
    * All identifiers must start with either a letter( a to z or A to Z ) or currency character($) or an underscore.
    * After the first character, an identifier can have any combination of characters.
    * A Java ```keyword``` cannot be used as an identifier.
    * Identifiers in Java are case sensitive, foo and Foo are two different identifiers.

Type Casting
------
* Type Casting is assigning a value of one type to a variable of another type and are classified into two types:
### 1. Widening Casting (Implicit)
```byte``` -> ```short``` -> ```int``` -> ```long``` -> ```float``` -> ```double```
* Widening (or Automatic type conversion) take place when...
    * the two types are compatible
    * the target type is larger than the source type
* E.g.
    ```java
    int i = 100;
    long l = i;
    float f = l;
    
    System.out.println("Int value: " + i);
    System.out.println("Long value: " + l);
    System.out.println("Float value: " + f);
    ```
    Output:
    ```tcsh
    Int value: 100
    Long value: 100
    Float value: 100.0
    ```
### 2. Narrowing Casting (Explicitly done)
```double``` -> ```float``` -> ```long``` -> ```int``` -> ```short``` -> ```byte```
* Narrowing (or Explicit type conversion) when you are assigning a larger type value to a variable of smaller type, then you need to perform explicit type casting.
* E.g.
    ```java
    double d = 100.04;
    long l = (long)d;
    int i = (int)l;
    
    System.out.println("Double value: " + d);
    System.out.println("Long value: " + l);
    System.out.println("Int value: " + i);
    ```
    Output:
    ```tcsh
    Double value: 100.04
    Long value: 100
    Int value: 100
    ```
Object Oriented
------
* ### Styles of Programming Languages
    * Unstructured
    * Structured
    * Object-Oriented
* ### Objects and Classes
* ### Method Overloading

Advanced Topics
------


