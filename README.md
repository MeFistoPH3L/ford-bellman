# Ford-Bellman algorithm
Suppose an oriented weighted graph G with n vertices and m edges is given, and some vertex v is given. Find the lengths of shortest paths from a vertex v to all other vertices.

In contrast to Dijkstra's algorithm, this algorithm is also applicable to graphs containing edges of negative weight. However, if the graph contains a negative cycle, then, of course, the shortest path to some vertices may not exist (because the weight of the shortest path must be equal to minus infinity); however, this algorithm can be modified to signal a negative-weight cycle, or even to output the cycle itself.

The algorithm is named after two American scientists: Richard Bellman and Lester Ford. Ford actually invented this algorithm in 1956 while studying another mathematical problem whose subtask consisted of finding the shortest path in a graph, and Ford gave an outline of the algorithm that solved that problem. Bellman published an article in 1958 devoted specifically to the problem of finding the shortest path, and in that article he clearly formulated the algorithm as we now know it.

# Algorithm description
We assume that the graph does not contain a loop of negative weight. The case of a negative loop will be considered below in a separate section.

Let us create an array of distances d[0 \ldots n-1] which, after working through the algorithm, will contain the answer to the problem. At the beginning we fill it as follows: d[v] = 0, and all other elements of d[] are equal to infinity.

The Ford-Bellman algorithm itself consists of several phases. In each phase all edges of the graph are viewed, and the algorithm tries to perform relaxation (relaxation, weakening) along each edge (a,b) of value c. Relaxation along an edge is an attempt to improve d[b] value by d[a] + c. In fact, it means that we try to improve the answer for vertex b using edge (a,b) and the current answer for vertex a.

It is said that n-1 phases of the algorithm are sufficient to correctly compute the lengths of all shortest paths in the graph (again, we assume that there are no cycles of negative weight). For unreachable vertices the distance d[] will remain equal to infinity.
