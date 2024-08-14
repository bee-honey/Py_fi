Here's a comparison of priority queue operations across Java, Swift, and Python:

### 1. **Basic Priority Queue Operations**

| **Functionality**                   | **Java (`PriorityQueue`)**                | **Swift (`PriorityQueue` via `Heap`)**       | **Python (`heapq`)**              |
|-------------------------------------|-------------------------------------------|----------------------------------------------|-----------------------------------|
| **Create Priority Queue**           | `PriorityQueue<Integer> pq = new PriorityQueue<>();` | `var pq = Heap<Int>()` (Custom Implementation) | `import heapq; pq = []`           |
| **Insert Element**                  | `pq.add(5);`                              | `pq.insert(5)` (Custom Implementation)       | `heapq.heappush(pq, 5)`           |
| **Peek/Access Min Element**         | `int min = pq.peek();`                    | `let min = pq.peek()` (Custom Implementation) | `min_ = pq[0]`                    |
| **Remove Min Element**              | `int min = pq.poll();`                    | `let min = pq.remove()` (Custom Implementation) | `min_ = heapq.heappop(pq)`        |
| **Check if Queue is Empty**         | `boolean empty = pq.isEmpty();`           | `let empty = pq.isEmpty` (Custom Implementation) | `empty = not pq`                  |
| **Get Queue Size**                  | `int size = pq.size();`                   | `let size = pq.count` (Custom Implementation) | `size = len(pq)`                  |

### 2. **Custom Comparator or Reverse Priority Queue**

| **Functionality**                   | **Java (`PriorityQueue`)**                | **Swift (`PriorityQueue` via `Heap`)**       | **Python (`heapq`)**              |
|-------------------------------------|-------------------------------------------|----------------------------------------------|-----------------------------------|
| **Create Max-Heap (Reverse Order)** | `PriorityQueue<Integer> pq = new PriorityQueue<>(Collections.reverseOrder());` | `var pq = Heap<Int>(sort: >)` (Custom Implementation) | `pq = []; heapq._heapify_max(pq)` |
| **Insert with Custom Comparator**   | *Not directly supported, use Comparable*  | *Use custom sort function in `Heap` implementation* | *Not directly supported, use tuple (priority, element)* |
| **Insert with Reverse Order**       | `pq.add(5);` (with reverse order comparator) | `pq.insert(5)` (Custom Implementation)       | `heapq.heappush(pq, -5)` (for max-heap behavior) |

### 3. **Bulk Operations**

| **Functionality**                   | **Java (`PriorityQueue`)**                | **Swift (`PriorityQueue` via `Heap`)**       | **Python (`heapq`)**              |
|-------------------------------------|-------------------------------------------|----------------------------------------------|-----------------------------------|
| **Add All Elements from Collection** | `pq.addAll(collection);`                 | `for item in collection { pq.insert(item) }` (Custom Implementation) | `for item in collection: heapq.heappush(pq, item)` |
| **Heapify a List**                  | `PriorityQueue<Integer> pq = new PriorityQueue<>(list);` | `var pq = Heap<Int>(array: list)` (Custom Implementation) | `heapq.heapify(list)`             |

### 4. **Access and Remove Operations**

