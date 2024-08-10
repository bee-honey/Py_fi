Here's a comparison of operations for finding the minimum and maximum of integers across Java, Swift, and Python:

### 1. **Finding Minimum and Maximum in a List/Array**

| **Functionality**                   | **Java**                                   | **Swift**                                   | **Python**                        |
|-------------------------------------|--------------------------------------------|---------------------------------------------|-----------------------------------|
| **Find Minimum in a List/Array**    | `int min = Collections.min(Arrays.asList(array));` | `let min = array.min()`                   | `min_ = min(array)`               |
| **Find Maximum in a List/Array**    | `int max = Collections.max(Arrays.asList(array));` | `let max = array.max()`                   | `max_ = max(array)`               |

### 2. **Finding Minimum and Maximum of Two Values**

| **Functionality**                   | **Java**                                   | **Swift**                                   | **Python**                        |
|-------------------------------------|--------------------------------------------|---------------------------------------------|-----------------------------------|
| **Find Minimum of Two Values**      | `int min = Math.min(a, b);`                | `let min = min(a, b)`                       | `min_ = min(a, b)`                |
| **Find Maximum of Two Values**      | `int max = Math.max(a, b);`                | `let max = max(a, b)`                       | `max_ = max(a, b)`                |

### 3. **Finding Minimum and Maximum of Multiple Values**

| **Functionality**                   | **Java**                                   | **Swift**                                   | **Python**                        |
|-------------------------------------|--------------------------------------------|---------------------------------------------|-----------------------------------|
| **Find Minimum of Multiple Values** | `int min = Math.min(a, Math.min(b, c));`   | `let min = [a, b, c].min()`                 | `min_ = min(a, b, c)`             |
| **Find Maximum of Multiple Values** | `int max = Math.max(a, Math.max(b, c));`   | `let max = [a, b, c].max()`                 | `max_ = max(a, b, c)`             |

### 4. **Handling Minimum and Maximum of Empty Collections**

| **Functionality**                   | **Java**                                   | **Swift**                                   | **Python**                        |
|-------------------------------------|--------------------------------------------|---------------------------------------------|-----------------------------------|
| **Find Minimum of Empty Collection** | Throws `NoSuchElementException` if collection is empty. | Returns `nil` if empty.             | Raises `ValueError` if empty.     |
| **Find Maximum of Empty Collection** | Throws `NoSuchElementException` if collection is empty. | Returns `nil` if empty.             | Raises `ValueError` if empty.     |

### 5. **Custom Comparator for Finding Min/Max**

| **Functionality**                   | **Java**                                   | **Swift**                                   | **Python**                        |
|-------------------------------------|--------------------------------------------|---------------------------------------------|-----------------------------------|
| **Find Min with Custom Comparator** | `Collections.min(list, Comparator.naturalOrder());` | `let min = list.min(by: <)`           | `min_ = min(list, key=lambda x: x.some_attribute)` |
| **Find Max with Custom Comparator** | `Collections.max(list, Comparator.naturalOrder());` | `let max = list.max(by: >)`           | `max_ = max(list, key=lambda x: x.some_attribute)` |

### 6. **Special Cases: Handling `NaN` or `null` Values**

- **Java:** When working with `Math.min` or `Math.max`, `NaN` (Not-a-Number) will propagate if present, i.e., `Math.min(Double.NaN, 1.0)` results in `NaN`.
- **Swift:** When using `array.min()` or `array.max()`, if the array contains `nil` or `NaN` values, Swift handles them as per the context. If you're working with optionals, you should unwrap them or use `compactMap`.
- **Python:** In Python, `min()` and `max()` functions skip `None` values if used in a list with `key=lambda x: x is not None`. `NaN` will propagate similarly to Java.

### 7. **Examples**

#### Java Example
```java
int[] array = {3, 5, 1, 2, 4};
int min = Collections.min(Arrays.asList(3, 5, 1, 2, 4)); // Min of array
int max = Math.max(10, 20); // Max of two values
```

#### Swift Example
```swift
let array = [3, 5, 1, 2, 4]
let min = array.min() // Min of array
let max = max(10, 20) // Max of two values
```

#### Python Example
```python
array = [3, 5, 1, 2, 4]
min_ = min(array)  # Min of array
max_ = max(10, 20) # Max of two values
```

This table and examples provide a quick comparison of finding minimum and maximum values in Java, Swift, and Python, including handling different scenarios such as empty collections, multiple values, and custom comparators.