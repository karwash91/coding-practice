# Stacks

### Time Complexity
- **Push**: O(1)
- **Pop**: O(1)
- **Peek**: O(1)

### Space Complexity
- **O(n)**: Space is proportional to the number of elements in the stack.

### Best Situations to Use
- When solving problems involving **last-in, first-out (LIFO)** ordering.
- Ideal for **balanced parentheses**, **function call tracking**, and **undo/redo operations**.

---

## Example: Implementing a Stack
```python
def is_valid_parentheses(s):
    """
    Checks if a string contains valid parentheses.

    Args:
    - s: str (input string)

    Returns:
    - bool: True if parentheses are valid, False otherwise
    """
    stack = []
    mapping = {')': '(', '}': '{', ']': '['}

    for char in s:
        if char in mapping:
            # If stack is empty or top element doesn't match, it's invalid
            if not stack or stack[-1] != mapping[char]:
                return False
            stack.pop()
        else:
            stack.append(char)

    # Valid if stack is empty after processing
    return len(stack) == 0

# Example usage:
s = "({[]})"
print(is_valid_parentheses(s))  # Output: True

