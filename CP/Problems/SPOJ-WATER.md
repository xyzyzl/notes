# SPOJ-WATER
#BFS #Graphs 
## Problem Statement
- given $n \times m$ grid of cuboids with varying heights
- a puddle is formed in a pool surrounded by higher cuboids
- find the maximum puddle volume
## Solution
- Start from the edges, and try to fill things in going in
	- Process each cuboid in increasing order of height using a min-heap
	- Indices being inserted will be inserted in min-heap order and the smallest value in the min-heap will be processed each time
- If an adjacent cuboid is lower than the current cuboid:
	- Through the min-heap invariant all other sides of the adjacent cuboid must be taller
	- Therefore we can set the water level of this cuboid to that of the top cuboid
- Otherwise:
	- This cuboid could still be used elsewhere, therefore we should just add this cuboid with the original height
- At the end, add the total difference between each water level and each original height
## Mistakes
- Again did the mistake described in [[Timus 2034 - Caravans]]
- Didn't reset the arrays on each test case so things didn't work as expected after the first test set in each test.