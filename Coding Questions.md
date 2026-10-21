# Python Coding Practice

A collection of common Python coding interview questions, solutions, outputs, and key concepts.

## Table of Contents

1. [Check Whether a String or Number Is a Palindrome](#1-check-whether-a-string-or-number-is-a-palindrome)
2. [Find Common Elements Between Two Lists](#2-find-common-elements-between-two-lists)
3. [Combine Two Lists](#3-combine-two-lists)
4. [Square the Even Numbers Using List Comprehension](#4-square-the-even-numbers-using-list-comprehension)
5. [Sort a List Without Using Built-in Methods](#5-sort-a-list-without-using-built-in-methods)
6. [Reverse a String Without Using Built-in Methods](#6-reverse-a-string-without-using-built-in-methods)
7. [Find Duplicate Elements in a List](#7-find-duplicate-elements-in-a-list)
8. [Count Vowels in a String](#8-count-vowels-in-a-string)
9. [Flatten a Nested List](#9-flatten-a-nested-list)
10. [Add Two 2D Matrices](#10-add-two-2d-matrices)
11. [Find Pairs of Songs Whose Durations Add Up to a Target](#11-find-pairs-of-songs-whose-durations-add-up-to-a-target)
12. [Generate the Fibonacci Series](#12-generate-the-fibonacci-series)

---

## 1. Check Whether a String or Number Is a Palindrome

A palindrome is a word or number that reads the same forward and backward.

```python
def is_palindrome(text):
    text = str(text)
    return text == text[::-1]


print(is_palindrome("racecar"))  # True
print(is_palindrome("python"))   # False
print(is_palindrome(12321))      # True
```

**Output:**

```text
True
False
True
```

**Key concept:** `text[::-1]` reverses a string.

---

## 2. Find Common Elements Between Two Lists

Find the elements that appear in both lists.

### Approach 1: Using a `for` loop

```python
l1 = [1, 3, 5, 9]
l2 = [9, 2, 4, 3]

for i in l1:
    if i in l2:
        print(i)
```

**Output:**

```text
3
9
```

### Approach 2: Using Sets

```python
l1 = [1, 3, 5, 9]
l2 = [9, 2, 4, 3]

result = set(l1).intersection(set(l2))
print(result)
```

**Possible output:**

```text
{3, 9}
```

**Key concept:** `intersection()` returns the elements common to both sets. Sets do not guarantee the order of elements.

---

## 3. Combine Two Lists

Use the `+` operator to concatenate two lists.

```python
a = [1, 2, 3]
n = [2, 3, 5]

print(a + n)
```

**Output:**

```text
[1, 2, 3, 2, 3, 5]
```

**Key concept:** List concatenation combines two lists into a new list without removing duplicates.

---

## 4. Square the Even Numbers Using List Comprehension

Generate the squares of even numbers from 0 to 9.

```python
squares = [i * i for i in range(10) if i % 2 == 0]

print(squares)
```

**Output:**

```text
[0, 4, 16, 36, 64]
```

**Key concepts:**

- `range(10)` generates numbers from 0 to 9.
- `i % 2 == 0` checks whether a number is even.
- `i * i` calculates the square of a number.
- The `if` condition comes after the `for` loop in this list comprehension.

---

## 5. Sort a List Without Using Built-in Methods

Use the **Bubble Sort** algorithm to sort a list in ascending order.

```python
dummy_list = [11, 33, 55, 78, 89, 156, 102]

n = len(dummy_list)

for i in range(n):
    for j in range(n - i - 1):
        if dummy_list[j] > dummy_list[j + 1]:
            dummy_list[j], dummy_list[j + 1] = (
                dummy_list[j + 1],
                dummy_list[j]
            )

print(dummy_list)
```

**Output:**

```text
[11, 33, 55, 78, 89, 102, 156]
```

**Key concept:** Compare adjacent elements and swap them if they are in the wrong order.

---

## 6. Reverse a String Without Using Built-in Methods

Reverse a string by iterating through its characters.

```python
dummy_string = "ask me any question"
support_string = ""

for char in dummy_string:
    support_string = char + support_string

print(support_string)
```

**Output:**

```text
noitseuq yna em ksa
```

**Key concept:** Add each new character to the beginning of the result string.

---

## 7. Find Duplicate Elements in a List

Find the elements that appear more than once in a list.

```python
numbers = [1, 2, 3, 2, 4, 5, 3, 6]
duplicates = []

for i in range(len(numbers)):
    for j in range(i + 1, len(numbers)):
        if numbers[i] == numbers[j] and numbers[i] not in duplicates:
            duplicates.append(numbers[i])

print(duplicates)
```

**Output:**

```text
[2, 3]
```

**Key concept:** Compare each element with the elements that come after it. Store each duplicate only once.

---

## 8. Count Vowels in a String

Count how many vowels (`a`, `e`, `i`, `o`, `u`) are present in a string.

```python
text = "Hello World"
vowels = "aeiou"
count = 0

for char in text.lower():
    if char in vowels:
        count += 1

print(count)
```

**Output:**

```text
3
```

**Key concept:** Check each character against the vowels and increase the count when a match is found.

---

## 9. Flatten a Nested List

Convert a list containing nested lists into a single flat list.

```python
nested_list = [[1, 2], [3, 4], [5, 6]]
flat_list = []

for sublist in nested_list:
    for item in sublist:
        flat_list.append(item)

print(flat_list)
```

**Output:**

```text
[1, 2, 3, 4, 5, 6]
```

**Key concept:** Use a nested loop to access each element and append it to a new list.

**Note:** This example handles a list nested one level deep.

---

## 10. Add Two 2D Matrices

Add two matrices by adding the elements at the same positions.

```python
a = [[1, 2], [3, 4]]
b = [[2, 3], [4, 7]]


def add(a, b):
    result = [[0, 0], [0, 0]]

    for i in range(2):
        for j in range(2):
            result[i][j] = a[i][j] + b[i][j]

    return result


print(add(a, b))
```

**Output:**

```text
[[3, 5], [7, 11]]
```

### Explanation

Matrix A:

```text
1  2
3  4
```

Matrix B:

```text
2  3
4  7
```

Add the elements at the same positions:

- First row: `1 + 2 = 3` and `2 + 3 = 5`
- Second row: `3 + 4 = 7` and `4 + 7 = 11`

Result:

```text
3  5
7 11
```

**Key concepts:**

- A 2D list represents a matrix in Python.
- The outer loop (`i`) iterates through the rows.
- The inner loop (`j`) iterates through the columns.
- `result[i][j] = a[i][j] + b[i][j]` adds the corresponding elements.
- Both matrices must have the same dimensions for element-wise addition.

---

## 11. Find Pairs of Songs Whose Durations Add Up to a Target

Find pairs of songs whose durations add up to 9 minutes.

```python
songs = [
    ("Song A", 7),
    ("Song B", 3),
    ("Song C", 9),
    ("Song D", 2),
    ("Song E", 6),
    ("Song F", 4),
    ("Song G", 8),
    ("Song H", 1),
    ("Song I", 5),
    ("Song J", 10)
]

for i in range(len(songs)):
    for j in range(i + 1, len(songs)):
        if songs[i][1] + songs[j][1] == 9:
            print(songs[i], songs[j])
```

**Output:**

```text
('Song A', 7) ('Song D', 2)
('Song A', 7) ('Song H', 1)
('Song B', 3) ('Song E', 6)
('Song F', 4) ('Song I', 5)
('Song G', 8) ('Song H', 1)
```

**Key concepts:**

- `songs[i][1]` accesses the duration of the first song.
- `songs[j][1]` accesses the duration of the second song.
- The condition checks whether their total duration is 9.
- `range(i + 1, len(songs))` avoids comparing a song with itself and prevents duplicate pairs.
- Nested loops compare each unique pair of songs.

---

## 12. Generate the Fibonacci Series

Generate the first 10 numbers of the Fibonacci series.

In this series, each number is the sum of the previous two numbers.

```python
n = 10

a = 0
b = 1

for i in range(n):
    print(a, end=" ")
    a, b = b, a + b
```

**Output:**

```text
0 1 1 2 3 5 8 13 21 34
```

**Key concepts:**

- `a = 0` and `b = 1` initialize the first two numbers.
- `print(a, end=" ")` prints the current number on the same line.
- `a, b = b, a + b` updates both variables to generate the next number.
- `range(n)` repeats the process 10 times.

**Remember:** Print the current number, update both variables, and repeat.

---

## Summary

| No. | Problem | Main Concept |
|---:|---|---|
| 1 | Palindrome | String slicing |
| 2 | Common elements | Loops and sets |
| 3 | Combine lists | List concatenation |
| 4 | Square even numbers | List comprehension |
| 5 | Sort a list | Bubble Sort |
| 6 | Reverse a string | String manipulation |
| 7 | Find duplicates | Nested loops |
| 8 | Count vowels | Conditions and loops |
| 9 | Flatten a nested list | Nested loops |
| 10 | Add two matrices | 2D lists and nested loops |
| 11 | Song duration pairs | Nested loops and tuple indexing |
| 12 | Fibonacci series | Loops and variable updates |

