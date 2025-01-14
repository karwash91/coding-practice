# Two Pointers

### Time Complexity
- **O(n)**: Typically linear when traversing the array once.
  
### Space Complexity
- **O(1)**: No extra space required.

### Best Situations to Use
- When you need to traverse an array or list from both ends toward the center or compare elements at different positions.
- Useful for problems involving **sorted arrays**, **finding pairs**, **removing duplicates**, or **partitioning data**.

---

## Example: Checking for a Pair with a Target Sum in a Sorted Array
```python
def has_pair_with_sum(arr, target):
    """
    Given a sorted array, returns True if there is a pair of numbers that adds up to the target.
    
    Args:
    - arr: List[int] (sorted array)
    - target: int (target sum)
    
    Returns:
    - bool: True if a pair exists, otherwise False
    """
    left, right = 0, len(arr) - 1  # Initialize two pointers at the start and end of the array

    while left < right:
        current_sum = arr[left] + arr[right]
        if current_sum == target:
            return True  # Pair found
        elif current_sum < target:
            left += 1  # Move left pointer to increase the sum
        else:
            right -= 1  # Move right pointer to decrease the sum
    
    return False  # No pair found

# Example usage:
arr = [1, 2, 3, 4, 6]
target = 9
print(has_pair_with_sum(arr, target))  # Output: True
