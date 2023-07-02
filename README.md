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
- [Typedef and aliases](#typedef)
- [Arrays and Vectors](#arraysandvectors)
- [Classes](#oop)
- [Member Attribute and Member Functions](#members)
- Stdio Streams
- Initialization Lists
- Static
- Structure of a C++ Program
- Strings in C++
- Pointers and References
- OOP - Classes and Objects
- Polymorphism
- Smart Pointers
- Standard Template Library (STL)
- I/O Stream
- Exception Handling

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

<a href="#members"></a>
# Member Attributes and Member Functions
