# Trees

Hey, let's look at the purest kinds of tree. 

A tree here means a connected graph without simple cycles. 

A graph with no simple cycles is called acyclic--so trees are acyclic connected graphs. 

## Tree Properties

```
O              O
|    O  O     /
|    | / \   /
|    |/   \ /
O----O     O----O
          /
         O 
```

A vertex of degree 1 is called a leaf. 

Check it out, there's 5 leaves in the tree above! If any edge was removed from this tree it wouldn't be a tree anymore, since it'd no longer be connected. Remember, a connected graph requires that every single vertex is connected together into one connected component. 

If any edge gets added between two vertices it's also not a tree anymore since it'd have a simple cycle. 

Between every pair of vertices there's a unique path. 

These features are common to all trees!

Theorem 3.1. Every tree has the following properties:
1. Any connected subgraph is a tree.
2. There is a unique simple path between every pair of vertices.
3. Adding an edge between two vertices creates a cycle.
4. Removing any edge disconnects the graph.
5. If it has at least two vertices, then it has at least two leaves.
6. The number of vertices is one larger than the number of edges

