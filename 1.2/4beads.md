### 0. This is actually a circular array problem.  

    Suppose the array size is N, the really index i = i%N; or maybe (i-N) if you know i is just over N.
    Or you can concatenate the string itself, thus you can avoid the mod (%) operation

# 1. Brute force

    For each index i as a start, if i+1 can be picked into the longest substring, we pick it then do this agin on i+1. Note that, if i is w, we must treat it as b and r, one by one. We do N times of picking attempt for each i. Therefore complexity is O(N2). Just a stright forward solution.

    Time Complexity: O(N**2)

# 2. DP method

    state: the length of sucessive r or b which ends at i: r[N], b[n]
    intial state: at location 0, the intial length of successive r or b;
    state transition:
        r[i] = r[i-1]+1 if it is not 'b', else 0
        b[i] = b[i-]+1 if it is not 'r', else 0

    result: 
        first compute longest r or b sequence: r[],b[]
            from n-1 to 0: r[i-1] == r[i] if r[i] != 0
        find max value of max(r[i]+b[i-1], b[i]+r[i-1]);
        compute and find can be combined, but it is clear to be separate.

    Time Complexity: O(N)
    Space Complexity: O(N)
