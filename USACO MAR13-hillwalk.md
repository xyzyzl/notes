# Problem Statement
- N hills, each line segment (x1, y1) -> (x2, y2)
# Notes
- start at (0,0) on first hill, continue walking until reach (x2,y2). Then fall off onto
	- Another hill: Only touches if less than (x2, y2) for that hill
	- Nothing: End program
- Check if less than through slopes, because you are given that there is no intersection.
	- Use this comparator in the std::set of currently existing lines
- Then just simulate through the process with sweepline
	- Binary search for current hill and hop to the one directly below once the hill is over