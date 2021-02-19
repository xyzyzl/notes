# CF 1427E - Xum
#Number-Theory #Math
## Problem Statement
- Given initial number $x$ on a whiteboard.
- Make some moves (either XOR or sum of some numbers already on the whiteboard. These may be the same number) s.t. we end up with a 1 on the whiteboard somewhere.
## Solution
- First find a number that's relatively prime to $x$. 
	- One number that we can find that is relatively prime to $x$ is $x \wedge 2^{\lfloor \lg x \rfloor + 1}$. This is because for odd $x$ this equals $2^{\lfloor \lg x \rfloor + 1}(x-1)+x$, which is relatively prime to $x$.
- Through Bezout we know that there are two numbers $p, q$ s.t. $px-qy=1$. Use the [Extended Euclidean Algorithm](https://brilliant.org/wiki/extended-euclidean-algorithm/) to find these numbers.
- Make sure that both $p$ and $q$ are positive.
- Also ensure that $p$ is odd, $q$ is even. Otherwise the xor will equal 3 instead of 1 since $px-qy=1$.
- The answer will result from $px \wedge qy$.
## Mistakes
- Didn't ensure that $p$ and $q$ were positive, just adding $p+y, q+x$ multiple times solved that.
- Tried to turn $p$ and $q$ positive incorrectly, doing $p + xy, q + xy$. That doesn't even work.
- Made a couple typos in adding things to the output queue; what was being added to the queue didn't reflect what I was doing.