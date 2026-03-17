# Ex. No: 17A - Generate a Graph for a Given Fixed Degree Sequence

## AIM:
To write a Python program to generate a graph for a given **fixed degree sequence**.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Check if the sum of the degree sequence is even.  
> (A necessary condition for the sequence to be graphical.)

- If not even, print an error message and exit the program.

**Step 3**: Use the **Havel-Hakimi algorithm** to determine whether a simple graph can be constructed from the sequence, and to generate the graph.

**Step 4**: If the graph is successfully created, **visualize it** using a graph drawing function (e.g., `networkx.draw()`).

**Step 5**: End the program.

## PYTHON PROGRAM

```

# Name: Vikram GS
# Reg No: 212222060296

degree = [2, 1, 1]

graph = {i: [] for i in range(len(degree))}

for i in range(len(degree)):
    for j in range(i+1, len(degree)):
        if degree[i] > 0 and degree[j] > 0:
            graph[i].append(j)
            graph[j].append(i)
            degree[i] -= 1
            degree[j] -= 1

print("Generated Graph:")
for node in graph:
    print(node, "->", graph[node])

```

## OUTPUT
```
Generated Graph:
0 -> [1, 2]
1 -> [0]
2 -> [0]

```

## RESULT

Graph is generated successfully for the given degree sequence.
