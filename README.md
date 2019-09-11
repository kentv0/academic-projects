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
Type Casting is assigning a value of one type to a variable of another type and are classified into two types:
1. Widening Casting (Implicit)
2. Narrowing Casting (Explicitly done)
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
Variables
------
Any information stored is stored in an address of the computer. Instead of remembering the complex address of the stored information, the address can be named. The naming of an address is known as a variable. Variable is the name of memory location. Java defines mainly three kind of variables:
1. Instance Variables
2. Static Variables
3. Local Variables
### 1. Instance Variables
Instance variables are variables that are declare inside a class but outside any method,constructor or block. Instance variable are also variable of object commonly known as field or property. They are referred as object variable. Each object has its own copy of each variable and thus, it doesn't effect the instance variable if one object changes the value of the variable.
* E.g.
    ```java
    class Customer {

        String name;    // Instance variable of Customer class
        int id;         // Instance variable of Customer class
    }
    ```
### 2. Static Variables
Static are class variables declared with static keyword. Static variables are initialized only once. Static variables are also used in declaring constant along with final keyword.
* E.g.
    ```java
    class Customer {

        String name;
        int id;
        static int storeCode = 1234;    // Each object of Customer class will share the storeCode property.
    ```
* Static Variable are also known as class variable.
* Static means to remain constant and will be constant for all the instances created for that class.
* Static Variable need not to be called from an object, instead is called by ```classname.staticVariableName```
* A Static Variable can never be defined inside a method, e.g. it can never be a local variable.
### 3. Local Variables
Local Variables are declared in a method, constructor, or block. Local Variables are initialized when the method, constructor, or block is started and is destroyed once it is ended. Local Variable reside in stack. Access modifiers are not used for Local Variable.
* E.g.
    ```java
    int getPrice(String item) {
    
        int price;  // Local variable
        price = item * 5;
        return price;
    }
    ```
Arrays
------
An array is a collection of similar data types. Array is a container object that hold values of homogeneous type. It is also known as a static data structure because the size of an array must be specified at the time of its declaration. An array can be either primitive or reference type. It gets memory in heap area. Index of array starts from zero to ```size - 1```.
### Declaration
* Both are valid syntax for array declaration, but the first is more readable.
    ```java
    datatype[] identifier;
    ```
    OR
    ```java
    datatype identifier[];
    ```
* E.g.
    ```java
    int[] arr;
    char[] arr;
    short[] arr;
    long[] arr;
    int[][] arr;   // Two dimensional array
     ```
### Initialization
The ```new``` operator is used to initialize an array.
* E.g.
    ```java
    int[] arr = new int[5];    // This creates an empty array named "arr" of integer type whose size is 5
    ```
    OR
    ```java
    int[] arr = {1, 2, 3, 4, 5};  // This creates an array named "arr" whose elements are given
    ```
### Accessing
Array index starts from 0.
* To access ```nth``` element of an array:
    ```java
    arrayName[n - 1];
    ```
* To find the length of an array use ```array_name.length```. There are no trailing parenthesis for length. It is not ```length()```.
### Foreach (or enhanced for loop)
Foreach is a special type of for loop to access elements of an array. Using foreach loop you can access the complete array sequentially without using the index of an array.
* E.g.
    ```java
    ...
        int[] arr = {1, 2, 3, 4};
        for(int x : arr) {
            System.out.println(x);
        }
    }
    ```
    Output:
    ```tcsh
    1
    2
    3
    4
    ```
Multi-Dimensional Arrays
------
A multi-dimensional array is very much similar to a single dimensional array. It can have multiple rows and multiple columns unlike single dimensional array, which can have only one full row or one full column.
### Declaration
* Both are valid syntax for multi-dimensional array declaration, but the first is more readable.
    ```java
    datatype[][] identifier;
    ```
    OR
    ```java
    datatype identifier[][];
    ```
### Initialization
The ```new``` operator is used to initialize a Multi-Dimensional array.
* E.g.
    ```java
    int[][] arr = new int[5][5];    // 5 x 5 is the size of the multi-dimensional array
    ```
    OR
    ```java
    // 3 x 5 is the size of the multi-dimensional array
    int[][] arr = {{1, 2, 3, 4, 5}, {6, 7, 8, 9, 10}, {11, 12, 13, 14, 15}};
    ```
### Accessing
For both row and column, the index begins from 0.
* To access ```mth``` row, ```nth``` column element of a multi-dimensional array:
    ```java
    arrayName[m - 1][n - 1]
    ```
