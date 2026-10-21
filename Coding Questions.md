# Python Coding Practice — More Problems

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

**Key concept:** Compare each element with the elements that come after it.

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

**Key
- create a 2d matrix and then add those matrix
  <img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/a09ca932-fa3e-4700-ae00-0fb8adbc8904" />

  # Python Coding Practice

## 1. Check Whether a String or Number Is a Palindrome

A palindrome is a word or number that reads the same forward and backward.

```python
def is_palindrome(text):
    # Convert to string in case a number is passed
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

**Output:**
```text
{3, 9}
```

**Key concept:** `intersection()` returns the elements common to both sets. A set does not guarantee the order of elements.

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

**Key concept:** List concatenation combines the elements of both lists into a new list. It does not remove duplicates.

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



