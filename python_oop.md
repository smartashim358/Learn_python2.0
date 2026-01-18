# Python OOP Revision for Backend Development

This document covers **Object-Oriented Programming (OOP)** concepts required for
Python backend development (Flask, Django, APIs, real-world projects).

---

## 1. What is OOP?
OOP is a programming paradigm based on **objects and classes**.

Backend benefits:
- Clean code structure
- Reusability
- Scalability
- Easy maintenance

---

## 2. Class and Object

### Class
A class is a blueprint for creating objects.

```python
class User:
    pass
```

### Object
An object is an instance of a class.

```python
user1 = User()
```

---

## 3. __init__ Constructor
Used to initialize object data.

```python
class User:
    def __init__(self, username, email):
        self.username = username
        self.email = email

user1 = User("ashim", "ashim@gmail.com")
```

---

## 4. Instance Variables
Variables specific to an object.

```python
self.username
self.email
```

---

## 5. Instance Methods
Functions that belong to a class.

```python
class User:
    def login(self):
        return "User logged in"
```

---

## 6. OOP Pillars (Very Important)

### 1️⃣ Encapsulation
Binding data and methods together.

```python
class User:
    def __init__(self, password):
        self.__password = password   # private variable
```

---

### 2️⃣ Inheritance
One class acquires properties of another class.

```python
class User:
    def login(self):
        return "Login success"

class Admin(User):
    def delete_user(self):
        return "User deleted"
```

---

### 3️⃣ Polymorphism
Same method name, different behavior.

```python
class User:
    def role(self):
        return "User"

class Admin(User):
    def role(self):
        return "Admin"
```

---

### 4️⃣ Abstraction
Hiding implementation details.

```python
from abc import ABC, abstractmethod

class Payment(ABC):
    @abstractmethod
    def pay(self):
        pass

class Esewa(Payment):
    def pay(self):
        return "Payment done"
```

---

## 7. self Keyword
Refers to the current object.

```python
self.username
```

---

## 8. Class Variables
Shared by all objects.

```python
class User:
    platform = "Web"
```

---

## 9. Static Methods
Methods not dependent on object data.

```python
class Utils:
    @staticmethod
    def is_valid_email(email):
        return "@" in email
```

---

## 10. OOP in Backend Example
```python
class User:
    def __init__(self, username):
        self.username = username

    def greet(self):
        return f"Hello {self.username}"

user = User("ashim")
print(user.greet())
```

---

## 11. Why OOP is Important for Backend
- Models in Django
- Services in Flask
- Database structure
- Business logic separation

---

## 12. OOP Backend Checklist
- class
- object
- __init__
- self
- inheritance
- polymorphism
- abstraction
- encapsulation
- staticmethod
