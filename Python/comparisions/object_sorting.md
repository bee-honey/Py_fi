Sorting objects, such as a `Person` class, based on attributes like `name` and `age` can be done differently in Java, Swift, and Python. Here's how you can achieve this in each language:

### 1. **Java**

#### Person Class
```java
class Person {
    String name;
    int age;

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return name + " (" + age + ")";
    }
}
```

#### Sorting by Name and Age

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        List<Person> people = Arrays.asList(
            new Person("Alice", 30),
            new Person("Bob", 25),
            new Person("Charlie", 30),
            new Person("Bob", 20)
        );

        // Sorting by name, then by age
        Collections.sort(people, Comparator.comparing(Person::getName).thenComparing(Person::getAge));

        // Print sorted list
        people.forEach(System.out::println);
    }
}
```

### 2. **Swift**

#### Person Class
```swift
struct Person {
    var name: String
    var age: Int
}

extension Person: CustomStringConvertible {
    var description: String {
        return "\(name) (\(age))"
    }
}
```

#### Sorting by Name and Age

```swift
let people = [
    Person(name: "Alice", age: 30),
    Person(name: "Bob", age: 25),
    Person(name: "Charlie", age: 30),
    Person(name: "Bob", age: 20)
]

// Sorting by name, then by age
let sortedPeople = people.sorted {
    $0.name == $1.name ? $0.age < $1.age : $0.name < $1.name
}

// Print sorted list
sortedPeople.forEach { print($0) }
```

### 3. **Python**

#### Person Class
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __repr__(self):
        return f"{self.name} ({self.age})"
```

#### Sorting by Name and Age

```python
people = [
    Person("Alice", 30),
    Person("Bob", 25),
    Person("Charlie", 30),
    Person("Bob", 20)
]

# Sorting by name, then by age
sorted_people = sorted(people, key=lambda person: (person.name, person.age))

# Print sorted list
for person in sorted_people:
    print(person)
```

### 4. **Comparison of Approaches**

| **Aspect**                    | **Java**                                   | **Swift**                                   | **Python**                        |
|-------------------------------|--------------------------------------------|---------------------------------------------|-----------------------------------|
| **Sorting Method**            | `Collections.sort()` with `Comparator`     | `sorted` method on array                    | `sorted()` function with `lambda` |
| **Chaining Comparisons**      | `Comparator.comparing().thenComparing()`   | Ternary comparison in `sorted()` closure    | Tuple in `lambda` for `sorted()`  |
| **Custom Object Setup**       | `Person` class with `getName()` and `getAge()` | `Person` struct with properties          | `Person` class with attributes    |
| **Syntax Complexity**         | Requires `Comparator` and method references | Simple closure for comparison logic         | Simple tuple-based comparison     |

### 5. **Explanation**

- **Java**: Uses the `Comparator` interface for custom sorting. You can chain comparators using `Comparator.comparing()` and `thenComparing()` for multi-level sorting.
- **Swift**: The `sorted` method on arrays can take a closure for custom sorting. The closure can compare attributes directly, making it easy to sort by multiple fields.
- **Python**: The `sorted()` function is versatile and allows tuple-based sorting with a lambda function. It’s straightforward and highly readable for sorting by multiple attributes.

### 6. **Output Example**
Given the input:
```plaintext
Alice (30), Bob (25), Charlie (30), Bob (20)
```

After sorting by name and then by age, the output will be:
```plaintext
Alice (30), Bob (20), Bob (25), Charlie (30)
```

This demonstrates how each language handles sorting objects based on multiple attributes like `name` and `age`.