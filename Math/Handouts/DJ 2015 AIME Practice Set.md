# DJ 2015 AIME Practice Set
https://davidaltizio.web.illinois.edu/Compilation_of_AIME_like_problems.pdf
## Algebra
1. Just solve the quadratic, find the distance from $(c, c)$ to $(13, 7)$, and then find the area. Just as they said. Probably AIME #1 if it even is AIME difficulty to begin with.
2. Expand both sides. Cancel all of the like terms and the rest plays out nicely. AIME #1.
3. Divide both sides by $\log_2 x \log_4 x \log_6 x$. The result follows quite simply. AIME #3. 
4. (\*) Requires more observations. We need to know that $\dfrac{1}{\sqrt{3} - \sqrt{2}} = \sqrt 3 + \sqrt 2$. Letting $x = \sqrt 3 + \sqrt 2$, we needed some algebraic manipulations in order to get the final value. Around an AIME #8 or #9.
	1. Observations are *probably the hardest part* for most mid-late AIME questions in my opinion.
5. Actually turned out easier than the previous question. It turned out that $a_i = 1 + \sqrt{2i-2}$ which could be found by **just listing small examples**. AIME #4 or AIME #5.
	1. Rigorously proving this is not that easy though. Will add a proof later, right now it's just "just trust me bro".
6. This question only has **limited possibilities**. Just adding all of the possibilities sufficed. AIME #6 or #7 ish.
7. (\*) Much of the question just relied on the $t$ in the numerator and denominator summing to $2008$. This led to a relatively nice expansion, which then needed to be simplified and then calculated. Probable AIME 10 or 11.
	1. A few unfamiliar concepts.
		1. $\overline{p} = \frac{1}{p}$ if $|p| = 1$. Looking at a unit circle this makes sense, but I didn't intuitively think of this.
		2. Could probably have guessed everything being real because nice=probable answer, but it is hard to prove.
		3. Expanding $11^x$ into $(10+1)^x$, which was really helpful in computing modulo 1000.
8. Turned into finding the number of valid fractional parts for each integral part, which then just became some simple summation. Probable AIME 11 or 12.
	1. Hardest part was finding which values worked and which didn't but this turned into a nice pattern.
9. Hard, required a lot of algebraic manipulation and quite a few observations between equalities. First noted that $b=c \implies a=d$, and then that $ad+bc = 2008$. Tried bashing at a few stages but it didn't work, but the final result was quite nice. Needed to think from multiple angles in order to get what was needed to find the answer. Most likely AIME 13. 
10. Kind of didn't actually do the required work to get the answer ~~but that will suffice~~. Started off with a bit of algebraic manipulation involving mainly the first equation into the second equation. Then the question turned into finding the largest value of $a$ given that $(a+b)(a+c)(a+d)$. Initially felt around and used AM-GM before realizing that it gave the *minimum* value of $a$ of $\dfrac{3 \sqrt[3]{528}}{2}$. This was when $a+b=a+c=a+d$. However, we could set $a+b >> a+c = a+d$. Minimizing $a+c=a+d$, we found that $a+b = 528 \implies a = 530/2 = 265$ which turned out to be right.
	1. The actual proof is pretty clever, basically using $(a+b-1)(a+c-1) \geq 0 \implies (a+b)(a+c) + 1 \geq 2a+b+c$. Repeating this for $(a+b)(a+c)$ and $(a+d)$ gives $3a+b+c+d \leq (a+b)(a+c)(a+d) + 2$, so $a \;eq \frac{(a+b)(a+c)(a+d)+2}{2} = \frac{530}{2} = 265$. $\blacksquare$
	2. Can't gauge the difficulty since I'm bad but is probably 11-15 somewhere.
## Combo
1. Complementary counting; there's a $\frac{3}{4}$ probability for each topping that the two pizzas don't both have this topping. The answer is $1-(\frac{3}{4})^4$. Probably AIME 1.
2. Just casework on the transposition type. Make sure to count $1 \to 2 \to 3 / 3 \to 2 \to 1$ cycles separately because going backwards or forwards actually makes a difference. Probably AIME 3 or 4 level.
3. This one appeared hard for me because you could go up, down, right, or up/right; more than the easy down/right or up/right two-directional network. However, I observed that there were only 7 ways to move from the left column to the right column, and that this repeated itself for the other two column transitions. Moving vertically didn't matter at all because the only points that mattered were left -> right transitions. This type of observation-based question will very likely show up on the AIME. Probably AIME 4-6.
4. Required some observation that if $|step| \leq 50$, then the total number of sequences is $|step|$. If $|step| > 50$, then there are only $100-|step|$ options that have enough terms. AIME 7-8?
5. This also appeared hard because the problem statement was an essay and you don't know the number of players. But after fixing the number of players $A$ I got some expressions for the total number of points in terms of $A$ and $n$. Setting variables for unknowns seemed to be the important step here. AIME 9?
6. Basic observation is that you can only move 5 up in 3, 4, or 5 intervals of upwards movements, and the same for rightwards movements. Also note that having 3 up and 5 right and vice versa is impossible. The rest follows quite directly. AIME 8-ish.
7. The idea is simple enough, that each configuration of the top row and leftmost column leads to one valid array. Thus, there are $2013^{4025}$ different arrays. The hardest part in my opinion was finding this value modulo 1000. Definitely AIME 12-ish.
	1. The idea is to first use Euler's totient theorem to simplify the $2013^{4025}$ to just $2013^{25} \pmod{1000}$. Next, hand calculate to find $13^{25} \equiv 68 \pmod{125}$ and $13^{25} \equiv 5 \pmod 8$. We then find that $-78 \cdot 8 + 5 \cdot 125 = 1$, so from Chinese Remainder Theorem we have that the answer is $5 + (68-5) \cdot (-78) \cdot 8 \equiv \boxed{693} \pmod{1000}$.
	2. This part was hard because I didn't really know to use Euler's totient theorem to simplify the value. Could have also used binomial theorem in the second step.