| **Functionality**                   | **Java (`PriorityQueue`)**                | **Swift (`PriorityQueue` via `Heap`)**       | **Python (`heapq`)**              |
|-------------------------------------|-------------------------------------------|----------------------------------------------|-----------------------------------|
| **Remove Specific Element**         | `pq.remove(5);`                           | `pq.remove(5)` (Custom Implementation)       | `pq.remove(5)` (Note: `heapq` doesn't support this directly) |
| **Access All Elements (in order)**  | `while (!pq.isEmpty()) { pq.poll(); }`    | `while !pq.isEmpty { pq.remove() }` (Custom Implementation) | `while pq: heapq.heappop(pq)`     |

### 5. **Complexity Considerations**

| **Functionality**                   | **Java (`PriorityQueue`)**                | **Swift (`PriorityQueue` via `Heap`)**       | **Python (`heapq`)**              |
|-------------------------------------|-------------------------------------------|----------------------------------------------|-----------------------------------|
| **Insertion Complexity**            | `O(log n)`                                | `O(log n)` (Custom Implementation)           | `O(log n)`                        |
| **Removal Complexity**              | `O(log n)`                                | `O(log n)` (Custom Implementation)           | `O(log n)`                        |
| **Access Min/Max Element Complexity** | `O(1)`                                  | `O(1)` (Custom Implementation)               | `O(1)`                            |

### 6. **Advanced Operations**

| **Functionality**                   | **Java (`PriorityQueue`)**                | **Swift (`PriorityQueue` via `Heap`)**       | **Python (`heapq`)**              |
|-------------------------------------|-------------------------------------------|----------------------------------------------|-----------------------------------|
| **Merge Multiple Queues**           | *No direct equivalent, use manual merging* | *No direct equivalent, custom implementation needed* | `merged = heapq.merge(pq1, pq2)`  |
| **Find `n` Largest Elements**       | *No direct equivalent, use `Collections.sort` or a custom approach* | *No direct equivalent, custom implementation needed* | `largest = heapq.nlargest(n, pq)` |
| **Find `n` Smallest Elements**      | *No direct equivalent, use `Collections.sort` or a custom approach* | *No direct equivalent, custom implementation needed* | `smallest = heapq.nsmallest(n, pq)` |

### 7. **Convert to List/Array**

| **Functionality**                   | **Java (`PriorityQueue`)**                | **Swift (`PriorityQueue` via `Heap`)**       | **Python (`heapq`)**              |
|-------------------------------------|-------------------------------------------|----------------------------------------------|-----------------------------------|
| **Convert Queue to List/Array**     | `List<Integer> list = new ArrayList<>(pq);` | `let list = pq.elements` (Custom Implementation) | `list_ = list(pq)` (Note: not ordered) |

### 8. **Custom Implementation of Priority Queue in Swift**

In Swift, there isn't a built-in `PriorityQueue` class like in Java or `heapq` in Python. However, you can implement a priority queue using a custom `Heap` structure:

```swift
struct Heap<Element: Comparable> {
    private var elements: [Element] = []
    private let sort: (Element, Element) -> Bool

    init(sort: @escaping (Element, Element) -> Bool) {
        self.sort = sort
    }

    mutating func insert(_ value: Element) {
        elements.append(value)
        siftUp(from: elements.count - 1)
    }

    mutating func remove() -> Element? {
        guard !elements.isEmpty else { return nil }
        elements.swapAt(0, elements.count - 1)
        let value = elements.removeLast()
        siftDown(from: 0)
        return value
    }

    func peek() -> Element? {
        return elements.first
    }

    var isEmpty: Bool {
        return elements.isEmpty
    }

    var count: Int {
        return elements.count
    }

    private mutating func siftUp(from index: Int) {
        var child = index
        var parent = (child - 1) / 2
        while child > 0 && sort(elements[child], elements[parent]) {
            elements.swapAt(child, parent)
            child = parent
            parent = (child - 1) / 2
        }
    }

    private mutating func siftDown(from index: Int) {
        var parent = index
        while true {
            let left = 2 * parent + 1
            let right = 2 * parent + 2
            var candidate = parent
            if left < elements.count && sort(elements[left], elements[candidate]) {
                candidate = left
            }
            if right < elements.count && sort(elements[right], elements[candidate]) {
                candidate = right
            }
            if candidate == parent { return }
            elements.swapAt(parent, candidate)
            parent = candidate
        }
    }
}
```

This provides a priority queue functionality with customizable sorting (min-heap or max-heap) in Swift, similar to Java's `PriorityQueue` and Python's `heapq`.

This table and example provide a quick comparison of priority queue operations in Java, Swift, and Python, highlighting how each language implements this data structure and the available operations.