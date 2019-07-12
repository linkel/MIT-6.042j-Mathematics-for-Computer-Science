# Intro

## Handshaking Lemma

The sum of the degrees of the vertices in a graph equals twice the number of edges.

If I have 
```
O----O
    /
   /
 O
```

You can see that we have a degree 1, 1, and 2, which sums to 4. And if we count the edges we get 2. 4 is twice that of 2. 

Every edge contributes two to the sum of the degrees, one for each endpoint. And I think reflexive connections will give 2 more degrees. 

# Connectedness

## Paths and Simple Cycles

Paths in graphs are defined similarly to digraphs. 

Let G be a graph with vertices V and edges E. A path in G is a sequence of vertices v0, ..., vk with k >= 0 such that vi to vi+1 is an edge in E for 0 <= i < k. The path is simple iff all the vi's are different, that is, vi = vj only if i = j. 

That middle part is just saying that you can't have more edges than vertices. You can have one less edge than the number of vertices though, and that's if everything is just chained up linearly so everything's got 1 or 2 degrees. 

```
O ---- O
```
Two vertices, one edge.

```
O ---- O ---- O ---- O
```
Four vertices, three edges. Makes sense!

Path is said to start at v0, to end at vk, and the length of the path is defined to be k. So if we have three nodes, the length of the path is 2! Since we count v0, v1, v2. 

An edge e is traversed n times by the path if there are n different values of i such that edge vi to vi+1 is e. 

Not sure I get that part. 

Anyhow, cycles are paths that begin and end with the same vertex. Simple cycles are those that don't cross themselves. 

A simple cycle is defined as a subgraph isomorphic (same form) to the simple cycle graph, Cn. A subgraph is obtained by restricting a graph to a subset of its vertices and then possibly deleting some additional edges... 

A subgraph, Gprime, of a graph G, is a graph whose vertices Vprime, are a nonempty subset of the vertices of G and whose edges are a subset of the edges of G. 

Endpoints of every edge of Gprime must be vertices in Vprime. 'Cause it's a graph. 

For n >=3, let Cn be the graph with vertices 1, ..., n, and edges 1 - 2, 2 - 3, ..., (n - 1) - n, n to 1. 

The last one isn't a subtraction, it's a "to". Got it. One big circle loop. 

The length of a simple cycle is the number of times the path traverse an edge which is the same as the number of distinct vertices on the path. Nice definition! Then we don't go on forever. 

## Connected Components

Connected: two vertices in a graph are connected if there's a path that starts at one and ends on another. 

You can see that for a graph (as opposed to a directed graph, digraph), it's...

1. Symmetric: if u is connected to v, then v is connected to u. 

2. Transitive: if u is connected to v and v is connected to w, then u is connected to w.

3. Reflexive: A path of length 0 connects a vertex with itself. 

Connectedness is an equivalence relation on the vertices of any graph! 

```

O----O    O-----O
 \   |
  \ |   O---O
   O
```
Here's a graph with three connected components. A graph is said to be connected if EVERY pair of vertices is connected. 

A connected component is the set of all the vertices connected to some single vertex. 

Connected components of a graph are the equivalence classes of its connectedness relation. 

So a graph is connected iff it has exactly ONE connected component! An empty graph on n vertices has n connected components. 

```
O
    O
  O
```
3 connected components, 3 vertices, empty graph. 

## Well-connectedness

What if we want connectivity that survives component failure? 

Look.

Two vertices in a graph are k-connected if they remain connected in any subgraph obtained by deleting k-1 edges. 

A graph is k-connected if every pair of its vertices are k-connected. 

```
A   Z
 \ /
  O

```
Above, A to Z is one connected. 

```
  O
 / \
A   Z
 \ /
  O
```
Above, A to Z is two connected. 

```
  O
 / \
A---Z
 \ /
  O
```
Above, A to Z is three connected. 

A simple cycle graph is 2-connected. 

So there's two concepts here, to reiterate! There's k-connected for vertices, and there's k-connected for the graph. 

A complete graph Kn is (n-1) connected. 

```
  O
 /|\
O-+-O
 \|/
  O
```
Above, a complete graph, 4 vertices. Graph is 3-connected. 

### Edge-disjoint

If 2 vertices are connected by k edge-disjoint edges (meaning no two paths traverse the same edge) then they are k-connected.

And there's Menger's theorem, which is that if 2 vertices are k-connected, then there are k edge-disjoint paths connecting them. See my example graphs above. 

## Connection by Simple Path 

Where there's a path there's a simple path. 

Lemma, formally: 
If vertex u is connected is connected to vertex v in a graph, then there is a simple path from u to v. 

Since there is a path from u to v, there must be, by the Least Number Principle, a minimum length path from u to v. If the min length is zero or 1, this min length path is itself a simple path from u to v. 

Otherwise, there's a min length path v0, v1, ..., vk from u = v0 to v = vk where k >= 2. We claim this path must be simple. 

Reminder -- a simple path is one that does not repeat vertices. 

And here's a proof! 

### Proof of Where there's a Path there's a Simple Path

Suppose the path isn't simple. That means a vertex gets crossed twice. That means that there's integers i, j, such that 0 <= i < j <= k with vi = vj. 

Then deleting the subsequence v sub i+1, ... vj yields a strictly shorter path from u to v, which contradicts minimality of given path. 

So that's like if we go along vertices 1, 2, 3, 4, 2, 3, 4, 5 to reach 5. You can see that in our steps...

```
Steps:  1 2 3 4 5 6 7 8
Vertex: 1 2 3 4 2 3 4 5
```

Where steps is our integer and vertex is our v sub integer, on steps 5 through 7 they repeat. And if we delete v sub i+1 to vj, in our case where vi = vj is at step 2 (since v sub 2 is vertex 2 and v sub 5 is vertex 2 again and it repeats to v sub 7 which is 4), v sub i+1 is 3 and we delete from 3 to step 6 to get

```
Steps:  1 2 3 4
Vertex: 1 2 4 5
```

```
1---2
    |\ 
    | \
    |  3
    | /
    |/
    4-----5 
```

For any path of length k in a graph, there is a simple path of at most k with the same endpoints. 

## Minimum Number of Edges in a Connected Graph

