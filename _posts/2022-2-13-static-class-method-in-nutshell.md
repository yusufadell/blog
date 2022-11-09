---

title: Instance Static Class Methods in a Nutshell
tags: [python]
category: [Python]
layout: post
author:
    name: Yusuf Adel
    link: gttps://github.com/yusufadell
---

## Instance - Static - Class Methods

![blog header for python post](/assets/img/posts/python-classes.jpg)
_instance - static - class and propetry methods python_

```python
class MyClass:
    # obj = MyClass
    # Same as MyClass().method(obj)
    def method(the_object):
        return 'instance method called' the_object

    @classmethod
    def classmethod(the_class):
        return 'class method called' the_class

    @staticmethod
    def staticmethod():
        return 'static method called'

    @property
    def nm(self):
        return 'property called'
```

Please note that naming these parameters **self** and **cls** is just a
**convention**. You could just as easily name them **the_object** and
**the_class** and get the same result. All that matters is that they’re
positioned first in the parameter list for that particular method.

```python
obj = MyClass()

print(obj.method())
```

## without the syntactic sugar provided by the obj.method() dot-call syntax

```python
print(same as  MyClass.method(obj))
print(obj.classmethod())
```

This confirms that static methods can neither access the object in-
stance state nor the class state. They work like **regular functions but belong to the class**’
(and every instance’s) namespace.

```shell
print(obj.staticmethod())
```

Flagging a method as a static method is not just a hint that a method
won’t modify class or instance state. As you’ve seen this restriction is
also enforced by the Python runtime.

## Key Takeaways

- Instance methods need a class instance and can access the instance through self.

- Class methods don’t need a class instance. They can’t access the
instance (self) but they have access to the class itself via cls.

- Static methods don’t have access to cls or self. They work like
regular functions but belong to the class’ namespace.

- Static and class methods communicate and (to a certain degree)
enforce developer intent about class design. This can have def-
inite maintenance benefits.
