# Asynchronous python

## 1. What is Async Python?
Async Python allows your program to handle multiple I/O-bound tasks efficiently
without blocking the main thread.

Async is best for:
- API calls
- Database queries
- File & network I/O
- Backend servers

❌ Not for CPU-heavy tasks.

---

## 2. Blocking vs Non-Blocking

### Blocking Example
```python
import time

def task():
    time.sleep(2)
    print("Done")
```
## None-Blocing(Async) concept:
- Asynchronous programming allows us to execute multiple tasks concurrently, improving performance and responsiveness.

**Features of asynchronous programming:**

- Improves Performance – Handles multiple tasks without waiting for each to complete.
- Non-Blocking I/O – Ideal for tasks like fetching external data or database operations.
- Better User Experience – Reduces delays for users when making API requests.

## async & await Keywords
```python
async def hello():
    return "Hello"

```
- async def defines a coroutine

- Calling it does NOT execute it

- It must be awaited

```python
async def main():
    result = await hello()
    print(result)

```
## Event Loop

- The event loop:

- Runs async tasks

- Switches tasks when waiting

```python
import asyncio

async def main():
    print("Event loop running")

asyncio.run(main())

```
## Async Sleep (Important)
**Blocking**
```python
time.sleep(2)

```
***Non-Blocking**
```python
await asyncio.sleep(2)

```
## Running Multiple Tasks (asyncio.gather)
```python
import asyncio

async def task(name, delay):
    print(f"{name} started")
    await asyncio.sleep(delay)
    print(f"{name} finished")

async def main():
    await asyncio.gather(
        task("Task-1", 2),
        task("Task-2", 2)
    )

asyncio.run(main())

```
## Background Tasks (create_task)
```python
import asyncio

async def background_task():
    await asyncio.sleep(2)
    print("Background done")

async def main():
    asyncio.create_task(background_task())
    print("Main continues")
    await asyncio.sleep(3)

asyncio.run(main())

```
**Used for:**

- Logging

- Notifications

- Webhooks
## Fetching APIs:
```python
import httpx
import asyncio

async def fetch(url):
    async with httpx.AsyncClient() as client:
        response = await client.get(url)
        return response.json()

async def main():
    data = await fetch("https://api.example.com")
    print(data)

asyncio.run(main())

```