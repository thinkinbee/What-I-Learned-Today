## Pickle

`import pickle`

Implements serializing and deserializing of a python data structure.

### writing data

we can use `dump` to write data in binary format

```python
import pickle
f = open('pickle_demo.dat','wb')

# writing different types of data into it
pickle.dump(11, f)
pickle.dump("this is a line", f)
pickle.dump([1, 2, 3, 4], f)
f.close()
```  

### contents of `pickle_demo.dat` file written using pickle

```text
I11
.S'this is a line'
p0
.(lp0
I1
aI2
aI3
aI4
a.
```

### reading data

using `load` to read data

```python
import pickle
f = open('pick.dat', 'rb')
pickle.load(f)
# 11
pickle.load(f)
# "this is a line"
pickle.load(f)
# [1,2,3,4]
f.close()
```

## Learning more on `self`

### plain basics
`self` refers to the object which invokes the method. 

```python

class Vehicle:

    def __init__(self, type):
        self.type = type

    def whichtype(self):
        return "the vehicle is a " + self.type
```

```python
car = Vehicle('ford') # creates a object 
# the `self` now references(points) to the above object

```

The `self` is automatically set as a reference to the object , as a part of the `__init__` call


## private in python

`__` before variable name makes it private

example: `__name` will be accessible only within the `class` not outside

## setters and getters

A good design way is to have `setters` and `getters`, they help in achieving `encapsulation`

Example:

```python
class Vehicle:

    def __init__(self, type):
        self.type = type
    
    
    # set the type of the vehicle
    def setType(self, type):
        self.type = type
        
    # get the type of the vehicle
    def getType(self):
        return self.type
``` 

This makes sure that the `data field` is always accessed via a `method` and is not available for modification without the `setter` method
