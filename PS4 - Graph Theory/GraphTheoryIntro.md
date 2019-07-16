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

A graph with k vertices and n edges has at least k minus n connected components. 

Seems to make sense! If I have 3 vertices and they're connected in a triangle that's 3 vertices and 3 edges, and it's got at least 0 connected components (it's got 1). 

```
O---O
 \ /
  O
```

This one's got 3 vertices and 2 edges! It's got at least 1 connected component, yep.
```
O---O---O
```

```
O---O   O
```
3 vertices and 1 edge! It's got at least 2 connected components.

```
O O O
```
3 vertices, no edges. At least 3 connected components. 

Okay, how can we prove it?

We use induction on the # of edges. Let P(n) be that for every k, every graph with k vertices and n edges has at least k minus n connected components. 

Base case: In a graph that's got 0 edges and k vertices, each vertex is itself a connected component, and so there's exactly k = k - 0 connected components. 

Inductive step: We assume that the induction hypothesis P(n) holds for every n-edge graph and prove that it holds for every (n + 1)-edge graph where n >= 0.

Let's take a graph G that has n + 1 edges and k vertices. We want to show that G has at least k minus (n + 1) connected components. 

If we remove an arbitrary edge u to v and call the resulting graph Gprime, G prime has at least k - n connected components by the induction hypothesis. Because this guy has k vertices and n edges, he's the original assumption up to n. 

Now let's add back that edge u to v to obtain the original graph G. 

There's two cases:

1. If u and v were in the same connected component of G prime, then G has the same connected components as G prime! So G has at least k - n > k - (n+1) components. 

2. Otherwise, if u and v were in different connected components of G prime, then by adding it back those two components merge into one in G, and all other components remain unchanged in G, thus reducing the number of components by 1. 

So G has at least (k - n) - 1 connected components. This is equal to k - (n + 1) connected components. 

### Corollary

Every connected graph with n vertices has at least n - 1 edges. 

Induction is a common proof style for graphs. It's often done on the number of edges in the graph, or the number of vertices. Think about induction on these when you hit a graph problem, says the text. 

In our inductive step in the previous proof, we took this (n + 1)-edge graph and threw out an edge to apply the induction assumption, then put the edge back. Apparently this is pretty common! Use the shrink-down, grow-back arguments. Beware thinking that you can just start with an n-edge graph and add one more to get an n+1 edge graph. That opens up some logical errors in certain proofs. 