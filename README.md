# CPP
This is a repo that holds the fundamentals to start working on the CPP modules ahead.

# Intro

![image](https://github.com/izzypt/CPP/assets/73948790/279b4bc2-f369-44dc-95e3-4828bb67460d)

C++ is a programming language that has evolved over time, and different versions, or standards, have been released to introduce new features, improve the language, and ensure compatibility across different implementations. Here's an overview of the major C++ standards:

- C++98: The first standardized version of C++ was known as C++98, released in 1998. This version introduced features like namespaces, exceptions, templates, and the Standard Template Library (STL).

- C++11: Released in 2011, C++11 was a major update to the language. It introduced numerous new features, including lambda expressions, smart pointers, range-based for loops, type inference (using the auto keyword), and the constexpr keyword. C++11 aimed to modernize the language and make it more expressive and efficient.

- C++14: Was released in 2014 as a minor update to C++11. It added several small features and improvements, such as binary literals, generic lambdas, relaxed constexpr restrictions, and improved support for variable templates. The focus of C++14 was on refining and enhancing the language rather than introducing major changes.

- C++17: C++17  was released in 2017. It brought several significant features, including structured bindings, if constexpr, constexpr lambdas, inline variables, and a simplified std::variant type. C++17 also introduced parallel algorithms in the STL, filesystem support, and other library enhancements.

- C++20: Released in 2020, C++20 introduced many new features and enhancements. Some notable additions include concepts (a way to specify type requirements), ranges (a new library for working with sequences of values), coroutines, three-way comparisons, and modules (a new way to organize and manage code). C++20 aimed to improve code readability, simplify common tasks, and provide better support for modern programming techniques.

The evolution of C++ standards is driven by the ISO C++ committee, which consists of experts from academia, industry, and the broader C++ community.

![image](https://github.com/izzypt/CPP/assets/73948790/fc93368b-1e7b-4e5d-bf66-b3e9825c0a3a)


# Table of Contents

- [NameSpaces](#namespaces)
- [Const](#const)
- [Static](#static)
- [Typedef and aliases](#typedef)
- [Stdio Streams](#iostreams)
- [Arrays and Vectors](#arraysandvectors)
- [Classes](#oop)
- [Member Attribute and Member Functions](#members)
- [Initialization Lists](#initializationlist)
- Strings in C++
- [Pointers and References](#pointersandreferences)
- [Passing by value or reference](#valueorreference)
- Standard Template Library (STL)

# Usefull references

- https://www.youtube.com/watch?v=-TkoO8Z07hI&t=3178s&ab_channel=BroCode

<a id="namespaces"></a>
# NameSpaces 

- NameSpaces provides a solution for preventing name conflicts.
- Each entity needs a unique name.
- A namespace allows for identically named entities as long as the namespaces are different.

Examples :

![image](https://github.com/izzypt/CPP/assets/73948790/69f7a8ef-3126-4467-93da-76a25e2e66af)

It will return 0. If I dont specify the namespace, we will use the local version of an entity.

But if I specify the namespace of the variable, like this ```<namespace>::variable``` it will specify the value of the variable within that namespace :

![image](https://github.com/izzypt/CPP/assets/73948790/5d07a8a3-b3d1-4bef-b84f-a851764dbc8b)

It will return 1 for ```first::x``` and 2 for ```second::x```.

<a id="const"></a>
# Const

- The const keyword specifies that a variable's value is constant.
- It tells the compiler to prevent anything from modifying it.

To create a constant variable, just preceed the datatype declaration of the variable with the ```const``` keyword:

![image](https://github.com/izzypt/CPP/assets/73948790/97418b8e-581e-415f-b3c0-0d422d6dae7a)

- If at some point you or someone else tries to change the value of ```PI```, the compier will throw an error.
- 
![image](https://github.com/izzypt/CPP/assets/73948790/b20b25d3-a640-4b04-b619-4ffb120c1ad0)

![image](https://github.com/izzypt/CPP/assets/73948790/f4d89687-ea21-45fd-8f7a-6c63f59bd3f1)

<a id="static"></a>
# Static

In C++, the keyword "static" has multiple uses and can be applied to variables, functions, and class members. Here are the main uses of the "static" keyword:

1. Static Variables:
   - When applied to a variable within a function or method, the "static" keyword gives the variable static storage duration. It means that the variable is initialized only once, and its value persists across multiple function calls. The variable retains its value even after the function or method scope is exited.

      ```cpp
      void countCalls() {
          static int counter = 0;
          counter++;
          cout << "Function called " << counter << " times." << endl;
      }
   
      int main() {
          countCalls();  // Function called 1 times.
          countCalls();  // Function called 2 times.
          countCalls();  // Function called 3 times.
          return 0;
      }
      ```
   
      In the example above, the "counter" variable inside the "countCalls" function is declared as static. It retains its value between function calls and increments with each call. Static variables are often used for maintaining state across function calls or for caching values.

2. Static Functions:
   - When applied to a function, the "static" keyword restricts the function's scope to the translation unit where it is defined. It means the function is not visible outside its source file. Static functions can only be called from other functions within the same file.

      ```cpp
      static void helperFunction() {
          // Function implementation
      }
   
      void publicFunction() {
          // Can call helperFunction()
      }
   
      int main() {
          // Cannot call helperFunction() here
          return 0;
      }
      ```
   
      In the example above, the "helperFunction" is declared as static. It can only be called within the same file, typically for internal implementation details or utility functions not intended to be accessed externally.

3. Static Class Members:
   - When applied to a class member (variable or function), the "static" keyword indicates that the member is associated with the class itself rather than with individual objects of the class. Static class members are shared among all instances of the class.

      ```cpp
      class MyClass {
      public:
          static int count;
      };
   
      int MyClass::count = 0;  // Definition and initialization
   
      int main() {
          MyClass obj1;
          MyClass obj2;
   
          obj1.count = 5;
          cout << obj2.count << endl;  // Output: 5
   
          return 0;
      }
      ```
   
      In the example above, the "count" variable is declared as a static member of the "MyClass" class. It is shared by all instances of the class, and modifying it in one instance reflects the change in other instances. Static class members are often used to store shared data or provide utility functions associated with the class itself rather than individual objects.

These are the primary uses of the "static" keyword in C++. It provides various capabilities such as persistent local variables, restricted visibility of functions, and shared data among class instances.

<a id="typedef"></a>
# Typedef and aliases 

- ```typedef``` is  a reserved keyword used to create a new datatype or an additional name (alias) for an existing data type.
- It helps with readbility and reduces types.

![image](https://github.com/izzypt/CPP/assets/73948790/7d9b8de9-2ab5-4666-ae27-7c30d18b56d0)

- In the picture above, we create the type ```text_t``` which is the same as referencing ```std::string```.

Another example would be :

![image](https://github.com/izzypt/CPP/assets/73948790/f1b8f7ee-5d47-4e3c-9203-782d72232676)

Nowadays, the keyword ```typedef``` has been largely replaced with the ```using``` keyword. (works bettwer w/ templates)


![image](https://github.com/izzypt/CPP/assets/73948790/391964bb-5d1b-4697-bd1a-6a539316fab8)


- This would do the same job

<a id="iostreams"></a>
# Stdio Streams

Let's explore the iostream library in more detail, focusing on the stream insertion (<<) and stream extraction (>>) operators, as well as formatting options using manipulators.

1. Stream Insertion (<<) Operator:
The stream insertion operator (<<) is used for output operations in C++. It allows us to insert data into an output stream, typically std::cout, to be displayed on the console or redirected to another output destination.

Example:
```cpp
int number = 10;
std::string message = "Hello, world!";

std::cout << "The number is: " << number << std::endl;
std::cout << message << std::endl;
```
In this example, we use the << operator to insert the value of `number` and the string `message` into the std::cout stream. The output will be:
```
The number is: 10
Hello, world!
```

2. Stream Extraction (>>) Operator:
The stream extraction operator (>>) is used for input operations in C++. It allows us to extract data from an input stream, typically std::cin, to store it in variables for further processing.

Example:
```cpp
int age;
std::string name;

std::cout << "Enter your age: ";
std::cin >> age;

std::cout << "Enter your name: ";
std::cin >> name;

std::cout << "Welcome, " << name << "! You are " << age << " years old." << std::endl;
```
In this example, we use the >> operator to extract the user's age and name from the std::cin stream. The input provided by the user is stored in the variables `age` and `name`, which are then used for output.

3. Formatting Options with Manipulators:
Manipulators in C++ allow us to modify the format and behavior of the output stream. The iostream library provides several useful manipulators to control various aspects of output formatting. Here are some commonly used manipulators:

- setw: Sets the width of the field for the next output value.
```cpp
#include <iomanip>

int number = 42;
std::cout << "The number is: " << std::setw(5) << number << std::endl;
```
Output:
```
The number is:    42
```

- setprecision: Sets the precision (number of decimal places) for floating-point values.
```cpp
#include <iomanip>

double pi = 3.14159;
std::cout << "The value of pi is: " << std::setprecision(3) << pi << std::endl;
```
Output:
```
The value of pi is: 3.14
```

- fixed: Forces floating-point values to be displayed in fixed-point notation.
```cpp
#include <iomanip>

double number = 123.456789;
std::cout << "The number is: " << std::fixed << number << std::endl;
```
Output:
```
The number is: 123.456789
```

These manipulators, along with many others available in the iostream library, provide greater control over the appearance and formatting of the output, making it easier to present data in a desired format.

By combining the stream insertion (<<) and stream extraction (>>) operators with manipulators, we can perform a wide range of input and output operations while maintaining control over the format and presentation of data.


<a id="arraysandvectors"></a>
# Arrays and vectors

Those are compound types because they are made of another data types.

<ins>Arrays</ins>: A data structure that can hold mutiple values acessed by an index number.
- Collection of elements.
- All elements are of the same type.
- Each element can be accessed directly.

![image](https://github.com/izzypt/CPP/assets/73948790/3f7ea465-6d20-4393-82c4-197c21702c5e)


<a id="oop"></a>
# Classes and Objects

<ins>Classes</ins>:
- Blueprints from which objects are created.
- A user defined data type.
- It has attributes (data)
- It has methods (functions)
- Able to hide data and methods
- Provides a publid interface

<ins>Objects</ins>:
- Created from a class
- Represents an instance of a class


## Declaring a class

```
class Class_Name
{
   //declartion(s);
}
```

Let's say we wanted to create a player class :

```
class Player
{
    //attributes
    std::string name;
    int health;
    int xp;

    //methods
    void talk(std::string text_to_say);
    bool is_dead(void);
}
```

Another example. let's say we wanted to create an Account class:

```
class Account
{
      // Attributes
      std::string name;
      double balance;

      // Methods
      bool withdraw(double amount);
      bool deposit(double amount);
}
```

## Creating objects

If we use the class we created above, creeating an object would be something like:


Approach 1 : Declared just like primitive data types.

```
      Player frank;
      Player hero;
```

Approach 2 : 
- We can also create pointer to objects using the ```new``` keyword. 
- We declare enemy as a pointer to a Player object.
- The ```new``` keyword, dynamically allocated memory on the heap for the player object. This memory must be freed.
- To release the memory allocated with ```new```, you need to use the ```delete``` keyword.
```
Player *enemy = new Player();
delete enemy;
```

Now, let's say we wanted to create objects for our account class :

Approach 1:

```
      Account frank_account;
      Account jim_account;
```
Approach 2:

```
      Account *marry_account = new Account();
      delete mary_account;
```

<a id="members"></a>
# Member Attributes and Member Functions

- Member attributes, also known as member variables or instance variables, are the data elements associated with an object.
- They represent the characteristics or properties that define the object's state.
- These attributes hold values that are unique to each object of a class.

>For example, in a Person class, member attributes could include the person's name, age, and address.

>Each instance of the Person class will have its own set of attribute values, allowing you to store and access specific data associated with each person object.

____________________________________________________________________________________________________________

- Member functions, also known as methods, are the actions or behaviors that objects of a class can perform.
- These functions are associated with the class and operate on its member attributes.
- They encapsulate the logic and operations that manipulate the data and provide functionality to the objects.

>Continuing with the Person class example, member functions could include methods like setName(), setAge(), and getAddress(). These functions allow you to modify or retrieve the attribute values of a Person object.

>Member functions are defined within the class definition and can access the member attributes of the class. They can perform computations, validate data, modify the object's state, or return information based on the object's attributes.

```
#include <iostream>
#include <string>

class Person {
private:
    std::string name;
    int age;
    std::string address;

public:
    void setName(const std::string& newName) {
        this->name = newName;
    }

    void setAge(int newAge) {
        this->age = newAge;
    }

    void setAddress(const std::string& newAddress) {
        this->address = newAddress;
    }

    std::string getName() const {
        return this->name;
    }

    int getAge() const {
        return this->age;
    }

    std::string getAddress() const {
        return this->address;
    }
};

int main() {
    Person person1;
    person1.setName("John");
    person1.setAge(30);
    person1.setAddress("123 Main St");

    std::cout << "Name: " << person1.getName() << std::endl;
    std::cout << "Age: " << person1.getAge() << std::endl;
    std::cout << "Address: " << person1.getAddress() << std::endl;

    return 0;
}

```

<a id="initializationlist"></a>
# Initialization List

In C++, an initialization list is a syntax used in the constructor definition to initialize the member variables of a class. It allows you to provide initial values to the member variables before the constructor body is executed.

The syntax of an initialization list is as follows:

```cpp
ConstructorName::ConstructorName(parameters) : 
    memberVariable1(initialValue1),
    memberVariable2(initialValue2),
    // ...
{
    // Constructor body
}
```

Here's an example to illustrate the usage of an initialization list:

```cpp
class MyClass {
private:
    int m_value1;
    double m_value2;
    std::string m_value3;

public:
    MyClass(int value1, double value2, const std::string& value3)
        : m_value1(value1), m_value2(value2), m_value3(value3)
    {
        // Constructor body (if needed)
    }
};
```

In this example, the `MyClass` constructor takes three parameters: `value1` of type `int`, `value2` of type `double`, and `value3` of type `const std::string&`.

The initialization list follows the constructor's parameter list. Each member variable is initialized using the syntax `memberVariable(initialValue)`. In this case, `m_value1` is initialized with `value1`, `m_value2` is initialized with `value2`, and `m_value3` is initialized with `value3`.

The advantage of using an initialization list is that it allows for direct initialization of member variables and can improve performance by avoiding unnecessary default constructions and assignments. 

It is particularly useful for initializing member variables that are of non-default constructible types or that are declared as `const` or reference types.

By using an initialization list, you ensure that the member variables are properly initialized before the constructor body is executed, providing a clean and efficient way to initialize your class's member variables.


<a id="pointersandreferences"></a>

# Pointers and References

Pointers:
- Pointers are variables that store memory addresses.
- They are denoted by the asterisk (*) symbol when declaring the pointer type.
- Pointers can be assigned the address of another object or null (nullptr) if they don't currently point to any valid memory location.
- Pointers can be reassigned to point to different objects throughout their lifetime.
- Dereferencing a pointer (using the asterisk (*) operator) allows access to the value stored at the memory address it points to.
- Pointers can be explicitly modified to point to a different object or memory location.
- Pointers can be used for dynamic memory allocation and deallocation using `new` and `delete` operators (in C++).

References:
- References are aliases or alternative names for existing objects.
- They are declared by using an ampersand (&) symbol after the type name.
- References must be initialized when declared and cannot be null.
- Once a reference is bound to an object, it cannot be changed to refer to another object.
- References provide a convenient and cleaner syntax for accessing and manipulating objects without needing to use pointer dereferencing syntax.
- They are useful when you want to pass objects to functions by reference, avoiding object copying.
- References cannot be reassigned to refer to different objects.

When to use pointers:
- When you need the flexibility to dynamically allocate and deallocate memory (e.g., using `new` and `delete`).
- When you want to represent the absence of an object by assigning null (nullptr) to the pointer.
- When you need to change the pointed object during runtime.
- When implementing data structures or algorithms that require fine-grained control over memory and object lifetimes.

When to use references:
- When you want a convenient way to access and modify an existing object without explicitly using pointer dereferencing syntax.
- When passing objects to functions, particularly large objects, to avoid the overhead of object copying.
- When implementing operator overloading to provide a more intuitive syntax.

It's worth noting that references can also be used in certain cases where pointers are used, but references offer a safer and more convenient alternative when there is no need for the flexibility provided by pointers.

<a id="valueorreference"></a>
# Passing by value or reference

Passing data between functions or objects in C++ can be done either by value or by reference.

1. Passing by Value:
   - When passing data by value, a copy of the data is made and passed to the function or object. Any modifications made to the copied data within the function or object do not affect the original data in the calling context.

      Example:
   
      ```cpp
      void increment(int value) {
          value++;  // Increment the copied value
      }
   
      int main() {
          int num = 5;
          increment(num);
          // The value of 'num' remains unchanged (still 5)
          return 0;
      }
      ```
   
      In the example above, the function `increment` takes an integer parameter `value` by value. Any changes made to `value` inside the function do not affect the original `num` variable in `main()`. This method is useful when you want to work with a local copy of the data without modifying the original value.

3. Passing by Reference:
   - When passing data by reference, instead of making a copy, a reference or pointer to the original data is passed. This allows the function or object to directly access and modify the original data.

      Example:
   
      ```cpp
      void increment(int& value) {
          value++;  // Increment the original value
      }
   
      int main() {
          int num = 5;
          increment(num);
          // The value of 'num' is modified to 6
          return 0;
      }
      ```
   
      In this example, the function `increment` takes an integer reference `value`. Any modifications made to `value` inside the function directly affect the original `num` variable in `main()`. This method is useful when you want to modify the original data or avoid making unnecessary copies of large objects.

Implications:

- Passing by value: Creating a copy of the data can have performance implications, especially for large objects or when called frequently. However, it ensures data immutability and avoids unintended side effects on the original data.
- Passing by reference: It allows direct modification of the original data and can be more efficient for large objects. However, it requires caution since modifications made inside the function affect the original data, potentially leading to unexpected behavior.

In general, passing by value is suitable for small, immutable data types, while passing by reference is more efficient for larger objects that need modification. The choice between the two methods depends on the specific requirements of the program and the desired behavior when interacting with data.

This video also explains more about it : https://www.youtube.com/watch?v=wro8Bb6JnwU&ab_channel=LowLevelLearning
