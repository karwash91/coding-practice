# Queues

### Time Complexity
- **Enqueue (push)**: O(1)
- **Dequeue (pop)**: O(1)
- **Peek (front)**: O(1)

### Space Complexity
- **O(n)**: Space is proportional to the number of elements in the queue.

### Best Situations to Use
- When solving problems involving **first-in, first-out (FIFO)** ordering.
- Useful for **breadth-first search (BFS)**, **task scheduling**, and **handling asynchronous events**.

---

## Example: Implementing a Queue Using a List
```python
from collections import deque

def bfs(graph, start):
    """
    Performs Breadth-First Search on a graph.

    Args:
    - graph: dict (adjacency list representation of the graph)
    - start: starting node

    Returns:
    - list: Nodes visited in BFS order
    """
    visited = []
    queue = deque([start])  # Using deque for efficient queue operations

    while queue:
        node = queue.popleft()  # Dequeue the front element
        if node not in visited:
            visited.append(node)
            queue.extend(graph[node])  # Enqueue all unvisited neighbors

    return visited

# Example usage:
graph = {
    'A': ['B', 'C'],
    'B': ['D', 'E'],
    'C': ['F'],
    'D': [],
    'E': ['F'],
    'F': []
}
print(bfs(graph, 'A'))  # Output: ['A', 'B', 'C', 'D', 'E', 'F']

