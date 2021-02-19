# APIO 2011 - Find the Path
#Dijkstra #Coordinates #Sweepline 
## Problem Statement
- Given a 2D grid with $n$ rectangles.
- Given start point $(s_x, s_y)$ and end point $(f_x, f_y)$.
- Find shortest path from $(s_x, s_y)$ to $(f_x, f_y)$ given that:
	- Cannot go through any rectangles
	- Can only change direction at edges or corners of rectangles
	- Can only travel $||$ to $x$ or $y$ axis
- $n \leq 1000$, all coordinates are between $[-10^9, 10^9]$.
## Solution
The hardest part of this problem is designing the nodes and the edges to use in the Dijkstra. The framing of the problem means that it is most likely a Dijkstra problem.

To form the edges, we look at the possible movements that we can take. Firstly, we can jump off of the current rectangle and potentially reach a new rectangle. Secondly, we can move along our current rectangle.

The vertices in this case would be every point on our rectangle, and the edges in this case would be every point on the exterior of the rectangle. However, for the full problem this would be too many (up to 1e9) points!

We can use the technique of coordinate compression to reduce the amount of points. As we have $n \leq 1000$, there can be at most $2000$ horizontal and $2000$ vertical points, for a total of at most $4000000$ points. And similarly, there can be at most $4000000$ edges. This *barely* fits into an $O(m \lg n)$ time frame worst worst case. There can probably be more optimizations but this works.

So we compress the coordinates, but keep the original coordinates so we can calculate distances. Next, we begin to build the graph. Storing each coordinate point as a node, we draw edges between adjacent points on the rectangle. Next, using sweepline, we also draw edges between points on adjacent rectangles; we must repeat this step for horizontal and vertical edges.

Finally, we just run Dijkstra's algorithm to find the shortest path.