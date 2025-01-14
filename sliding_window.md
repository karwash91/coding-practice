# Sliding Window

### Time Complexity
- **O(n)**: Typically linear when moving the window across the array or string.

### Space Complexity
- **O(1)**: No extra space required in most cases, though it may vary depending on the problem.

### Best Situations to Use
- When you need to find a **contiguous subarray** or substring that meets a certain condition (e.g., maximum sum, minimum length, etc.).
- Commonly used for problems involving **fixed-size windows** or **dynamic-size windows** over arrays or strings.

---

## Example: Maximum Sum of a Subarray of Fixed Size `k`
```python
def max_subarray_sum(arr, k):
    """
    Finds the maximum sum of a subarray with fixed size k.
    
    Args:
    - arr: List[int] (array of integers)
    - k: int (size of the subarray)
    
    Returns:
    - int: Maximum sum of the subarray
    """
    max_sum = 0
    window_sum = 0

    for i in range(len(arr)):
        window_sum += arr[i]  # Add the current element to the window
        
        # When we reach the window size, calculate max and slide the window
        if i >= k - 1:
            max_sum = max(max_sum, window_sum)
            window_sum -= arr[i - (k - 1)]  # Remove the element going out of the window
    
    return max_sum

# Example usage:
arr = [2, 1, 5, 1, 3, 2]
k = 3
print(max_subarray_sum(arr, k))  # Output: 9
