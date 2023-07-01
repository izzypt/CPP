# CPP
This is a repo that holds the basics and functionalities of CPP. It serves as the foundation for the future CPP modules repos.

# Table of Contents

- [NameSpaces](#namespaces)
- [Const](#const)
- [Typedef and aliases](#typedef)
- Classes
- Member Functions
- Stdio Streams
- Initialization Lists
- Static
- ...

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
