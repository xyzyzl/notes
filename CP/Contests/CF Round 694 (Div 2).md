# CF Round 694 (Div 2)
Paired with div 1 round; C was 1A and D 1B, so on. 1E and 1F were not on the div 2 contest

Overall: could've done way better if I'd been more accurate on A and B or had solved D in contest. still got +20 but that was not what I needed or wanted. at least it wasn't huge - delta.

A) WA because didn't ceiling the final answer and overflow
B) WA because I didn't write the code as I intended
C) Instasolve. How was this not A?
D) Around 10 WA's, 3 in contest and 7 after contest. Instantly got the idea, spent around 30 minutes coding up something, and then spent the next two days figuring out various bugs that I managed to fuck up greatly and implant into just ten of the 144 fucking lines of code. In the contest, I thought that $w=1$ and $w=2$ would actually make a difference, but this clearly turned out not to be the case as anything that didn't become a perfect square at $w=1$ wouldn't become one at $w=2$. After the contest I realized this and removed this step. Then I got it wrong because I had forgotten to count for cases where no perfect squares exist. After fixing that, it turned out that my entire way of counting squares was wrong. I had added every single odd value into one collective sum $sq1$, not realizing that sometimes the different values encountered were not always compatible with each other. Therefore, I added another map to filter the source of each value and took the maximum out of those; doing this gave an AC. The initial observation of this question was quite nice but this question was still shit. No one likes easy and fun questions with shitty implementations.
E) not done
F) not done