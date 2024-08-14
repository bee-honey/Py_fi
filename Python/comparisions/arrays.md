Here's a comparison of array operations across Java, Swift, and Python:

### 1. **Basic Array Operations**

| **Functionality**                    | **Java (`Array`)**                           | **Swift (`Array`)**                           | **Python (`list`)**               |
|--------------------------------------|----------------------------------------------|-----------------------------------------------|-----------------------------------|
| **Create Array**                     | `int[] arr = new int[5];`                    | `var arr = [Int](repeating: 0, count: 5)`     | `arr = [0] * 5`                   |
| **Create Array with Initial Values** | `int[] arr = {1, 2, 3};`                     | `let arr = [1, 2, 3]`                         | `arr = [1, 2, 3]`                 |
| **Access Element by Index**          | `int num = arr[0];`                          | `let num = arr[0]`                            | `num = arr[0]`                    |
| **Modify Element by Index**          | `arr[0] = 10;`                               | `arr[0] = 10`                                 | `arr[0] = 10`                     |
| **Get Array Length**                 | `int length = arr.length;`                   | `let length = arr.count`                      | `length = len(arr)`               |
| **Check if Array is Empty**          | *No direct equivalent*                       | `let empty = arr.isEmpty`                     | `empty = not arr`                 |

### 2. **Adding and Removing Elements**

| **Functionality**                    | **Java (`Array` or `ArrayList`)**            | **Swift (`Array`)**                           | **Python (`list`)**               |
|--------------------------------------|----------------------------------------------|-----------------------------------------------|-----------------------------------|
| **Add Element (for `ArrayList`)**    | `arrList.add(4);`                            | `arr.append(4)`                               | `arr.append(4)`                   |
| **Insert Element at Index**          | `arrList.add(1, 4);`                         | `arr.insert(4, at: 1)`                        | `arr.insert(1, 4)`                |
| **Remove Element by Index**          | `arrList.remove(1);`                         | `arr.remove(at: 1)`                           | `arr.pop(1)`                      |
| **Remove Element by Value**          | `arrList.remove(Integer.valueOf(4));`        | `arr.removeAll { $0 == 4 }`                   | `arr.remove(4)`                   |

### 3. **Array Slicing and Subarrays**

| **Functionality**                    | **Java (`Array`)**                           | **Swift (`Array`)**                           | **Python (`list`)**               |
|--------------------------------------|----------------------------------------------|-----------------------------------------------|-----------------------------------|
| **Get Subarray (Slice)**             | `int[] subArr = Arrays.copyOfRange(arr, 1, 4);` | `let subArr = Array(arr[1...3])`            | `subArr = arr[1:4]`               |

### 4. **Searching and Sorting**

| **Functionality**                    | **Java (`Array`)**                           | **Swift (`Array`)**                           | **Python (`list`)**               |
|--------------------------------------|----------------------------------------------|-----------------------------------------------|-----------------------------------|
| **Find Element Index**               | `int index = Arrays.asList(arr).indexOf(3);` | `if let index = arr.firstIndex(of: 3) { ... }` | `index = arr.index(3)`            |
| **Check if Element Exists**          | `boolean exists = Arrays.asList(arr).contains(3);` | `let exists = arr.contains(3)`            | `exists = 3 in arr`               |
| **Sort Array**                       | `Arrays.sort(arr);`                          | `arr.sort()`                                  | `arr.sort()`                      |

### 5. **Array Transformation**

| **Functionality**                    | **Java (`Array`)**                           | **Swift (`Array`)**                           | **Python (`list`)**               |
|--------------------------------------|----------------------------------------------|-----------------------------------------------|-----------------------------------|
| **Reverse Array**                    | `Collections.reverse(Arrays.asList(arr));`   | `arr.reverse()`                               | `arr.reverse()`                   |
| **Map/Transform Elements**           | `int[] newArr = Arrays.stream(arr).map(x -> x * 2).toArray();` | `let newArr = arr.map { $0 * 2 }`          | `newArr = [x * 2 for x in arr]`   |
| **Filter Elements**                  | `int[] filtered = Arrays.stream(arr).filter(x -> x > 2).toArray();` | `let filtered = arr.filter { $0 > 2 }`   | `filtered = [x for x in arr if x > 2]` |

### 6. **Joining and Splitting**

| **Functionality**                    | **Java (`Array`)**                           | **Swift (`Array`)**                           | **Python (`list`)**               |
|--------------------------------------|----------------------------------------------|-----------------------------------------------|-----------------------------------|
| **Join Arrays**                      | `int[] joined = IntStream.concat(Arrays.stream(arr1), Arrays.stream(arr2)).toArray();` | `let joined = arr1 + arr2`          | `joined = arr1 + arr2`            |
| **Join Elements into String**        | `String joined = String.join(",", Arrays.stream(arr).mapToObj(String::valueOf).toArray(String[]::new));` | `let joined = arr.map { String($0) }.joined(separator: ",")` | `joined = ",".join(map(str, arr))` |

### 7. **Array Conversion**

| **Functionality**                    | **Java (`Array`)**                           | **Swift (`Array`)**                           | **Python (`list`)**               |
|--------------------------------------|----------------------------------------------|-----------------------------------------------|-----------------------------------|
| **Convert Array to List**            | `List<Integer> list = Arrays.asList(arr);`   | `let list = Array(arr)`                       | `list_ = list(arr)`               |
| **Convert List to Array**            | `int[] arr = list.toArray(new int[0]);`      | `let arr = list.toArray()`                    | `arr = list_`                     |

### 8. **Array Aggregation**

| **Functionality**                    | **Java (`Array`)**                           | **Swift (`Array`)**                           | **Python (`list`)**               |
|--------------------------------------|----------------------------------------------|-----------------------------------------------|-----------------------------------|
| **Sum of Elements**                  | `int sum = Arrays.stream(arr).sum();`        | `let sum = arr.reduce(0, +)`                  | `sum_ = sum(arr)`                 |
| **Product of Elements**              | `int product = Arrays.stream(arr).reduce(1, (a, b) -> a * b);` | `let product = arr.reduce(1, *)`          | `import math; product = math.prod(arr)` |

### 9. **Advanced Array Operations**

| **Functionality**                    | **Java (`Array`)**                           | **Swift (`Array`)**                           | **Python (`list`)**               |
|--------------------------------------|----------------------------------------------|-----------------------------------------------|-----------------------------------|
| **Find Max Element**                 | `int max = Arrays.stream(arr).max().getAsInt();` | `let max = arr.max()`                        | `max_ = max(arr)`                 |
| **Find Min Element**                 | `int min = Arrays.stream(arr).min().getAsInt();` | `let min = arr.min()`                        | `min_ = min(arr)`                 |
| **Flatten Nested Arrays**            | `int[] flat = Arrays.stream(arr).flatMapToInt(Arrays::stream).toArray();` | `let flat = arr.flatMap { $0 }`            | `flat = [item for sublist in arr for item in sublist]` |

### 10. **Miscellaneous**

| **Functionality**                    | **Java (`Array`)**                           | **Swift (`Array`)**                           | **Python (`list`)**               |
|--------------------------------------|----------------------------------------------|-----------------------------------------------|-----------------------------------|
| **Array Hash Code**                  | `int hash = Arrays.hashCode(arr);`           | `let hash = arr.hashValue`                    | `hash_ = hash(tuple(arr))`        |

This table provides a comparison of array operations in Java, Swift, and Python, highlighting the similarities and differences across these languages.