In Python, most built-in types and some classes in standard libraries are named with lowercase starting letters. This follows the convention for naming basic data structures and fundamental types, similar to how `list`, `dict`, and `tuple` are named. Here are some examples:

### Built-in Types
- **`list`**: Represents a mutable sequence.
- **`dict`**: Represents a dictionary, a mutable mapping of key-value pairs.
- **`set`**: Represents an unordered collection of unique elements.
- **`frozenset`**: Represents an immutable version of a set.
- **`tuple`**: Represents an immutable sequence.
- **`str`**: Represents a string.
- **`int`**: Represents an integer.
- **`float`**: Represents a floating-point number.
- **`complex`**: Represents a complex number.
- **`bool`**: Represents a Boolean value (`True` or `False`).

### Collections Module
- **`deque`**: A double-ended queue optimized for fast appends and pops from both ends.
- **`defaultdict`**: A subclass of `dict` that calls a factory function to supply missing values.
- **`namedtuple`**: Factory function for creating tuple subclasses with named fields.
- **`OrderedDict`**: A dictionary that maintains the order of keys as they are added.

### Examples and Usage

#### `list`
```python
my_list = [1, 2, 3, 4]
my_list.append(5)
```

#### `dict`
```python
my_dict = {'a': 1, 'b': 2}
my_dict['c'] = 3
```

#### `set`
```python
my_set = {1, 2, 3}
my_set.add(4)
```

#### `deque`
```python
from collections import deque

d = deque([1, 2, 3])
d.appendleft(0)
d.append(4)
```

#### `defaultdict`
```python
from collections import defaultdict

dd = defaultdict(int)
dd['a'] += 1
```

#### `namedtuple`
```python
from collections import namedtuple

Point = namedtuple('Point', ['x', 'y'])
p = Point(1, 2)
print(p.x, p.y)
```

#### `OrderedDict`
```python
from collections import OrderedDict

od = OrderedDict()
od['a'] = 1
od['b'] = 2
```

### Understanding the Naming Convention
The convention of using lowercase names for fundamental types and data structures in Python helps to differentiate them from classes that might have more complex behaviors or are intended to be used as objects instantiated from user-defined classes. It creates a clear distinction between basic, built-in functionalities and more advanced, user-defined or library-specific functionalities.