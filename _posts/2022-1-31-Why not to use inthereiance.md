---
layout: post
title: "Why not to use Inheritance"
tags: [python, programming]
categories: [Programming]
author:
    name: Yusuf Adel
    link: https://yusufadell.web.app
---

It’s easy to overengineer your classes using inheritance. As Luciano
Ramalho states, “Placing objects in a neat hierarchy appeals to our sense
of order; programmers do it just for fun.” We’ll create classes, subclasses,
and sub-subclasses when a single class, or a couple of functions in a mod-
ule, would achieve the same effect. But recall the Zen of Python tenet in
Chapter 6 that simple is better than complex.
Using OOP allows you to organize your code into smaller units (in this
case, classes) that are easier to reason about than one large .py file with hun-
dreds of functions defined in no particular order. Inheritance is useful if
you have several functions that all operate on the same dictionary or list
data structure. In that case, it’s beneficial to organize them into a class.
But here are some examples of when you don’t need to create a class or
use inheritance:

- If your class consists of methods that never use the self or cls param-
eter, delete the class and use functions in place of the methods.•

- If you’ve created a parent with only a single child class but never create
objects of the parent class, you can combine them into a single class.

- If you create more than three or four levels of subclasses, you’re prob-
ably using inheritance unnecessarily. Combine those subclasses into
fewer classes.

As the non-OOP and OOP versions of the tic-tac-toe program in the
previous chapter illustrate, it’s certainly possible to not use classes and still
have a working, bug-free program. Don’t feel that you have to design your
program as some complex web of classes. A simple solution that works is bet-
ter than a complicated solution that doesn’t. Joel Spolsky writes about this in
his blog post, “Don’t Let the Astronaut Architects Scare You” at https://www
.joelonsoftware.com/2001/04/21/dont-let-architecture-astronauts-scare-you/.

You should know how object-oriented concepts like inheritance work,
because they can help you organize your code and make development and
debugging easier. Due to Python’s flexibility, the language not only offers
OOP features, but also doesn’t require you to use them when they aren't
suited for your program's needs
