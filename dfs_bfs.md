# DFS & BFS (Iterative and Recursive)

### Time Complexity
- **DFS**: O(V + E), where V = vertices, E = edges.
- **BFS**: O(V + E), where V = vertices, E = edges.

### Space Complexity
- **DFS Recursive**: O(V) due to recursion stack (in the worst case).
- **DFS Iterative**: O(V) due to stack storage.
- **BFS**: O(V) due to queue storage.

### Best Situations to Use
- **DFS**: Explore all nodes in depth before backtracking. Suitable for problems involving **backtracking**, **cycle detection**, and **connected components**.
- **BFS**: Explore all neighbors first, layer by layer. Suitable for problems like **shortest path in an unweighted graph** or **level-order traversal**.

---

## Depth-First Search (DFS)

### Recursive Implementation
```python
def dfs_recursive(node, visited=set()):
    if node not in visited:
        print(node, end=" ")  # Process the node
        visited.add(node)
        for neighbor in graph[node]:
            dfs_recursive(neighbor, visited)

# Example usage:
graph = {
    1: [2, 3],
    2: [4, 5],
    3: [],
    4: [],
    5: []
}
dfs_recursive(1)  # Output: 1 2 4 5 3

def bfs_iterative(start):
    visited = set()
    queue = deque([start])
    while queue:
        node = queue.popleft()
        if node not in visited:
            print(node, end=" ")  # Process the node
            visited.add(node)
            for neighbor in graph[node]:
                queue.append(neighbor)

# Example usage:
bfs_iterative(1)  # Output: 1 2 3 4 5