* E.g.
    ```java
    int[][] arr = {{1, 2, 3, 4, 5}, {6, 7, 8, 9, 10}, {11, 12, 13, 14, 15}};
    System.out.println("Element at (2,3):" + arr[1][2]);
    ```
    Output:
    ```tcsh
    8
    ```
Jagged Arrays
------
Jagged means to have an uneven edge or surface. In java, a Jagged Array means to have a multi-dimensional array with uneven size of rows in it.
* E.g.
    ```java
    int[][] arr = new int[3][];
    arr[0] = new int[3];
    arr[1] = new int[4];
    arr[2] = new int[5];
    ```
Operators
------
Java provides a rich set of operators environment. Java operators can be divided into following categories:
* Arithmetic Operators
* Relation Operators
* Logical Operators
* Bitwise Operators
* Assignment Operators
* Conditional Operators
* Misc Operators
### Arithmetic Operators
* Arithmetic operators are used in mathematical expression in the same way that are used in algebra.

    | Operator | Description                        |
    |:--------:|:-----------------------------------|
    | ```+```  | Adds two operands                  |
    | ```-```  | Subtract second operand from first |
    | ```*```  | Multiply two operand               |
    | ```/```  | Divide numerator by denominator    |
    | ```%```  | Remainder of division              |
    | ```++``` | Increment value by one             |
    | ```--``` | Decrement value by one             |
### Relation Operators
* The following table shows all relation operators supported by Java

    | Operator | Description                                                     |
    |:--------:|:----------------------------------------------------------------|
    | ```==``` | Check if two operand are equal                                  |
    | ```!=``` | Check if two operand are not equal                              |
    | ```>```  | Check if left operand is greater than right operand             |
    | ```<```  | Check if left operand is less than right operand                |
    | ```>=``` | Check if left operand is greater than or equal to right operand |
    | ```<=``` | Check if left operand is less than or equal to right operand    |
### Logical Operators
* The following table shows the three logical operators supported by Java

    | Operator     | Description | Example (a = 1, b = 0)  |
    |:------------:|:------------|:------------------------|
    | ```&&```     | Logical AND | ```(a && b)``` is false |
    | &#124;&#124; | Logical OR  | (a || b) is true        |
    | ```!```      | Logical NOT | ```(!a)``` is false     |
### Bitwise Operators
* Bitwise operators can be applied to the integer types ```long```, ```int```, ```short```, ```char``` and ```byte```
* The following table shows all bitwise operators supported by Java

    | Operator | Description          |
    |:--------:|:---------------------|
    | ```&```  | Bitwise AND          |
    | &#124;   | Bitwise OR           |
    | ```^```  | Bitwise exclusive OR |
    | ```<<``` | Left shift           |
    | ```>>``` | Right shift          |
* Truth Table for ```&```, ```|```, and ```^``` bitwise operators

    | ```a``` | ```b``` | ```a & b``` | a &#124; b  | ```a ^ b``` |
    |:--------|:--------|:------------|:------------|:------------|
    | 0       | 0       | 0           | 0           | 0           |
    | 0       | 1       | 0           | 1           | 1           |
    | 1       | 0       | 0           | 1           | 1           |
    | 1       | 1       | 1           | 1           | 0           |
* The bitwise shift operators shifts the bit value. The left operand specifies the value to be shifted and the right operand specifies the number of positions that the bits in the value are to be shifted. Both operands have the same precedence. E.g.
    ```java
    a = 0000100
    b = 2
    a << b = 0010000
    a >> b = 0000001
    ```
### Assignment Operators
* The following table shows all assignment operators supported by Java

    | Operator | Description                                                              | Example                              |
    |:--------:|:-------------------------------------------------------------------------|:-------------------------------------|
    | ```=```  | Assign right operand to left operand                                     | ```a = b```                          |
    | ```+=``` | Assign left operand to the sum of left operand and right operand         | ```a += b``` or ```a = a + b``` |
    | ```-=``` | Assign left operand to the difference of right operand from left operand | ```a -= b``` or ```a = b - a``` |
    | ```*=``` | Assign left operand to the product of left operand with right operand    | ```a *= b``` or ```a = a * b``` |
    | ```/=``` | Assign left operand to the quotient of left operand with right operand   | ```a /= b``` or ```a = a / b``` |
    | ```%=``` | Assign left operand to the modulo of left operand with right operand     | ```a %= b``` or ```a = a % b``` |
