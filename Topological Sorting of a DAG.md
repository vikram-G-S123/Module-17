# Ex. No: 17D - Topological Sorting of a DAG

## AIM:
To write a Python program to **print topological sorting** of a **Directed Acyclic Graph (DAG)**.

## ALGORITHM:

**Step 1**: Create a graph and add edges to represent relationships between nodes.

**Step 2**: Use a `visited` set to keep track of visited nodes and a **stack** (or list) to record the **order of nodes** after processing.

**Step 3**: Perform **DFS** for each unvisited node:
- Explore all its neighbors.
- Recursively apply DFS to each unvisited adjacent node.
- After all neighbors are visited, **push the current node onto the stack**.

**Step 4**: After DFS is complete for all nodes, the stack will contain nodes in **reverse order of their completion time**.

**Step 5**: Print the stack in **reverse** to get the **topological order**.

---

## PYTHON PROGRAM

```
# Name: Vikram GS
# Reg No: 212222060296

from collections import deque

graph = {
    1: [2, 3],
    2: [4],
    3: [4],
    4: []
}

in_degree = {i: 0 for i in graph}

for u in graph:
    for v in graph[u]:
        in_degree[v] += 1

queue = deque([i for i in in_degree if in_degree[i] == 0])

print("Topological Sort:")

while queue:
    node = queue.popleft()
    print(node, end=" ")
    for neighbor in graph[node]:
        in_degree[neighbor] -= 1
        if in_degree[neighbor] == 0:
            queue.append(neighbor)


```

## OUTPUT
```
Topological Sort:
1 2 3 4

```

## RESULT

Topological sorting of DAG is performed successfully.
