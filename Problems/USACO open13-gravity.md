#Graphs #BFS
# Problem Details
- Start at point $C$, want to get to point $D$
- Everything is on a $N \times M$ grid, with `#` signifying a solid block and `.` an empty block
- Fall to the highest solid block below/lowest solid block above, depending on gravity
- At each step, you can:
	1. Flip gravity (determines if you move to highest solid block below/lowest solid block above)
	2. Move left
	3. Move right
- Find minimum # of gravity flips, or state that it's impossible to reach $D$.
# Solution Steps
## Abstractly
- Flip
	- Just simulate the flip and the fall, which is at most $O(N)$. Terminate if solid block reached (ok), $D$ reached (good), or fall out (don't consider this case).
- Move left/right
	- Ignore if hit a wall or fall out of the map
	- Otherwise move left/right and obey laws of gravity

This seems doable with BFS, considering each flip as traversing an edge. However, we can move left or right with edges of cost 0.
## Implementation Details
- Simulate falling down/up the the nearest solid block
	- Fall conditions: No falling into the void, terminate if reached $D$ while falling
- Have functions simulating flipping gravity or going left and right.
	- Left/right: make sure don't hit a wall and that fall conditions satisfied
	- Flip: make sure fall conditions satisfied
- BFS
	- Recursion: Flipping gravity
		- Make sure we're not revisiting any points
		- Add all points on the "flip" side (can call a connected component) to the BFS queue
	- Break condition: if the current connected component contains $D$.
	- So we have a graph with each block as a node. Some nodes are already connected and you just want to reach some node on some connected component.
		- BFS only between edges on each component.
# Why did this take so long?
> I'm just stupid -xyzyzl, every time he screws up but wants to assuage his wounded pride
1. This is just a hellish implementation that not even the worst of society should ever experience the pain of doing.
2. There are actually multiple BFS's, the implementation notes above only cover one BFS
3. Make sure that gravity logic is correct. Parts of each code should be worked out
4. Make sure that the starting point is actually on the ground (as opposed to in midair, which would affect the results).