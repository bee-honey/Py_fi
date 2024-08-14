Lists are one of the most commonly used data structures in Python and are highly versatile. Here’s a comprehensive overview of all list operations and methods that are useful for coding interviews:

### Basic List Operations

1. **Creating Lists**
   ```python
   # Creating a list
   my_list = [1, 2, 3, 4]
   
   # Creating an empty list
   empty_list = []
   ```

2. **Accessing Elements**
   ```python
   first_element = my_list[0]  # Accessing the first element
   last_element = my_list[-1]  # Accessing the last element
   ```

3. **Adding Elements**
   ```python
   my_list.append(5)  # Adds an element to the end
   my_list.insert(2, 2.5)  # Inserts an element at a specific position
   ```

4. **Removing Elements**
   ```python
   my_list.remove(2)  # Removes the first occurrence of 2
   popped_element = my_list.pop()  # Removes and returns the last element
   popped_element_at_index = my_list.pop(1)  # Removes and returns the element at index 1
   ```

5. **Clearing a List**
   ```python
   my_list.clear()  # Removes all elements
   ```

6. **Copying a List**
   ```python
   new_list = my_list.copy()  # Shallow copy
   ```

### List Methods

1. **Extending a List**
   ```python
   my_list.extend([6, 7, 8])  # Extends the list by appending elements from an iterable
   ```

2. **Counting Elements**
   ```python
   count_of_2 = my_list.count(2)  # Counts the number of occurrences of 2
   ```

3. **Finding the Index of an Element**
   ```python
   index_of_3 = my_list.index(3)  # Returns the index of the first occurrence of 3
   ```

4. **Reversing a List**
   ```python
   my_list.reverse()  # Reverses the elements of the list in place
   ```

5. **Sorting a List**
   ```python
   my_list.sort()  # Sorts the list in ascending order in place
   my_list.sort(reverse=True)  # Sorts the list in descending order in place
   ```

### List Comprehensions

1. **Creating a List with Comprehension**
   ```python
   squares = [x * x for x in range(6)]
   print(squares)  # Output: [0, 1, 4, 9, 16, 25]
   ```

### Iterating Through a List

1. **Iterating Through Elements**
   ```python
   for element in my_list:
       print(element)
   ```

2. **Iterating Through Indices**
   ```python
   for index in range(len(my_list)):
       print(my_list[index])
   ```

### Slicing Lists

1. **Basic Slicing**
   ```python
   sub_list = my_list[1:3]  # Returns a slice from index 1 to 2
   ```

2. **Slicing with Steps**
   ```python
   every_other_element = my_list[::2]  # Returns every other element
   ```

### Examples in Interview Context

#### Example 1: Removing Duplicates from a List
```python
def remove_duplicates(nums):
    return list(set(nums))

nums = [1, 2, 2, 3, 3, 3]
print(remove_duplicates(nums))  # Output: [1, 2, 3]
```

#### Example 2: Finding the Intersection of Two Lists
```python
def intersection(list1, list2):
    return list(set(list1) & set(list2))

list1 = [1, 2, 3, 4]
list2 = [3, 4, 5, 6]
print(intersection(list1, list2))  # Output: [3, 4]
```

#### Example 3: Flattening a Nested List
```python
def flatten(nested_list):
    flat_list = []
    for sublist in nested_list:
        for item in sublist:
            flat_list.append(item)
    return flat_list

nested_list = [[1, 2, 3], [4, 5], [6, 7, 8]]
print(flatten(nested_list))  # Output: [1, 2, 3, 4, 5, 6, 7, 8]
```

#### Example 4: Finding the Maximum Product of Two Elements in a List
```python
def max_product(nums):
    nums.sort()
    return nums[-1] * nums[-2]

nums = [1, 10, 2, 6, 5, 3]
print(max_product(nums))  # Output: 60
```

#### Example 5: Rotating a List
```python
def rotate_list(nums, k):
    k = k % len(nums)  # In case k is greater than the length of the list
    return nums[-k:] + nums[:-k]

nums = [1, 2, 3, 4, 5, 6, 7]
k = 3
print(rotate_list(nums, k))  # Output: [5, 6, 7, 1, 2, 3, 4]
```

By mastering these list operations and methods, you will be well-prepared to handle many common problems in coding interviews that involve sequences, manipulations, and transformations of data.