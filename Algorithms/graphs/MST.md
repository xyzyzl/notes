# Minimum Spanning Trees
A **spanning tree** is a tree that covers every node of a graph.

Given a weighted graph, a **minimum spanning tree** is the spanning tree with the least total weight.

## Algorithms
- Prim's / Jarnik's, better if the graph is close to a complete graph in its $O(V^2)$ adjacency matrix form. Prim is also $O(E \lg V)$ in priority queue form, which is slightly faster for dense graphs than Kruskal but not necessarily needed.
- Kruskal's, better if the graph is less dense as it runs in $O(E \lg E + E \lg V)$. If the graph is too dense this becomes around $O(V^2)$ and it is better to use Prim's.

## Problems
### $O(N^2)$ Prim
- [[USACO FEB15-superbull]]
- [[USACO OPEN19-walk]]
### Kruskal
