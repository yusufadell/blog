---
layout: post
title: "Method and Decorators (Part 1)"
tags: [python, programming]
categories: [Programming]
author:
    name: Yusuf Adel
    link: https://yusufadell.web.app
---

# Method and Decorators

Python’s decorators are a handy way to modify functions.
Decorators were first introduced in Python 2.2, with the `classmethod()` and `staticmethod()` decorators,
but were overhauled to become more flexible and readable. Along with these two original decorators,
Python now provides a few right out of the box and supports the simple creation of custom decorators.
But it seems as though most developers do not understand how they work behind the scenes.

we’ll look at using decorators to create static, class, and abstract methods
and take a close look at the `super()` function, which allows you to place implementable
code inside an abstract method.

## Decorators and When to Use Them

A decorator is a function that takes another function as an argument and
replaces it with a new, modified function. The primary use case for decorators is in factoring common code
that needs to be called before, after, or around multiple functions. If you’ve ever written Emacs Lisp code,
you may have used the defadvice decorator, which allows you to define code called
around a function. If you’ve used method combinations in the Common
Lisp Object System (CLOS), Python decorators follow the same concepts.
We’ll look at some simple decorator definitions, and then we’ll examine
some common situations in which you’d use decorators.

## Creating Decorators

The odds are good that you’ve already used decorators to make your own
wrapper functions. The dullest possible decorator, and the simplest example,
is the `identity()` function, which does nothing except return the original
function. Here is its definition:

```python
def identity(f):
    return f
```

You would then use your decorator like this:

```python
@identity
def foo():
    return 'bar'
```

You enter the name of the decorator preceded by an `@` symbol and then
enter the function you want to use it on. This is the same as writing the
following:

```python
def foo():
    return 'bar'

foo = identity(foo)
```

This decorator is useless, but it works. Let’s look at another, more useful

```python
_functions = {}

def register(f):
    global _functions
    _functions[f.__name__] = f
    return f

@register
def foo():
    return 'bar'
```

the register decorator stores the decorated function
name into a dictionary. The `_functions` dictionary can then be used and
accessed using the function name to retrieve a function: `_functions['foo']`
points to the `foo()` function.

In the following Post, I will explain how to write your own decora tors.
Then I’ll cover how the built-in decorators provided by Python work
and explain how (and when) to use them.
