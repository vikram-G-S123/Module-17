# Ex. No: 17B - BFS Traversal from a Given Source Vertex

## AIM:
To write a Python program to **print BFS traversal** from a given source vertex.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Create a graph using **adjacency list representation**.

**Step 3**: Add edges between vertices using the `addEdge()` method.

**Step 4**: Implement the `BFS()` function:
- Initialize all vertices as **not visited**.
- Use a **queue** to track vertices for traversal.
- Mark the **starting vertex** as visited and enqueue it.
- Dequeue a vertex, process it, and enqueue all its **adjacent unvisited vertices** while marking them as visited.

**Step 5**: Input the **starting vertex** and perform BFS traversal from it.

**Step 6**: Print the vertices in **BFS order**.

**Step 7**: End the program.

## PYTHON PROGRAM

```
# Name: Vikram GS
# Reg No: 212222060296

from collections import deque

graph = {
    1: [2, 3],
    2: [4],
    3: [],
    4: []
}

visited = set()
queue = deque([1])

print("BFS Traversal:")

while queue:
    node = queue.popleft()
    if node not in visited:
        print(node, end=" ")
        visited.add(node)
        queue.extend(graph[node])

```

## OUTPUT

BFS Traversal:
1 2 3 4


## RESULT
DFS TRAVERSAL FROM A GIVEN SOURCE VERTEX
