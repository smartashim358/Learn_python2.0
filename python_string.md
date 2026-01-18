# Python String Revision with backend overview

This document covers **all essential string concepts** required for Python backend development
(Flask, Django, APIs, authentication, validation, databases).

---

## 1. What is a String?
A string is a sequence of characters enclosed in quotes.

```python
'hello'
"hello"
"""hello"""
```

Backend usage:
- User input
- API responses (JSON)
- Database fields
- Tokens, headers, messages

---

## 2. Creating Strings
```python
name = "Ashim"
email = "ashim@gmail.com"
bio = """Backend Developer"""
```

---

## 3. String Indexing & Slicing
```python
text = "backend"

text[0]      # 'b'
text[-1]     # 'd'
text[0:4]    # 'back'
text[:3]     # 'bac'
text[3:]     # 'kend'
```

---

## 4. String Immutability
Strings cannot be modified directly.

```python
s = "hello"
s = "H" + s[1:]
```

---

## 5. Important String Methods

### Case Conversion
```python
text.lower()
text.upper()
text.title()
```

Used for username and email normalization.

---

### Remove Whitespace (Very Important)
```python
email.strip()
email.lstrip()
email.rstrip()
```

Used in login and form validation.

---

### Replace Text
```python
msg = "Hello User"
msg.replace("User", "Admin")
```

---

### Find & Check
```python
email.find("@")
"@" in email
```

---

### Startswith / Endswith
```python
filename.endswith(".png")
filename.startswith("img")
```

Used in file uploads and URL checks.

---

## 6. Splitting & Joining

### split()
```python
data = "username,password,email"
data.split(",")
```

### join()
```python
words = ["backend", "developer"]
" ".join(words)
```

---

## 7. String Formatting (Best Practice)
```python
username = "ashim"
role = "admin"

f"User {username} is {role}"
```

---

## 8. String Validation
```python
username.isalpha()
user_id.isdigit()
password.isalnum()
len(password) >= 8
```

---

## 9. Escape Characters
```python
"He said \"Hello\""
"C:\\Users\\Admin"
```

---

## 10. Multiline Strings
```python
query = """
SELECT * FROM users
WHERE is_active = 1
"""
```

Used for SQL queries and email templates.

---

## 11. String Comparison
```python
username.lower() == "admin"
```

---



## 13. Backend Login Example
```python
username = input("Username: ").strip()
password = input("Password: ").strip()

if username.lower() == "admin" and len(password) >= 8:
    print("Login successful")
else:
    print("Invalid credentials")
```

---

## 14. String Checklist
- strip()
- lower()
- len()
- split()
- join()
- f-strings
- startswith()
- endswith()
- in operator
