### 0. This is actually a circular array problem.  

    Suppose the array size is N, the really index i = i%N; or maybe (i-N) if you know i is just over N.
    Or you can concatenate the string itself, thus you can avoid the mod (%) operation

# 1. Brute force

For each index i as a start, if i+1 can be picked into the longest substring, we pick it then do this agin on i+1. Note that, if i is w, we must treat it as b and r, one by one. We do N times of picking attempt for each i. Therefore complexity is O(N2). Just a stright forward solution.

# 2. DP method

We denote substring composed by successive r, which ends at index i to ti,r

    .

ti,r={ti−1,r+10if ai is r or wif ai is b or i > N

Similarly, we denote substring composed by successive b, which ends at index i
to ti,b

.
ti,b={ti−1,b+10if ai is b or wif ai is r or i > N

On the other hand, we denote substring composed by successive r, which starts at index i
to si,r

.
si,r={si+1,r+10if ai is r or wif ai−1 is b or i=0

And substring composed by successive b, which starts at index i
to ti,b

.
si,b={si+1,b+10if ai is b or wif ai−1 is r or i=0

For each index ai
, max{si,r,si,b}+max{ti,r,ti,b} is the length of longest substring if we break it at index i. We do this for N times, the greatest one is the answer. Complexity of this algorithm is O(n).
