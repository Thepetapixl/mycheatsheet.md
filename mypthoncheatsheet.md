# Python classes

- Consists of

1. `__init__(self):` </br>
Initializes the attributes of the object and is automatically called.
</br>

2. special methods are denoted with two underscores such as `__add__(self).`
</br>

3. Instance methods are methods that belong to the object created, `l.append(4).`
</br>

```python
class Dog:
  def __init__(self,name,breed,age):
    self.Name = name
    self.Breed = breed
    self.Age = age
```

__self__ - always the first parameter and refers to the object which will be created in the future.

__name, breed and age__ are the remaining arguments. They contain the values for the object's attributes.
</br>

```python
class Dog:
    def __repr__(self):
        return "Name: {}, Breed: {}, Age: {}".format(self.Name,
                                           self.Breed,self.Age)
```

\_\_repr__ takes a unique arguement self which can also access all the attributes of the object.

```python
class Dog:
    def __init__(self, name, breed, age, tired):
        self.Name = name
        self.Breed = breed
        self.Age = age
        self.tired = tired

    def sleep(self):
        if self.tired == True:
            return "I will sleep"
        else:
            return "I still will sleep"
```

here if we add another parameter tired in the inti function and create an instance sleep which uses the tired then it can access the parameter and then perform it's function.
