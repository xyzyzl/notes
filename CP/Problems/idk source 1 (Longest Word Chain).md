# idk source #1
#Strings #Trie 
- Have $N$ strings
	- Call a set of strings a "string chain" if each element is a prefix of the previous element.
	- Find the longest string chain.
## Solution
- Store all strings in a trie data structure
- Run DFS on the trie
	- store the number of end nodes processed at the current node
	- the answer is the maximum number of string-end nodes reached on a path to some leaf node