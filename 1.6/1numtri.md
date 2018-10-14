# 1. DFS
    dfs(row, col, sum) ==> dfs(row+1, col, newsum) and dfs(row+1, col+1, newsum)
    Time complexity: O(2**n)
    Space Complexity: O(n) only for stack

# 2. BFS
    queue items: item(row, col, sum)
    initially only item(0,0,0) queued
    Just like dfs, two items are queued for every one de-queued from the queue.
    Time Complexity: O(2**n)
    Space Complexity: O(2**n)

# 3. DP
    based on DFS or DFS, get the optimal substructure
    Time Complexity (n**2)
    Space Complexity: O(n**2)

# Key point: Time Complexity reduced by using DP
