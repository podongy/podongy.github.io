---
layout: post
title: SOLID
---
## * SRP(Single-Responsibility Principle) 
  - A class should have only one reason to change.
  
## * OCP(Open-Closed Principle)
  - Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification.
  - When a single change to a program results in a cascade of changes to dependent module 
  - “Open For Extension”
    - The behavior of the module can be extended. 
  - “Closed for Modification”.
    - The source code of such a module is inviolate. No one is allowed to make source code changes to it.
    
 ![](https://github.com/podongy/podongy.github.io/blob/master/images/fig_1.jpg)

## * LSP(Liskov Substitution Principle)
  - An object of type T may be substituted with any object of a subtype S.
    - A model viewed in isolation cannot be meaningfully validated with respect to LSP! Validity must be judged from the perspective of possible usages of the model.
  - Design-by-Contract
  - Refactoring

## * DIP(Dependency Inversion Principle)
  - High level modules should not depend on low level modules; both should depend on abstractions. 
  - Abstractions should not depend on details. Details should depend upon abstractions. 
