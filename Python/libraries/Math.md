In technical interviews, especially those focused on algorithms and system design, certain math functions and techniques are frequently used. Python provides a rich set of built-in functions and libraries to handle these. Here’s a list of commonly used math functions and concepts:

### 1. **Basic Arithmetic Operations**
   - **Addition (`+`), Subtraction (`-`), Multiplication (`*`), Division (`/`)**
   - **Integer Division (`//`)**: Divides and returns the integer part of the quotient.
   - **Modulus (`%`)**: Returns the remainder of division.
   - **Exponentiation (`**`)**: Raises a number to the power of another number.

   ```python
   x = 10
   y = 3
   print(x + y)  # Addition
   print(x - y)  # Subtraction
   print(x * y)  # Multiplication
   print(x / y)  # Division
   print(x // y) # Integer Division
   print(x % y)  # Modulus
   print(x ** y) # Exponentiation
   ```

### 2. **Math Module Functions**
   - **`math.sqrt(x)`**: Returns the square root of `x`.
   - **`math.pow(x, y)`**: Returns `x` raised to the power `y`.
   - **`math.log(x, base)`**: Returns the logarithm of `x` to the specified `base`. Default base is `e` (natural logarithm).
   - **`math.factorial(x)`**: Returns the factorial of `x`.
   - **`math.gcd(x, y)`**: Returns the greatest common divisor of `x` and `y`.
   - **`math.lcm(x, y)`**: Returns the least common multiple of `x` and `y`.
   - **`math.ceil(x)`**: Returns the smallest integer greater than or equal to `x`.
   - **`math.floor(x)`**: Returns the largest integer less than or equal to `x`.
   - **`math.isqrt(x)`**: Returns the integer square root of `x`.

   ```python
   import math

   print(math.sqrt(16))       # 4.0
   print(math.pow(2, 3))      # 8.0
   print(math.log(8, 2))      # 3.0
   print(math.factorial(5))   # 120
   print(math.gcd(54, 24))    # 6
   print(math.lcm(12, 15))    # 60
   print(math.ceil(4.2))      # 5
   print(math.floor(4.8))     # 4
   print(math.isqrt(17))      # 4
   ```

### 3. **Rounding Functions**
   - **`round(x, n)`**: Rounds `x` to `n` decimal places. If `n` is omitted, rounds to the nearest integer.

   ```python
   print(round(3.14159, 2))  # 3.14
   print(round(2.5))         # 2 (Python rounds to the nearest even number for .5)
   ```

### 4. **Min/Max/Absolute Functions**
   - **`min(x, y, ...)`**: Returns the smallest value among the arguments.
   - **`max(x, y, ...)`**: Returns the largest value among the arguments.
   - **`abs(x)`**: Returns the absolute value of `x`.

   ```python
   print(min(1, 2, 3, -1))  # -1
   print(max(1, 2, 3, -1))  # 3
   print(abs(-5))           # 5
   ```

### 5. **Trigonometric Functions (from `math` module)**
   - **`math.sin(x)`, `math.cos(x)`, `math.tan(x)`**: Returns the sine, cosine, and tangent of `x` (in radians).
   - **`math.asin(x)`, `math.acos(x)`, `math.atan(x)`**: Returns the arc sine, arc cosine, and arc tangent of `x` (returns in radians).
   - **`math.degrees(x)`**: Converts `x` from radians to degrees.
   - **`math.radians(x)`**: Converts `x` from degrees to radians.

   ```python
   import math

   angle = math.radians(30)
   print(math.sin(angle))  # 0.5
   print(math.degrees(math.asin(0.5)))  # 30.0
   ```

### 6. **Random Number Generation**
   - **`random.random()`**: Returns a random float between 0.0 and 1.0.
   - **`random.randint(a, b)`**: Returns a random integer between `a` and `b` (inclusive).
   - **`random.choice(seq)`**: Returns a random element from the sequence `seq`.
   - **`random.shuffle(lst)`**: Shuffles the list `lst` in place.
   - **`random.sample(seq, k)`**: Returns a list of `k` unique random elements from the sequence `seq`.

   ```python
   import random

   print(random.random())          # Example: 0.654321
   print(random.randint(1, 10))    # Example: 7
   print(random.choice([1, 2, 3])) # Example: 2
   lst = [1, 2, 3, 4, 5]
   random.shuffle(lst)
   print(lst)                      # Example: [3, 1, 5, 4, 2]
   print(random.sample(lst, 3))    # Example: [1, 3, 4]
   ```

### 7. **Combinatorics (from `itertools` and `math` modules)**
   - **`itertools.permutations(seq, r)`**: Returns all `r`-length permutations of the sequence `seq`.
   - **`itertools.combinations(seq, r)`**: Returns all `r`-length combinations of the sequence `seq`.
   - **`itertools.combinations_with_replacement(seq, r)`**: Returns `r`-length combinations of `seq` with replacement.
   - **`math.comb(n, k)`**: Returns the number of combinations (binomial coefficient) of `n` items taken `k` at a time.
   - **`math.perm(n, k)`**: Returns the number of permutations of `n` items taken `k` at a time.

   ```python
   import itertools
   import math

   print(list(itertools.permutations([1, 2, 3], 2)))  # [(1, 2), (1, 3), (2, 1), (2, 3), (3, 1), (3, 2)]
   print(list(itertools.combinations([1, 2, 3], 2)))  # [(1, 2), (1, 3), (2, 3)]
   print(math.comb(5, 2))                             # 10
   print(math.perm(5, 2))                             # 20
   ```

### 8. **Prime Number Checking and Generation**
   - **`math.isqrt(x)`**: Used for efficient square root calculations, helpful in prime number algorithms.
   - **`sympy.isprime(x)`**: (from the `sympy` library) Checks if a number is prime.
   - **`sympy.primerange(a, b)`**: Generates prime numbers in a range.

   ```python
   import math
   from sympy import isprime, primerange

   print(isprime(11))           # True
   print(list(primerange(1, 20))) # [2, 3, 5, 7, 11, 13, 17, 19]
   ```

### 9. **Linear Algebra (from `numpy` library)**
   - **`numpy.dot(a, b)`**: Computes the dot product of two arrays.
   - **`numpy.linalg.inv(a)`**: Computes the inverse of a matrix.
   - **`numpy.linalg.det(a)`**: Computes the determinant of a matrix.
   - **`numpy.linalg.eig(a)`**: Computes the eigenvalues and right eigenvectors of a matrix.

   ```python
   import numpy as np

   a = np.array([[1, 2], [3, 4]])
   b = np.array([[5, 6], [7, 8]])

   print(np.dot(a, b))          # [[19 22] [43 50]]
   print(np.linalg.inv(a))      # [[-2.   1. ] [ 1.5 -0.5]]
   print(np.linalg.det(a))      # -2.0
   print(np.linalg.eig(a))      # (array([-0.37228132,  5.37228132]), array([[-0.82456484, -0.41597356], [ 0.56576746, -0.90937671]]))
   ```

### 10. **Probability and Statistics**
   - **`statistics.mean(data)`**: Calculates the mean of the data.