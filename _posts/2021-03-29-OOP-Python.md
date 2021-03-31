- Everything in Python is object, even functions are objects in Python
- We can create, manipulate, destroy objects. `del` will destroy objects which will be reclaimed by garbage collector.
- Objects are data abstraction
- Example, list are internally implementaed by manipulation of linked list, internal resentaion is hidden. We can interact by `L[i], del L[i], max(), L.append()` etc.
- `__init__()` is something camparable to class consractor. `self` is comparable to Java `this`.
- `__str__` is cool. It is called when an object is printed. It can be used as debug tool.

```python
>>> class Coordinate:
...     def __init__(self, x, y):
...             self.x = x
...             self.y = y
...     def __str__(self):
...             return "<"+str(self.x)+","+str(self.y)+">"
... 
>>> c = Coordinate(1, 0)
>>> c
<__main__.Coordinate object at 0x7f01c18ab2d0>
```

## Inheritence
- information hiding, use getters and setters
- Class vaiable are shared among all insatnces

```python
>>> class Class:
...     tag = 0
...     def __init__(self):
...             Class.tag += 1
... 
>>> a = Class()
>>> b = Class()
>>> Class.tag
2
>>> 
```

> Setting underscore `_` before any atribute name is a convention for considering that attribute as private and not to use outside the class