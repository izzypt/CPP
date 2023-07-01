# CPP
This is a repo that holds the basics and functionalities of CPP. It serves as the foundation for the future CPP modules repos.

# Table of Contents

- [NameSpaces](#namespaces)
- Classes
- Member Functions
- Stdio Streams
- Initialization Lists
- Static
- Const
- ...

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
