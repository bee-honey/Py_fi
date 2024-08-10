Here's a comparison of deque (double-ended queue) operations across Java (using `Deque`), Swift, and Python:

### 1. **Basic Deque Operations**

| **Functionality**                  | **Java (`Deque`)**                        | **Swift**                                   | **Python (`collections.deque`)** |
|------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Create Deque**                   | `Deque<String> deque = new ArrayDeque<>();` | `var deque: [String] = []`                 | `from collections import deque; deque = deque()` |
| **Add to Front (Push)**            | `deque.addFirst("Apple");`                | `deque.insert("Apple", at: 0)`              | `deque.appendleft("Apple")`      |
| **Add to Rear**                    | `deque.addLast("Apple");`                 | `deque.append("Apple")`                     | `deque.append("Apple")`          |
| **Remove from Front (Pop)**        | `String item = deque.removeFirst();`      | `let item = deque.removeFirst()`            | `item = deque.popleft()`         |
| **Remove from Rear**               | `String item = deque.removeLast();`       | `let item = deque.removeLast()`             | `item = deque.pop()`             |
| **Peek at Front**                  | `String item = deque.peekFirst();`        | `let item = deque.first`                    | `item = deque[0]` or `item = deque[0] if deque else None` |
| **Peek at Rear**                   | `String item = deque.peekLast();`         | `let item = deque.last`                     | `item = deque[-1]` or `item = deque[-1] if deque else None` |
| **Check if Deque is Empty**        | `boolean empty = deque.isEmpty();`        | `let empty = deque.isEmpty`                 | `empty = not deque`              |
| **Get Deque Size**                 | `int size = deque.size();`                | `let size = deque.count`                    | `size = len(deque)`              |
| **Clear Deque**                    | `deque.clear();`                          | `deque.removeAll()`                         | `deque.clear()`                  |

### 2. **Deque Iteration**

| **Functionality**                  | **Java (`Deque`)**                        | **Swift**                                   | **Python (`collections.deque`)** |
|------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Iterate Over Deque from Front**  | `for (String item : deque) {}`            | `for item in deque {}`                      | `for item in deque:`             |
| **Iterate Over Deque from Rear**   | `Iterator<String> it = deque.descendingIterator();` | `for item in deque.reversed() {}`         | `for item in reversed(deque):`   |

### 3. **Advanced Deque Operations**

| **Functionality**                  | **Java (`Deque`)**                        | **Swift**                                   | **Python (`collections.deque`)** |
|------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Add to Front (Alternative)**     | `deque.push("Apple");`                    | `deque.insert("Apple", at: 0)`              | `deque.appendleft("Apple")`      |
| **Add to Rear (Alternative)**      | `deque.offerLast("Apple");`               | `deque.append("Apple")`                     | `deque.append("Apple")`          |
| **Remove from Front (Alternative)**| `String item = deque.pollFirst();`        | `let item = deque.removeFirst()`            | `item = deque.popleft()`         |
| **Remove from Rear (Alternative)** | `String item = deque.pollLast();`         | `let item = deque.removeLast()`             | `item = deque.pop()`             |

### 4. **Deque Manipulation**

| **Functionality**                  | **Java (`Deque`)**                        | **Swift**                                   | **Python (`collections.deque`)** |
|------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Rotate Deque**                   | *No direct equivalent (use loop)*         | *No direct equivalent (use loop)*           | `deque.rotate(1)` (right), `deque.rotate(-1)` (left) |
| **Extend Deque**                   | `deque.addAll(otherDeque);`               | `deque.append(contentsOf: otherDeque)`      | `deque.extend(otherDeque)`       |
| **Extend Deque at Front**          | *No direct equivalent*                    | *No direct equivalent*                      | `deque.extendleft(otherDeque)`   |

### 5. **Deque Slicing**

| **Functionality**                  | **Java (`Deque`)**                        | **Swift**                                   | **Python (`collections.deque`)** |
|------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Slice Deque**                    | *No direct equivalent (convert to List)*  | `let slice = Array(deque[1...3])`           | `slice = list(deque)[1:4]`       |

### 6. **Deque Conversion**

| **Functionality**                  | **Java (`Deque`)**                        | **Swift**                                   | **Python (`collections.deque`)** |
|------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Convert Deque to List/Array**    | `List<String> list = new ArrayList<>(deque);` | `let list = Array(deque)`                | `list_ = list(deque)`            |

### 7. **Miscellaneous**

| **Functionality**                  | **Java (`Deque`)**                        | **Swift**                                   | **Python (`collections.deque`)** |
|------------------------------------|-------------------------------------------|---------------------------------------------|----------------------------------|
| **Get Hash Code**                  | *No direct equivalent (Deque not hashable)* | *No direct equivalent (Array not hashable)* | *No direct equivalent (Deque not hashable)* |

This table provides a quick comparison of deque operations in Java, Swift, and Python, highlighting the similarities and differences across these languages.