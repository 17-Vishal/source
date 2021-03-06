---
date: 2020-09-01
linktitle: Lambda Expressions
menu:
  main:
    parent: java
title: Lambda Expressions in Java
weight: 8
url: /java/lambda-expressions
description: It is an anonymous function which doesn't belong to any class nor a name. It provides a concise way to show a method or interface.
keywords:
  - java
  - lambda
tags: [Java]  
---
## 1. Lambda Expressions

### 1.1 Introduction
- Lambda expression is the fundamental approach to **functional programming** in Java.
- It is an anonymous function which doesn’t belong to any class nor does it have a name.
- It provides a concise way to show a method or interface.
- Provides implementation of **functional interface**.

### 1.2 Syntax
`Parameter(s) -> body of expression`

### 1.3 Characteristics
- **Optional type declaration** - Declaration of parameter type is not required. It means when declaring parameters we don't have to declare their type.
- **Optional parentheses** - Required when multiple parameters are used. It means we don’t have place parentheses when only a single parameter is passed
- **Optional curly braces** - Only to be used when the expression body contains multiple statements and is not necessary when the body contains only one statement.
- **Optional return keyword** - Automatically returns the value when body contains one expression to return it. It means when only one expression returns the value then we dont need to add return keyword before it.

### 1.4 Parameter Types

- Zero Parameters - No parameters are passed.

```
( ) -> System.println("No Parameters")
```

- One Parameter - Only one parameter is passed.

```
(x) -> System.println("One Parameter: " + x)
```

- Multiple Parameters - Multiple parameters are passed.

```
(x,y) -> System.println("Multiple Parameters: " + x + " " + y);
```


### 1.5 Lambda Expression Example
Accepts two values x, y and returns the product of those two numbers.

```
(x, y) -> x * y
```
             
## 2. Functional Interface

### 2.1  Introduction
- It is an interface which contains only one abstract method.
- It can have any number of default or static methods.

Examples: `FileFilter`, `Comparators`, `Runnable` etc.

### Example
```java
import java.util.*;

// Functional Interface
interface Addition {
    void answer(int x, int y); // Abstract function
}
public class Main {
    public static void main(String args[]) {
        Addition obj = (int x, int y) - > System.out.println(x + y);
        obj.answer(25, 25);
    }
}
```
Output:
```
50
```

## 3. Lambda Variable Capture
Lambda expressions can access variables declared outside the lambda function under certain conditions.

- Local Variables
- Instance Variables
- Static Variables
    
### Local Variable
```java
import java.io.*;


interface abst {
    void local(String s);
}


class main {
    public static void main(String[] args) {

        String text1 = "bcbcc"; // Local Variable

        abst obj = (String a) - > System.out.println(a);

        obj.local(text1);
    }
}
```
Output:
```
bcbcc
```

### Instance Variable and Static Variable
File: Lambda.java
```java
import java.io.*;

interface Interf {
    void print();
}
public class Lambda {
    int x; // instance variable
    static int y = 100; // static variable
    Lambda(int x) {
        this.x = x;
    }
    void show() {

        Interf test = () - > {

            System.out.println("Value of x = " + x);
            System.out.println("Value of y = " + y);
        };
        test.print();
    }
    public static void main(String arg[]) {
        Lambda obj = new Lambda(50);
        obj.show();
    }
}
```
Output:
```
$ javac Lamda.java
$ java Lamda
Value of x = 50
Value of y = 100
```

## 4. Method reference in Lambda
Method reference is used to give reference to methods in the functional interface. It makes the code more concise and much more reading friendly.

### 4.1 Types of method references

- Static Method Reference
- Instance Method Reference
- Constructor Reference                              

### Example of Static Method Reference
```java
import java.io.*;
interface abst {
    void local(int x, int y);
}

public class Test {

    public static void adding(int x, int y) {
        System.out.println("Sum = " + (x + y));
    }
}


class Example {
    public static void main(String[] args) {

        abst ref = Test::adding;
        ref.local(30, 30);

        //output - Sum = 60
    }
}
```

### Example of Instance Method Reference
```java
import java.io.*;


interface abst {
    void local(int x, int y);
}

public class Test {

    public void adding(int x, int y) {
        System.out.println("Sum = " + (x + y));
    }
}


class Example {
    public static void main(String[] args) {

        Test add = new Test();
        abst ref = add::adding;
        ref.local(30, 30);

    }
}
```

### Example of Constructor Reference
File : Test.java
```java
import java.io.*;

interface Interf {
    Hello getMessage(String s);
}

class Hello {
    Hello(String s) {
        System.out.println(s);
    }
}

public class Test {
    public static void main(String[] args) {
        Interf obj = Hello::new;
        obj.getMessage("Hello World");
    }
}
```
Output:
```
$ javac Test.java
$ java Test
Hello World
```

## Miscellaneous Code Examples

#### For each loop in lambda form
```java
import java.util.*;
public class Example {

    public static void main(String[] args) {

        List < Integer > list = new ArrayList < Integer > ();
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.add(5);

        list.forEach((n) - > System.out.println(n));
    }
}
```
Output:
```
2
3
4
5
```

#### Filtering Collection Data Using Lambda Expression
```
import java.util.*;  
import java.util.stream.Stream;


class Product{  
 	 
	String brand;  
	float price;  
	public Product(String brand, float price) {  
    	super();  

    	this.brand = brand;  
    	this.price = price;  
	}  
}  
public class Test  {  
	public static void main(String[] args)
	{  
		List<Product> lst=new ArrayList<Product>();  
        	lst.add(new Product("Asus",10000));  
        	lst.add(new Product("Dell",20000));  
    	       	lst.add(new Product("Rogue",30000));  
		lst.add(new Product("Mac Book",40000));  
        
		Stream<Product> data = lst.stream().filter(p -> p.price > 15000);  
     	 
            	data.forEach(  product -> System.out.println(product.brand+": "+product.price));  
   	}  
} 

```
Output:
```
$ javac Test.java
$ java Test

Dell: 20000.0
Rogue: 30000.0
Mac Book: 40000.0
```
