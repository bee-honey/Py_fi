Certainly! Here's a comparison of dictionary operations across Java (using `Map`), Swift, and Python:

### 1. **Basic Dictionary Operations**

| **Functionality**                  | **Java (`Map`)**                          | **Swift (`Dictionary`)**                   | **Python (`dict`)**               |
|------------------------------------|-------------------------------------------|--------------------------------------------|-----------------------------------|
| **Create Dictionary**              | `Map<String, Integer> map = new HashMap<>();` | `var dict: [String: Int] = [:]`           | `dict = {}`                       |
| **Add or Update Key-Value Pair**   | `map.put("Apple", 5);`                    | `dict["Apple"] = 5`                        | `dict["Apple"] = 5`               |
| **Remove Key-Value Pair**          | `map.remove("Apple");`                    | `dict.removeValue(forKey: "Apple")`        | `dict.pop("Apple")`               |
| **Get Value by Key**               | `Integer value = map.get("Apple");`       | `let value = dict["Apple"]`                | `value = dict.get("Apple")`       |
| **Check if Key Exists**            | `boolean exists = map.containsKey("Apple");` | `let exists = dict.keys.contains("Apple")` | `exists = "Apple" in dict`        |
| **Check if Value Exists**          | `boolean exists = map.containsValue(5);`  | `let exists = dict.values.contains(5)`     | `exists = 5 in dict.values()`     |
| **Get Dictionary Size**            | `int size = map.size();`                  | `let size = dict.count`                    | `size = len(dict)`                |
| **Check if Dictionary is Empty**   | `boolean empty = map.isEmpty();`          | `let empty = dict.isEmpty`                 | `empty = not dict`                |
| **Clear Dictionary**               | `map.clear();`                            | `dict.removeAll()`                         | `dict.clear()`                    |

### 2. **Dictionary Iteration**

| **Functionality**                  | **Java (`Map`)**                          | **Swift (`Dictionary`)**                   | **Python (`dict`)**               |
|------------------------------------|-------------------------------------------|--------------------------------------------|-----------------------------------|
| **Iterate Over Keys**              | `for (String key : map.keySet()) {}`      | `for key in dict.keys {}`                  | `for key in dict:`                |
| **Iterate Over Values**            | `for (Integer value : map.values()) {}`   | `for value in dict.values {}`              | `for value in dict.values():`     |
| **Iterate Over Key-Value Pairs**   | `for (Map.Entry<String, Integer> entry : map.entrySet()) {}` | `for (key, value) in dict {}`           | `for key, value in dict.items():` |

### 3. **Accessing Keys and Values**

| **Functionality**                  | **Java (`Map`)**                          | **Swift (`Dictionary`)**                   | **Python (`dict`)**               |
|------------------------------------|-------------------------------------------|--------------------------------------------|-----------------------------------|
| **Get All Keys**                   | `Set<String> keys = map.keySet();`        | `let keys = Array(dict.keys)`              | `keys = dict.keys()`              |
| **Get All Values**                 | `Collection<Integer> values = map.values();` | `let values = Array(dict.values)`        | `values = dict.values()`          |

### 4. **Merging Dictionaries**

| **Functionality**                  | **Java (`Map`)**                          | **Swift (`Dictionary`)**                   | **Python (`dict`)**               |
|------------------------------------|-------------------------------------------|--------------------------------------------|-----------------------------------|
| **Merge Two Dictionaries**         | `map.putAll(otherMap);`                   | `dict.merge(otherDict) { (_, new) in new }` | `dict.update(otherDict)`         |

### 5. **Default Values**

| **Functionality**                  | **Java (`Map`)**                          | **Swift (`Dictionary`)**                   | **Python (`dict`)**               |
|------------------------------------|-------------------------------------------|--------------------------------------------|-----------------------------------|
| **Get Value with Default**         | `Integer value = map.getOrDefault("Apple", 0);` | `let value = dict["Apple", default: 0]` | `value = dict.get("Apple", 0)`    |

### 6. **Dictionary Comprehension/Creation**

| **Functionality**                  | **Java (`Map`)**                          | **Swift (`Dictionary`)**                   | **Python (`dict`)**               |
|------------------------------------|-------------------------------------------|--------------------------------------------|-----------------------------------|
| **Create from Arrays**             | `Map<String, Integer> map = IntStream.range(0, keys.length).boxed().collect(Collectors.toMap(i -> keys[i], i -> values[i]));` | `let dict = Dictionary(uniqueKeysWithValues: zip(keys, values))` | `dict = dict(zip(keys, values))` |

### 7. **Removing by Condition**

| **Functionality**                  | **Java (`Map`)**                          | **Swift (`Dictionary`)**                   | **Python (`dict`)**               |
|------------------------------------|-------------------------------------------|--------------------------------------------|-----------------------------------|
| **Remove Entries by Condition**    | `map.values().removeIf(value -> value > 5);` | `dict = dict.filter { $0.value <= 5 }`    | `dict = {k: v for k, v in dict.items() if v <= 5}` |

### 8. **Equality and Subset**

| **Functionality**                  | **Java (`Map`)**                          | **Swift (`Dictionary`)**                   | **Python (`dict`)**               |
|------------------------------------|-------------------------------------------|--------------------------------------------|-----------------------------------|
| **Check if Dictionaries are Equal**| `boolean equal = map.equals(otherMap);`   | `let equal = dict == otherDict`            | `equal = dict == otherDict`       |
| **Check if Dictionary Contains All Key-Value Pairs from Another** | *No direct equivalent* | `let isSubset = otherDict.allSatisfy { dict[$0] == $1 }` | `isSubset = all(item in dict.items() for item in otherDict.items())` |

### 9. **Convert to List/Array**

| **Functionality**                  | **Java (`Map`)**                          | **Swift (`Dictionary`)**                   | **Python (`dict`)**               |
|------------------------------------|-------------------------------------------|--------------------------------------------|-----------------------------------|
| **Convert Keys to List**           | `List<String> keysList = new ArrayList<>(map.keySet());` | `let keysList = Array(dict.keys)`       | `keysList = list(dict.keys())`    |
| **Convert Values to List**         | `List<Integer> valuesList = new ArrayList<>(map.values());` | `let valuesList = Array(dict.values)` | `valuesList = list(dict.values())`|

### 10. **Miscellaneous**

| **Functionality**                  | **Java (`Map`)**                          | **Swift (`Dictionary`)**                   | **Python (`dict`)**               |
|------------------------------------|-------------------------------------------|--------------------------------------------|-----------------------------------|
| **Get Hash Code**                  | `int hash = map.hashCode();`              | `let hash = dict.hashValue`                | `hash = hash(frozenset(dict.items()))` |

This table provides a quick comparison of dictionary operations in Java, Swift, and Python, showcasing the syntactical differences and functional equivalences across these languages.