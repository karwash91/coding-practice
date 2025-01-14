# Binary Trees

### Time Complexity
- **Insert/Search/Delete**: O(h), where h is the height of the tree.
  - For a **balanced binary tree**, h ≈ log(n).
  - For a **skewed tree**, h ≈ n (worst case).
  
### Space Complexity
- **O(n)**: Space for storing n nodes.
- Additional space for recursion stack in DFS (O(h)).

### Best Situations to Use
- When hierarchical or parent-child relationships are involved.
- Used in **binary search trees (BST)**, **heaps**, and **expression trees**.
- Great for problems requiring **in-order**, **pre-order**, or **post-order** traversal.

---

## Example: Basic Binary Tree Implementation
```python
class TreeNode:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

# Example usage:
root = TreeNode(10)
root.left = TreeNode(5)
root.right = TreeNode(15)
print(root.value)  # Output: 10

 # Example: Depth-First Search (DFS) Traversals

def in_order_traversal(node):
    if node:
        in_order_traversal(node.left)
        print(node.value, end=" ")  # Process the root
        in_order_traversal(node.right)

def pre_order_traversal(node):
    if node:
        print(node.value, end=" ")  # Process the root
        pre_order_traversal(node.left)
        pre_order_traversal(node.right)

def post_order_traversal(node):
    if node:
        post_order_traversal(node.left)
        post_order_traversal(node.right)
        print(node.value, end=" ")  # Process the root

# Example: Breadth-First Search (BFS) or Level-Order Traversal

from collections import deque

def level_order_traversal(root):
    if not root:
        return
    queue = deque([root])
    while queue:
        node = queue.popleft()
        print(node.value, end=" ")  # Process the current node
        if node.left:
            queue.append(node.left)
        if node.right:
            queue.append(node.right)

# Example usage:
level_order_traversal(root)  # Output: 10 5 15




