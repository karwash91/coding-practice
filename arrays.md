# Arrays

### Time Complexity:
- **Accessing an element by index**: O(1)
- **Inserting/Deleting at the end**: O(1) (on average)
- **Inserting/Deleting at the beginning or middle**: O(n) (due to shifting elements)
- **Searching for an element**: O(n) (linear search), O(log n) (binary search if sorted)

### Space Complexity:
- O(n) (where n is the number of elements in the array)

---

### When to Use:
- When you need **fast random access** by index.
- When the size of the data structure is fixed or changes infrequently.
- Useful for problems involving contiguous storage like sliding window, two-pointer techniques, or dynamic programming.

---

### Implementation: Basic Array Operations
```python
# Creating an array
arr = [1, 2, 3, 4, 5]

# Accessing an element by index (O(1))
print(arr[2])  # Output: 3

# Adding an element at the end (O(1))
arr.append(6)
print(arr)  # Output: [1, 2, 3, 4, 5, 6]

# Removing the last element (O(1))
arr.pop()
print(arr)  # Output: [1, 2, 3, 4, 5]

# Inserting an element at a specific position (O(n))
arr.insert(2, 10)
print(arr)  # Output: [1, 2, 10, 3, 4, 5]

# Removing an element by value (O(n))
arr.remove(10)
print(arr)  # Output: [1, 2, 3, 4, 5]

# Searching for an element (O(n) for unsorted arrays)
print(4 in arr)  # Output: True
print(arr.index(4))  # Output: 3

# Iterating through an array (O(n))
for num in arr:
    print(num, end=' ')  # Output: 1 2 3 4 5
