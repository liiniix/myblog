## Data Model

```python
... # x + y     ==>     __add__
... # init      ==>     __init__
... # repr(x)   ==>     __repr__
... # len(x)    ==>     __len__
... # x()       ==>     __call__
```

## Metaclass

## Decorator

Decorator is a wrapper, it wrap up some code with other functionality.

```python
def wrapper(func):
        def f():
                print("wrapper begins")
                func()
                print("wrapper ends")
        return f

def func():
        print("actual code")

func = wrapper(func)
func()
```
Instead of doing so, we could do
```python
def wrapper(func):
        def f():
                print("wrapper begins")
                func()
                print("wrapper ends")
        return f
@wrapper
def func():
        print("actual code")

#func = wrapper(func)

func()
```



