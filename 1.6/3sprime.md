For N digits
    int d1[] = {2, 3, 5, 7};
    int do[] = {1, 3, 7, 9};

# 1. dfs
    backtracking

# 2. bfs
    same as dfs, can do backtracking
    queue<int> q, q1;
    for (i =0; i<4; ++i) q1.push(a1[i]);
    for (i =0; j< N-1; ++j) {
        q.swap(q1);
        while(q.empty()) {
            for (j = 0; j< 4; ++j) {
                m  = q.top()*10 + do[j];
                if (is_prime(m)) q1.push(m);
            }
            q.pop();
        }
    }

    dequeue from q1;

    Space Complexity: O(4**N)
