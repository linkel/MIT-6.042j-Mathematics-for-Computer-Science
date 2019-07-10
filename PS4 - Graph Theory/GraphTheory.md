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



