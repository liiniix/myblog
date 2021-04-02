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

## Debugging
### Defensive programming



#### Type Hinting

Special thanks for this stackoverflow question for this: [How do Python functions handle the types of the parameters that you pass in?](https://stackoverflow.com/questions/2489669/how-do-python-functions-handle-the-types-of-the-parameters-that-you-pass-in).

And special thanks for the answer of [erb](https://stackoverflow.com/users/965332/erb).

* From PEP 3107 onward, we can now specify the type of parameters and return value.

```python
def pick(l: list, index: int) -> int:
    retutn l[index]
```

* Default values can also be specified like this:

```python
def pick(l: list, index: int = 0) -> int:
    return l[index]
```

* Although Python won't throw `TypeError`, we can use `isinstance` function and `raise TypeError`.

```python
def pick(l: list, index: int) -> int:
    if not isinstance(l, list):
        raise TypeError
    return l[index]
```

* PEP 484 comes with these type hinting

    - `List`, `Tuple`, `Set`, `Map` - for `list`, `tuple`, `set` and `map` respectively.
    - `Iterable` - useful for generators.
    - `Any` - when it could be anything.
    - `Union` - when it could be anything within a specified set of types, as opposed to Any.
    - `Optional` - when it might be None. Shorthand for `Union[T, None]`.
    - `TypeVar` - used with generics.
    - `Callable` - used primarily for functions, but could be used for other callables.

[Example code with type hinting](https://github.com/ActivityWatch/aw-core/blob/master/aw_core/models.py)