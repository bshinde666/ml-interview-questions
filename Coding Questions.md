- sort the list without using built-in method
- <img width="1539" height="453" alt="image" src="https://github.com/user-attachments/assets/1d8abdab-c066-44c7-b85b-d86923502b7d" />

- reverse the string / list with out using built-in method
  <img width="680" height="196" alt="image" src="https://github.com/user-attachments/assets/68e2caf4-facd-4a83-97ef-da5917f80864" />

- find the duplicate present in the list 
- find the how / vowels present in the string 
- flatten the nested lists
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



