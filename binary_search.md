# Binary Search

### Time Complexity:
- **Average/Worst Case**: O(log n)
- **Best Case**: O(1) (when the target is the middle element)

### Space Complexity:
- **Iterative**: O(1) (constant space)
- **Recursive**: O(log n) (due to recursive call stack)

---

### When to Use:
- When the array is **sorted**.
- To find an element or determine if it exists efficiently.
- Great for searching in large datasets with sorted data.

---

### Implementation (Iterative)
```python
def binary_search(nums, target):
    """
    Perform binary search to find the target in a sorted array.

    Args:
        nums (List[int]): A sorted list of integers.
        target (int): The integer to search for.

    Returns:
        int: The index of the target if found, else -1.
    """
    left, right = 0, len(nums) - 1

    while left <= right:
        mid = (left + right) // 2
        if nums[mid] == target:
            return mid
        elif nums[mid] < target:
            left = mid + 1
        else:
            right = mid - 1

    return -1

# Example usage:
nums = [1, 3, 5, 7, 9, 11]
target = 7
print(binary_search(nums, target))  # Output: 3
