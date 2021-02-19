# CF Round 703 (Div. 2)
#Binary-Search 
sadge, -83.
## A
Literally took 30 minutes to solve this piece of crap, even though it was the most straightforward brute-force algorithm. Originally thought the wrong way then had to deal with literal int overflow for around 10 minutes.
## B
Didn't even solve in the contest wtf. Forgot how to calculate minimum sum of Manhattan distances even though I could've simplified to just X and Y. Almost thought of this, but only for the $n=2$ case??
## C1
Literally the easiest interactive on the site? Just binary search. Somehow I didn't write my code right and got WA for a few minutes but this was easy nonetheless
## C2
This was significantly harder. I tried to modify the binary search, but there was one thing that didn't work. The solution turned out to be a lot easier, just binary searching over the distance from the 2nd max to either the left or the right. 
## D
Tried using PBDS. I then realized that this worked only for finding $k$, and it would be $O(n(n-k))$ to brute force for all $i \geq k$. Actually realized that it was still BINARY SEARCH which I ruled out because THERE WERE ALREADY TWO BINARY SEARCH PROBLEMS but NOPE it was still binary search

The correct solution was binary searching on the answer and checking for all $i$ and all sizes using prefix sums and prefix min.
## E
Didn't even get to read this during the contest. That was such a mistake. The question is *obviously* Dijkstra, the only hard part was generating edges.

The most notable fact is that edge weights are $\leq 50$. We can essentially add a node for each edge weight leading to each vertex, and then add the desired edge length from this node to each destination node.