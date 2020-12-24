# Dec. 22 POJ Mashup Summary
1. [POJ 1113](http://poj.org/problem?id=1113)
	1. Turned into convex hull + being $L$ distance away from the circle. Ended up having multiple WA's because my convex hull implementation was wrong. I needed to set the bottom left coordinate to the origin for Graham Scan to work.
		1. Got around 10 WA's before finally getting AC.
2. [POJ 2828](http://poj.org/problem?id=2828)
	1. No clue. Seems like some data structure I'm unfamiliar with, as BIT, segtree, and PBDS all don't work as well as traditional array/vector/set.
		1. Additionally POJ doesn't support PBDS so even if it did work POJ would call it a compilation error
3. [POJ 1459](http://poj.org/problem?id=1459)
	1. Seems like a network flow, which I'm completely unfamiliar with.