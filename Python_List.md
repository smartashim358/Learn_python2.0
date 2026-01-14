# 🐍 Python List -- Complete Revision Guide

In Python, a **list** is a built-in data structure used to store an
**ordered collection of items**.\
Python lists are very flexible and powerful compared to arrays in other
languages.

## 🔹 Key Features of Lists

-   Can contain **duplicate items**
-   **Mutable** -- items can be modified, replaced, or removed
-   **Ordered** -- maintains the insertion order
-   **Index-based** -- elements are accessed using indices (starting
    from `0`)
-   Can store **mixed data types** (integers, strings, booleans, floats,
    even other lists)

## 🧱 Creating a List

### 1️⃣ Using Square Brackets

``` python
a = [1, 2, 3, 4, 5]
b = ['apple', 'banana', 'cherry']
c = [1, 'hello', 3.14, True]
```

### 2️⃣ Using list() Constructor

``` python
a = list((1, 2, 3, 'apple', 4.5))
b = list("GFG")
```

### 3️⃣ Creating Repeated Elements

``` python
a = [2] * 5
b = [0] * 7
```

## 🎯 Accessing Elements

``` python
nums = [10, 20, 30, 40]
nums[0]
nums[-1]
```

## ✂️ Slicing

``` python
nums[1:4]
nums[:3]
nums[::2]
nums[::-1]
```

## 🔄 Modifying Lists

``` python
nums[1] = 99
```

## ➕ Adding Elements

``` python
nums.append(40)
nums.insert(1, 15)
nums.extend([50, 60])
```

## ➖ Removing Elements

``` python
nums.remove(99)
nums.pop()
nums.pop(1)
del nums[0]
nums.clear()
```

## 🧠 List Methods

``` python
nums.sort()
nums.sort(reverse=True)
nums.reverse()
nums.copy()
nums.index(8)
nums.count(2)
```

## 🔁 Looping

``` python
for x in nums:
    print(x)
```

``` python
for i in range(len(nums)):
    print(nums[i])
```

``` python
i = 0
while i < len(nums):
    print(nums[i])
    i += 1
```

## ⚡ List Comprehension

``` python
squares = [x**2 for x in range(5)]
even = [x for x in range(10) if x % 2 == 0]
```

## 🧩 Nested Lists

``` python
matrix = [[1,2,3],[4,5,6]]
matrix[1][2]
```

## 🔍 Membership & Length

``` python
2 in nums
len(nums)
```

## 📊 List vs Tuple

| Feature  | List   | Tuple  |
|----------|--------|--------|
| Mutable  | ✅ Yes | ❌ No  |
| Speed   | Slower | Faster |
| Syntax  | `[]`   | `()`   |

