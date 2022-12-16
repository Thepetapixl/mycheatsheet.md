# Data Structures

## Python classes

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

## Python Linked List Implementation

```python
class node:
    def __init__(self, data):
        self.data = data
        self.prev, self.next = None, None
        
    def __str__(self):
        return str(self.data)
```

Here class node represents a single node with the parameters of self and data. Data consists of the contents of the node. Self is the object itself.

It also has two pointers prev and next which keep track of the node before and after it. By default they are set to null.

```python
class LinkedList:
    def __init__(self) -> None:
        self.head = None
        
    def search(self, target):
        current = self.head
        while current:
            if current.data == target:
                return current
            current = current.next
        return None
```

- As you see above the Linkedlist class has two functions one is the `__init__` function which initializes the head.

- The other function we have is the search functions which has the target parameter. We then use a while loop to traverse through the linked list to find the target using the contents of the node.data as we pass through. Here we set current as the head of the linked list.

```python
    def insert(self, node):
        node.next = self.head
        if self.head:
            self.head.prev = node
        
        self.head = node
        node.prev = None
        
    def delete(self, node):
        if node.prev is not None:
            node.prev.next = node.next
        else:
            self.head = node.next
        
        if node.next is not None:
            node.next.prev = node.prev
```

- The insert function first sets the inserted node's next parameter to the current head and vice versa where the current head's previous pointer is pointing to the inserted node.

- Finally we set the newly inserted node as the head and set the previous of this node to null.

- The delete function first points the target node's previous to the target node's next and vice versa.

- Note: if you have the key, then first you have to search the node and then use the delete operation in order to delete the targeted node.
