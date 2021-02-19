# LeetCode 1125 - Smallest Sufficient Team
#DP #Bitmasks 
Given lists of strings of skills and lists of people's capabilities, find the smallest team of people that has all skills.
## Solution
$O(M2^N)$ solutions where $N$ is the number of skills total. Just iterate over all bitmasks and all people. In our DP state however, we also maintain a vector containing all of the people used along with the minimum number of people used in the team.

## Speed
Took around one hour which is normal for a easy-med plat problem. Spent around five minutes trying to test, which was kind of fruitless as the test worked. Did sniff out a few compile time bugs I wouldn't have otherwise, which was good. Overall wasn't focused enough and could've finished earlier if i had been more focused