### Conditional Operators
Also known as the ternary operator and used to evaluate ```Boolean``` expression
* E.g.
    ```java
    expression1 ? expression2 : expression3
    ```
    If the condition of ```expression1``` is true? Then evaluate ```expression2``` : Otherwise evaluate ```expression3```
### ```instanceOf``` Operator
* Used for object reference variables. The operator checks whether the object is of a particular type (class type or interface type)

### Misc Operators
* There are few other operators supported by the Java programming language.

Object-Oriented Programming (OOP) Concepts
======
Styles of Programming Languages
------
Programming languages can be classified into 3 primary types:
1. Unstructured Programming Languages
2. Structured Programming Languages
3. Object-Oriented Programming Languages
### 1. Unstructured Programming Languages
The earliest of all programming language were unstructured programming language. It has a sequentially flow of control. Code is repeated through out the program.
* E.g. a very elementary code of banking application in unstructured Programming language will have two variables of one account number and another for account balance
    ```java
    int accountNumber = 20;
    int accountBalance = 100;
    
    accountBalance = accountBalance + 100;
    
    // Same two lines repeated below
    printf(“Account Number = %d, accountNumber);
    printf(“Account Balance = %d, accountBalance);
    
    accountBalance = accountBalance - 50;
    
    printf(“Account Number = %d, accountNumber);
    printf(“Account Balance = %d, accountBalance);
    
    accountBalance = accountBalance - 10;
    
    printf(“Account Number = %d, accountNumber);
    printf(“Account Balance = %d, accountBalance);
    ```
    Any deposit or withdraw operation requires continuously repeating lines of code
### 2. Structured Programming Languages
Structured programming language has a non-sequentially flow of control. Repeated lines on the code were put into structures such as functions or methods and allowed for re-use of code.
* E.g.
    ```java
    // Commonly repeated code defined into a function
    void showData() {
        printf(“Account Number = %d, accountNumber);
        printf(“Account Balance = %d, accountBalance);
    }
    ```
    ```java
    int accountNumber = 20;
    int accountBalance = 100;
    
    accountBalance = accountBalance + 100;
    
    // Call being made to the function
    showData();
    
    accountBalance = accountBalance - 50;
    
    showData();
    
    accountBalance = accountBalance - 10;
    
    showData();
    ```
    Whenever needed, a simple call to the function is made.
### 3. Object-Oriented Programming Languages
Object-oriented programming language combines data & action together. The very basic characteristic in any software program is having data and performing certain operation on that data.
* E.g. The same code will have the same data and some action performed on that data.
    ```java
    Class Account {
        // Data
        int accountNumber;
        int accountBalance;
        
        // Action
        public void showData() {
            System.out.println(“Account Number = ” + accountNumber);
            System.out.println(“Account Balance = ” + accountBalance);
        }
    }
    ```
* Combining data and action has many advantages over structural programming such as...
    * Inheritence
    * Polymorphism
    * Encapsulation
    * Abstraction

Objects and Classes
------
* The complete Java programming language builds on classes and objects. It uses real world approach to solve a problem.
* In Java everything is encapsulated under classes. Class is the core of the Java programming language. Class can be defined as a template/blueprint that describe the behaviors/states of a particular entity. A class defines a new data type and once defined, this new data type can be used to create object of that data type. Object is an instance of class.

### Declaration
* A class is declared using the ```class``` keyword.
* A class contain both the data and the code that operate on that data. The data or variables defined within a class are called **instance variables** and the code that operates on this data are known as **methods**. Thus, the instance variables and methods are known as class members. A class is also known as a user defined data type.

### Rules
* A class can only be declared with the ```public``` access modifier or default (none).
* A class can either be declared as ```abstract```, ```final```, or concrete (none).
* A class must be declared with the keyword ```class``` and must be followed by a legal identifier.
* (Optional) It may extend from one parent class. By default, it will extend ```java.lang.Object```.
* (Optional) It may implement any number of comma-separated ```interface```.
* Class variables and methods are declared within a set of curly braces ```{}```.
* Each ```.java``` source file may only contain one ```public class```, but may contain any number of default visible classes.
* The name of the source file must match the name of the ```public class```.

Method Overloading
------
Constructor in Java
------
this keyword
------
Garbage Collection
------
Java Modifiers
------
Inheritance
------
Aggregation
------
Method Overriding
------
Runtime Polymorphism
------
instanceof Operator
------
Command line Argument
------
Package
------
Abstract Class
------
Interface
------
Nested Classes
------

Advanced Topics
======
