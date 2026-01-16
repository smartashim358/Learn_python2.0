# Day 04 – Python File Handling (Revision)

## 📅 Topics Covered
- Python File Handling (Read, Write, Append)
- Best practices using `with`
- Real-world use cases
- Git commands revision (including pull, clone, push, commit, etc.)

---

## 🐍 Python File Handling

File handling allows programs to store data permanently and interact with real-world systems.
This is essential for AI, backend development, automation, cybersecurity, and robotics.

---

## 📂 Opening a File

### Syntax
```python
open("filename", "mode")
```

### File Modes
| Mode | Description |
|----|------------|
| `r` | Read (default) |
| `w` | Write (overwrite file) |
| `a` | Append (add data) |
| `r+` | Read + Write |

---

## ✍️ Writing to a File (`w` mode)

```python
with open("readfile1.txt", "w") as f:
    f.write("From the adjoining mapping diagram, write the pre-images of q\n")
```

---

## ➕ Appending to a File (`a` mode)

```python
with open("readfile1.txt", "a") as f:
    f.write("In how many places a vertical line cuts the function\n")
```

---

## 📖 Reading from a File

```python
with open("readfile1.txt", "r") as f:
    print(f.read())
```

---


## Video reference for learning:
**File handling:**
[![Video Title](https://img.youtube.com/vi/aequTxAvQq4/0.jpg)](https://www.youtube.com/watch?v=aequTxAvQq4)
-----------------------------------------------------------------------------------------------------------------