8. Expected value is the main concept here, but that was quite easy to find out. Just $\frac{\binom{1000}{k} \cdot k(1000-k)}{2^{1000}}$. The real hard part is the algebra needed to get to the final answer
	1. That required expanding the binomial coefficient, but ended up pretty nice and not requiring too much calculation
	2. Probably AIME 11.
9. The central observation is not that hard to find, that all numbers divisible by 3 need to be in different sets. The ensuing casework isn't hard to find but is difficult to execute. Probably AIME 13-15.
	1. Need to count all possible cases and check if they're supposed to be ordered or not.
10. I did do this but I'm not sure if I'm right or not
## Geometry
1. this is a mathcounts problem.
2. I got stuck on this for a hilariously long time and I don't even know why. Let $M$ be the midpoing of $YZ$. Then $D$ sweeps out a circle of radius 1 centered at $M$. $PD$ is maximized whne $P,M,D$ are collinear.
3. Straight pythag application that I think is around AIME 4-6.
4. I used calculus although I don't think it's necessary. 
	1. The actual solution used trig but screw all that
		Let $O_1$ be the center of the first circle and $O_2$ be the center of the second circle. Also let $P_1$ be the projection of $O_1$ onto $XY$ and $P_2$ be the projection of $O_1$ onto $XY$. We know that $\angle O_1PP_1 + \angle O_2PP_2 = 90^\circ$. Let $P_1P = x$. Then, we know that $P_2P = \frac{12}{5} \sqrt{25-x^2}$. By maximizing the product $XP \cdot YP$, we want to find the maximum $P_1P \cdot P_2P$, because the former is just 4 times the latter.
		Let $f(x) = x \cdot \frac{12}{5} \sqrt{25-x^2}$. We want to find the $x$ value such that $f(x)$ is maximized, or that $f'(x) = 0$. We find that $f'(x) = (x \cdot \dfrac{d\sqrt{25-x^2}}{dx} + \sqrt{25-x^2} \cdot 1)$. Since $\dfrac{d\sqrt{25-x^2}}{dx} = -\dfrac{1}{2\sqrt{25-x^2}} \cdot 2x = -\dfrac{x}{\sqrt{25-x^2}}$, we have that $f'(x) = \dfrac{-x^2}{\sqrt{25-x^2}}+\sqrt{25-x^2} = \dfrac{25-2x^2}{\sqrt{25-x^2}}$. Thus, $x$ must be $5\sqrt{2}$ because the only other solution is negative.
		Plugging back in gives $P_1P \cdot P_2P = 30$, so $XP \cdot YP = \boxed{120}$. $\blacksquare$
	
5. Turn the slopes into arctangents and calculate the arctangents. This took stupidly long because I needed to use trig identities to simplify the calculation of arctans into something I can do on my calculator (which is allowed on mandelbrots).
6. not done yet
7. This one's also trig but it was a lot nicer than 5 (and 4?). Originally tried something with areas but that turned into something quite nasty; turns out that tangents were all I needed. Needed to remember another trig identity (tangent half angle and its various forms). Will need to look into this before the AMC 12 and AIME as it'll be useful there. I'm also spectacularly bad at trig, so this question took a lot of time and I can't give an objective difficulty rank.
8. Found $AN$ with Law of Sines, and then found $AT$ using similar triangles. 
	1. Always look for angle relations and similar triangles in a diagram.
	2. Always find right angles because there are a multitude of properties involving them.
	3. Remember Extended Law of Sines.
9. Note that $\frac{2}{9}$ of a quadrilateral is clipped with `clip(quadrilateral)` and that $\frac{4}{81}$ of an octagon is clipped with `clip(octagon)`. Therefore, we can use Engineer's Induction to guess that a $4x$-gon will have $(\frac{2}{9})^x$ of itself clipped out.
	1. Getting to the Engineer's Induction part is really hard because Engineer's Induction doesn't provide enough insurance that what I was doing actually worked. I spent way too much time trying to work through small cases to see a trend and didn't just go "just trust me bro" like earlier
	2. Probably would've just gone "just trust me bro" during a contest
	3. Also got tripped up by me forgetting the geometric series formula for 20 minutes and I'm ashamed of myself
	4. This took like 2 hours and I don't know how.