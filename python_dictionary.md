# Python Dictionary ( Revision & Backend Focus)

## What is a Dictionary?
A dictionary is a **key-value** data structure used to store related data.
In backend development, dictionaries are heavily used to represent:
- Users
- JSON data
- Database-like structures
- API request/response data

---

## Creating a Dictionary
```python
user = {
    "username": "admin",
    "password": "1234",
    "is_active": True
}
```

---

## Accessing Dictionary Values
```python
print(user["username"])
```

⚠️ If the key does not exist, it will raise an error.

Safe way:
```python
print(user.get("username"))
```

---

## Real Backend Example: User Database
```python
user_db = {
    "admin": {
        "password": "1234",
        "role": "superadmin"
    },
    "john": {
        "password": "abcd",
        "role": "user"
    }
}
```

---

## Important Line Explained
```python
user = user_db[username]
```

### Meaning:
- `username` is entered by the user
- `user_db[username]` fetches that user's data
- `user` becomes a dictionary

Example:
```python
username = "admin"
user = user_db["admin"]

print(user["password"])  # 1234
```

---

## Login Validation Using Dictionary
```python
username = input("Username: ")
password = input("Password: ")

if username in user_db:
    user = user_db[username]
    if user["password"] == password:
        print("Login successful")
    else:
        print("Wrong password")
else:
    print("User not found")
```

---

## Why Dictionary is IMPORTANT for Backend
- Represents database rows
- Works directly with JSON
- Fast lookup (O(1))
- Clean and readable code

---

## Common Dictionary Methods
```python
user.keys()
user.values()
user.items()
```

---

## Summary
- Dictionary = backend backbone
- Used everywhere (Django, Flask, APIs)
- Maps directly to real-world data


