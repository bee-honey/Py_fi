Certainly! Here's a comparison of set operations across Java, Swift, and Python:

### 1. **Basic Set Operations**

| **Functionality**                      | **Java**                                   | **Swift**                                   | **Python**                       |
|----------------------------------------|--------------------------------------------|---------------------------------------------|----------------------------------|
| **Add Element**                        | `set.add("Apple");`                        | `set.insert("Apple")`                       | `set.add("Apple")`               |
| **Remove Element**                     | `set.remove("Apple");`                     | `set.remove("Apple")`                       | `set.remove("Apple")`            |
| **Check if Set Contains Element**      | `boolean exists = set.contains("Apple");`  | `let exists = set.contains("Apple")`        | `exists = "Apple" in set`        |
| **Get Set Size**                       | `int size = set.size();`                   | `let size = set.count`                      | `size = len(set)`                |
| **Check if Set is Empty**              | `boolean empty = set.isEmpty();`           | `let empty = set.isEmpty`                   | `empty = not set`                |
| **Clear Set**                          | `set.clear();`                             | `set.removeAll()`                           | `set.clear()`                    |

### 2. **Set Operations**

| **Functionality**                      | **Java**                                   | **Swift**                                   | **Python**                       |
|----------------------------------------|--------------------------------------------|---------------------------------------------|----------------------------------|
| **Union (Combine Sets)**               | `Set<String> union = new HashSet<>(set1); union.addAll(set2);` | `let union = set1.union(set2)`    | `union = set1.union(set2)`       |
| **Intersection (Common Elements)**     | `Set<String> intersection = new HashSet<>(set1); intersection.retainAll(set2);` | `let intersection = set1.intersection(set2)` | `intersection = set1.intersection(set2)` |
| **Difference (Elements in Set1 but not Set2)** | `Set<String> diff = new HashSet<>(set1); diff.removeAll(set2);` | `let diff = set1.subtracting(set2)` | `diff = set1.difference(set2)`  |
| **Symmetric Difference (Elements in Either Set, but not Both)** | `Set<String> symDiff = new HashSet<>(set1); symDiff.addAll(set2); symDiff.removeAll(intersection);` | `let symDiff = set1.symmetricDifference(set2)` | `symDiff = set1.symmetric_difference(set2)` |

### 3. **Bulk Operations**

| **Functionality**                      | **Java**                                   | **Swift**                                   | **Python**                       |
|----------------------------------------|--------------------------------------------|---------------------------------------------|----------------------------------|
| **Add All Elements from Another Collection** | `set.addAll(otherSet);`                  | `set.formUnion(otherSet)`                   | `set.update(otherSet)`           |
| **Remove All Elements in Another Collection** | `set.removeAll(otherSet);`              | `set.subtract(otherSet)`                    | `set.difference_update(otherSet)`|
| **Retain Only Elements in Another Collection** | `set.retainAll(otherSet);`              | `set.formIntersection(otherSet)`            | `set.intersection_update(otherSet)` |

### 4. **Subset and Superset Operations**

| **Functionality**                      | **Java**                                   | **Swift**                                   | **Python**                       |
|----------------------------------------|--------------------------------------------|---------------------------------------------|----------------------------------|
| **Check if Set1 is a Subset of Set2**  | `boolean isSubset = set2.containsAll(set1);` | `let isSubset = set1.isSubset(of: set2)`   | `isSubset = set1.issubset(set2)` |
| **Check if Set1 is a Superset of Set2**| `boolean isSuperset = set1.containsAll(set2);` | `let isSuperset = set1.isSuperset(of: set2)` | `isSuperset = set1.issuperset(set2)` |

### 5. **Set Equality and Disjoint**

| **Functionality**                      | **Java**                                   | **Swift**                                   | **Python**                       |
|----------------------------------------|--------------------------------------------|---------------------------------------------|----------------------------------|
| **Check if Sets are Equal**            | `boolean equal = set1.equals(set2);`       | `let equal = set1 == set2`                  | `equal = set1 == set2`           |
| **Check if Sets are Disjoint (No Common Elements)** | `boolean disjoint = Collections.disjoint(set1, set2);` | `let disjoint = set1.isDisjoint(with: set2)` | `disjoint = set1.isdisjoint(set2)` |

### 6. **Convert Set to List/Array**

| **Functionality**                      | **Java**                                   | **Swift**                                   | **Python**                       |
|----------------------------------------|--------------------------------------------|---------------------------------------------|----------------------------------|
| **Convert Set to List**                | `List<String> list = new ArrayList<>(set);` | `let list = Array(set)`                    | `list = list(set)`               |
| **Convert Set to Array**               | `String[] array = set.toArray(new String[0]);` | `let array = Array(set)`                  | `array = list(set)`              |

### 7. **Iterators**

| **Functionality**                      | **Java**                                   | **Swift**                                   | **Python**                       |
|----------------------------------------|--------------------------------------------|---------------------------------------------|----------------------------------|
| **Get Iterator**                       | `Iterator<String> it = set.iterator();`    | `var it = set.makeIterator()`               | `it = iter(set)`                 |
| **For Each Element**                   | `set.forEach(System.out::println);`        | `set.forEach { print($0) }`                 | `for item in set: print(item)`   |

This table provides a quick comparison of set operations in Java, Swift, and Python, showcasing the syntactical differences and functional equivalences across these languages.