Certainly! Here's a comparison of each Java list operation with its equivalent in Swift and Python:

### 1. **Basic List Operations**

| **Functionality**                   | **Java**                        | **Swift**                                      | **Python**                       |
|-------------------------------------|---------------------------------|------------------------------------------------|----------------------------------|
| **Add Element**                     | `list.add("Apple");`            | `list.append("Apple")`                         | `list.append("Apple")`           |
| **Insert Element at Index**         | `list.add(1, "Orange");`        | `list.insert("Orange", at: 1)`                 | `list.insert(1, "Orange")`       |
| **Remove Element by Index**         | `list.remove(1);`               | `list.remove(at: 1)`                           | `list.pop(1)`                    |
| **Remove Element by Value**         | `list.remove("Apple");`         | `list.remove("Apple")`                         | `list.remove("Apple")`           |
| **Get Element by Index**            | `String fruit = list.get(0);`   | `let fruit = list[0]`                          | `fruit = list[0]`                |
| **Set Element at Index**            | `list.set(1, "Orange");`        | `list[1] = "Orange"`                           | `list[1] = "Orange"`             |
| **Get List Size**                   | `int size = list.size();`       | `let size = list.count`                        | `size = len(list)`               |
| **Check if List is Empty**          | `boolean empty = list.isEmpty();`| `let empty = list.isEmpty`                     | `empty = not list`               |
| **Clear List**                      | `list.clear();`                 | `list.removeAll()`                             | `list.clear()`                   |
| **Check if List Contains Element**  | `boolean exists = list.contains("Apple");`| `let exists = list.contains("Apple")`         | `exists = "Apple" in list`       |
| **Find Index of Element**           | `int index = list.indexOf("Apple");`| `let index = list.firstIndex(of: "Apple")`   | `index = list.index("Apple")`    |
| **Find Last Index of Element**      | `int lastIndex = list.lastIndexOf("Apple");`| `let lastIndex = list.lastIndex(of: "Apple")` | `lastIndex = len(list) - 1 - list[::-1].index("Apple")` |

### 2. **Bulk Operations**

| **Functionality**                   | **Java**                               | **Swift**                                      | **Python**                       |
|-------------------------------------|----------------------------------------|------------------------------------------------|----------------------------------|
| **Add All Elements from Another List**| `list.addAll(otherList);`            | `list.append(contentsOf: otherList)`           | `list.extend(otherList)`         |
| **Remove All Elements in Another List**| `list.removeAll(otherList);`        | `list.removeAll(where: { otherList.contains($0) })` | `for item in otherList: list.remove(item)` |
| **Retain Only Elements in Another List**| `list.retainAll(otherList);`       | `list = list.filter { otherList.contains($0) }`| `list = [x for x in list if x in otherList]` |
| **Check if All Elements Exist in Another List**| `boolean allExist = list.containsAll(otherList);`| `let allExist = otherList.allSatisfy { list.contains($0) }` | `allExist = all(item in list for item in otherList)` |

### 3. **Sublist and Conversion**

| **Functionality**                   | **Java**                               | **Swift**                                      | **Python**                       |
|-------------------------------------|----------------------------------------|------------------------------------------------|----------------------------------|
| **Get Sublist**                     | `List<String> sublist = list.subList(1, 3);`| `let sublist = Array(list[1..<3])`          | `sublist = list[1:3]`            |
| **Convert List to Array**           | `Object[] array = list.toArray();`      | `let array = Array(list)`                     | `array = list.copy()`            |

### 4. **Iterators**

| **Functionality**                   | **Java**                               | **Swift**                                      | **Python**                       |
|-------------------------------------|----------------------------------------|------------------------------------------------|----------------------------------|
| **Get Iterator**                    | `Iterator<String> it = list.iterator();` | `var it = list.makeIterator()`                | `it = iter(list)`                |
| **Get ListIterator**                | `ListIterator<String> lit = list.listIterator();` | `var lit = list.enumerated().makeIterator()` | `lit = iter(enumerate(list))`    |
| **Get ListIterator from Index**     | `ListIterator<String> lit = list.listIterator(1);`| `var lit = list[1...].enumerated().makeIterator()` | `lit = iter(enumerate(list[1:]))`|
| **For Each Element**                | `list.forEach(System.out::println);`    | `list.forEach { print($0) }`                   | `for item in list: print(item)`  |

### 5. **Sorting and Searching**

| **Functionality**                   | **Java**                               | **Swift**                                      | **Python**                       |
|-------------------------------------|----------------------------------------|------------------------------------------------|----------------------------------|
| **Sort List**                       | `list.sort(Comparator.naturalOrder());` | `list.sort()`                                  | `list.sort()`                    |
| **Binary Search in Sorted List**    | `int pos = Collections.binarySearch(list, "Apple");`| `let pos = list.binarySearch("Apple")`       | `import bisect; pos = bisect.bisect_left(list, "Apple")` |

### 6. **Stream Operations**

| **Functionality**                   | **Java**                               | **Swift**                                      | **Python**                       |
|-------------------------------------|----------------------------------------|------------------------------------------------|----------------------------------|
| **Get Stream**                      | `list.stream().forEach(System.out::println);`| `list.forEach { print($0) }`                  | `for item in list: print(item)`  |
| **Get Parallel Stream**             | `list.parallelStream().forEach(System.out::println);`| `DispatchQueue.concurrentPerform(iterations: list.count) { index in print(list[index]) }` | `import concurrent.futures; with concurrent.futures.ThreadPoolExecutor() as executor: executor.map(print, list)` |

### 7. **Spliterator**

| **Functionality**                   | **Java**                               | **Swift**                                      | **Python**                       |
|-------------------------------------|----------------------------------------|------------------------------------------------|----------------------------------|
| **Get Spliterator**                 | `Spliterator<String> spl = list.spliterator();`| *No direct equivalent*                       | *No direct equivalent*           |

### 8. **Miscellaneous**

| **Functionality**                   | **Java**                               | **Swift**                                      | **Python**                       |
|-------------------------------------|----------------------------------------|------------------------------------------------|----------------------------------|
| **Check Equality of Lists**         | `boolean equal = list.equals(otherList);` | `let equal = list == otherList`              | `equal = list == otherList`      |
| **Get Hash Code of List**           | `int hash = list.hashCode();`           | `let hash = list.hashValue`                   | `hash = hash(tuple(list))`       |

This table provides a quick comparison of list operations in Java, Swift, and Python, highlighting the syntactical differences and functional equivalences across these languages.