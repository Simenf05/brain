2025-10-06 15:11

Tags: #itgk #python #numpy #matplotlib

# Tasks for itgk
---
### **1. Even or Odd Sum Checker**

**Level**: Beginner
**Focus**: Loops, conditionals, list manipulation

**Problem**:
Write a function that takes a list of integers and returns a string:

* `"even"` if the sum of the even numbers is greater than the sum of the odd numbers.
* `"odd"` if the sum of the odd numbers is greater.
* `"equal"` if the sums are the same.

**Example**:

```python
compare_even_odd([1, 2, 3, 4]) ➞ "equal"  # 2+4 == 1+3
```

---
### **2. Count Above Average**

**Level**: Beginner
**Focus**: Loops, arithmetic, conditionals, no built-in functions

**Problem**:
Write a function that takes a list of numbers and returns how many numbers are strictly above the average — **without using built-in functions** like `sum()`, `len()`, `max()`, `min()`, etc.

#### 🔍 Example:

```python
count_above_average([1, 2, 3, 4, 5]) ➞ 2
```

* The average is `3`
* Numbers `4` and `5` are above the average → result: `2`
---
### **3. Flatten Nested List**

**Level**: Intermediate
**Focus**: Recursion, list operations

**Problem**:
Write a function `flatten(lst)` that flattens a nested list of arbitrary depth.

**Example**:

```python
flatten([1, [2, [3, 4], 5]]) ➞ [1, 2, 3, 4, 5]
```

---
### **4. FizzBuzz Extended**

**Level**: Beginner
**Focus**: Conditionals, loops, string formatting

**Problem**:
Write a function that prints the numbers from 1 to `n`. But for multiples of 3, print `"Fizz"` instead of the number, and for multiples of 5, print `"Buzz"`. For numbers which are multiples of both 3 and 5, print `"FizzBuzz"`. Additionally, for numbers that are prime, append `" (prime)"` after the output.

#### 🔍 Example:

```python
fizzbuzz_extended(10)
```

#### ✅ Output:

```
1
2 (prime)
Fizz (prime)
4
Buzz (prime)
Fizz
7 (prime)
8
Fizz
Buzz
```

#### 🧠 Hints:

* Use the `%` (modulo) operator to check for multiples.
* Write a helper function `is_prime(n)` to check for primality using a simple loop.

---
### **5. Basic Matrix Multiplication**

**Level**: Easy-Intermediate
**Focus**: NumPy basics

**Problem**:
Write a function that performs matrix multiplication of two 2D NumPy arrays *without* using `numpy.matmul` or the `@` operator — just use basic indexing and loops.