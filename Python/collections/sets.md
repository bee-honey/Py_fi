In Python, the `set` data structure provides a variety of operations that are useful for handling collections of unique elements. These operations are particularly valuable during coding interviews for problems involving collections, duplicates, and relationships between sets. Here’s a comprehensive overview of all set operations in Python:

### Basic Set Operations

1. **Creating Sets**
   ```python
   # Creating a set
   my_set = {1, 2, 3}
   
   # Creating an empty set (use set(), not {})
   empty_set = set()
   ```

2. **Adding Elements**
   ```python
   my_set.add(4)
   print(my_set)  # Output: {1, 2, 3, 4}
   ```

3. **Removing Elements**
   ```python
   my_set.remove(3)  # Raises KeyError if 3 is not present
   my_set.discard(3)  # Does not raise an error if 3 is not present
   ```

4. **Clearing a Set**
   ```python
   my_set.clear()  # Removes all elements
   ```

5. **Copying a Set**
   ```python
   new_set = my_set.copy()
   ```

### Set Operations

1. **Union**
   Combines elements from both sets (removing duplicates).
   ```python
   set1 = {1, 2, 3}
   set2 = {3, 4, 5}
   union_set = set1 | set2  # or set1.union(set2)
   print(union_set)  # Output: {1, 2, 3, 4, 5}
   ```

2. **Intersection**
   Elements common to both sets.
   ```python
   intersection_set = set1 & set2  # or set1.intersection(set2)
   print(intersection_set)  # Output: {3}
   ```

3. **Difference**
   Elements in `set1` but not in `set2`.
   ```python
   difference_set = set1 - set2  # or set1.difference(set2)
   print(difference_set)  # Output: {1, 2}
   ```

4. **Symmetric Difference**
   Elements in either `set1` or `set2` but not in both.
   ```python
   symmetric_difference_set = set1 ^ set2  # or set1.symmetric_difference(set2)
   print(symmetric_difference_set)  # Output: {1, 2, 4, 5}
   ```

### Subset and Superset Operations

1. **Subset**
   Check if `set1` is a subset of `set2`.
   ```python
   is_subset = set1 <= set2  # or set1.issubset(set2)
   print(is_subset)  # Output: False
   ```

2. **Superset**
   Check if `set1` is a superset of `set2`.
   ```python
   is_superset = set1 >= set2  # or set1.issuperset(set2)
   print(is_superset)  # Output: False
   ```

### Other Useful Set Methods

1. **Checking Membership**
   ```python
   print(1 in set1)  # Output: True
   print(6 in set1)  # Output: False
   ```

2. **Set Length**
   ```python
   print(len(set1))  # Output: 3
   ```

3. **Iterating Through a Set**
   ```python
   for elem in set1:
       print(elem)
   ```

4. **Frozen Sets**
   Immutable sets, useful when you need an immutable set as a dictionary key.
   ```python
   frozen_set = frozenset([1, 2, 3])
   print(frozen_set)  # Output: frozenset({1, 2, 3})
   ```

### Examples in Interview Context

#### Example 1: Removing Duplicates
```python
def remove_duplicates(nums):
    return list(set(nums))

nums = [1, 2, 3, 1, 2, 3]
print(remove_duplicates(nums))  # Output: [1, 2, 3]
```

#### Example 2: Finding Common Elements
```python
def common_elements(list1, list2):
    return list(set(list1) & set(list2))

list1 = [1, 2, 3, 4]
list2 = [3, 4, 5, 6]
print(common_elements(list1, list2))  # Output: [3, 4]
```

#### Example 3: Checking for Subset
```python
def is_subset(list1, list2):
    return set(list1).issubset(set(list2))

list1 = [1, 2]
list2 = [1, 2, 3, 4]
print(is_subset(list1, list2))  # Output: True
```

By mastering these set operations, you will be well-prepared to handle many common problems in coding interviews that involve collections of unique elements.