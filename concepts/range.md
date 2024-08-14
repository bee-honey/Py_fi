The `range()` function in Python is used to generate a sequence of numbers. It can take one, two, or three arguments, depending on how you want to specify the range of numbers.

### 1. **Single Argument (`stop`)**
   - **Syntax:** `range(stop)`
   - **Input:** A single integer that specifies the end of the range (exclusive).
   - **Output:** A sequence of numbers starting from `0` up to, but not including, `stop`.
   
   ```python
   range(5)  # Generates: 0, 1, 2, 3, 4
   ```

### 2. **Two Arguments (`start`, `stop`)**
   - **Syntax:** `range(start, stop)`
   - **Input:** Two integers, `start` and `stop`. The sequence starts at `start` and ends at `stop` (exclusive).
   - **Output:** A sequence of numbers starting from `start` up to, but not including, `stop`.
   
   ```python
   range(2, 5)  # Generates: 2, 3, 4
   ```

### 3. **Three Arguments (`start`, `stop`, `step`)**
   - **Syntax:** `range(start, stop, step)`
   - **Input:** Three integers:
     - `start`: The starting point of the range.
     - `stop`: The end point of the range (exclusive).
     - `step`: The amount by which the sequence is incremented or decremented.
   - **Output:** A sequence of numbers starting from `start`, incremented by `step`, up to but not including `stop`.
   
   ```python
   range(2, 10, 2)  # Generates: 2, 4, 6, 8
   range(10, 2, -2)  # Generates: 10, 8, 6, 4
   ```

### Key Points:
- **`stop` (required):** The upper boundary of the range (exclusive).
- **`start` (optional):** The starting point of the range (default is `0`).
- **`step` (optional):** The difference between each pair of consecutive numbers in the sequence (default is `1`).

### Examples:
```python
# Single argument: stop
for i in range(5):
    print(i)  # Output: 0 1 2 3 4

# Two arguments: start, stop
for i in range(2, 5):
    print(i)  # Output: 2 3 4

# Three arguments: start, stop, step
for i in range(2, 10, 2):
    print(i)  # Output: 2 4 6 8

# Negative step (decreasing sequence)
for i in range(10, 2, -2):
    print(i)  # Output: 10 8 6 4
```

### Summary:
- `range(stop)` generates numbers from `0` to `stop - 1`.
- `range(start, stop)` generates numbers from `start` to `stop - 1`.
- `range(start, stop, step)` generates numbers from `start` to `stop - 1`, with increments of `step`. If `step` is negative, it generates numbers in descending order.