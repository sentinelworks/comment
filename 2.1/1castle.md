## flood fill (DFS)

dfs(node u)
  for each node v connected to u :
    if v is not visited :
      visited[v] = true
      dfs(v)


for each node u:
  if u is not visited :
    visited[u] = true
    connected_component += 1
    dfs(u)

Time Complexity: O(n*n)
Space Complexity: O(n)

## flood fill (BFS)

TODO

## disjoint set
my idea:  
define unvisited[][] to store mark
flood fill to mark the unvisited
find the two maximum (if there are three, this is a problem)
max_value = 0;
try to combine them together


for each node parent[node] = node

for each node u :
   for each node v connected to u :
       if findset(u)!=findset(v) :
           union(u,v)

**I assume you know about how findset and union works **
for each node if (parent[node] == node)
    connected_component += 1

Time Complexity: O(n)
Space Complexity: O(n)

The fastest algorithm for finding connected components given an edge list is the union-find algorithm: for each node, hold the pointer to a node in the same set, with all edges converging to the same node, if you find a path of length at least 2, reconnect the bottom node upwards.

This will definitely run in linear time:

- push all edges into a union-find structure: O(n)
- store each node in its set (the union-find root)
    and update the set of non-empty sets: O(n)
- return the set of non-empty sets (graph components).

Since the list of edges already almost forms a union-find tree, it is possible to skip the first step:

for each node
- if the node is not marked as collected
-- walk along the edges until you find an order-1 or order-2 loop, 
   collecting nodes en-route
-- reconnect all nodes to the end of the path and consider it a root for the set.
-- store all nodes in the set for the root.
-- update the set of non-empty sets.
-- mark all nodes as collected.
return the set of non-empty sets

The second algorithm is linear as well, but only a benchmark will tell if it's actually faster. The strength of the union-find algorithm is its optimization. This delays the optimization to the second step but removes the first step completely.

You can probably squeeze out a little more performance if you join the union step with the nearest neighbor calculation, then collect the sets in the second pass.



 Number of Islands 

Given a 2d grid map of '1's (land) and '0's (water), count the number of islands. An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.

Example 1:

     11110
     11010
     11000
     00000

Answer: 1

Example 2:

     11000
     11000
     00100
     00011

Answer: 3


 Surrounded Regions

Question

    Given a 2D board containing 'X' and 'O' (the letter O), capture all regions surrounded by 'X'.

    A region is captured by flipping all 'O's into 'X's in that surrounded region.

    For example,

    X X X X
    X O O X
    X X O X
    X O X X

    After running your function, the board should be:

    X X X X
    X X X X
    X X X X
    X O X X


 Longest Consecutive Sequence

07/13/2016 Array Union Find
Question

    Given an unsorted array of integers, find the length of the longest consecutive elements sequence.

    For example,

    Given [100, 4, 200, 1, 3, 2],

    The longest consecutive elements sequence is [1, 2, 3, 4]. Return its length: 4.

    Your algorithm should run in O(n)

    complexity.


Hash Table Way

class Solution {
public:
    int longestConsecutive(vector<int>& nums) {
        unordered_set<int> mp;
        int ret = 0;
        for(const auto x:nums)
            //if(mp.count())
            mp.insert(x);
        while(mp.size())
            {
                int x = *mp.begin();
                int left = x,right = x+1;
                while(mp.count(left))
                    mp.erase(left--);
                while(mp.count(right))
                    mp.erase(right++);
                ret = max(ret,right - left  - 1);
            }
        return ret;
    }
};


Union Find Way

class Solution {
    vector<int> id;
    vector<int> size;
public:
    int longestConsecutive(vector<int>& nums) {
        int n = nums.size();
        if(n < 2) return n;
        size = vector<int>(n,1);
        for(int i = 0; i < n; i++) {
            id.push_back(i);
        }
        unordered_map<int,int> record;
        for(int i = 0 ; i < n; i++) {
            if(record.find(nums[i]) != record.end()) continue;
            record[nums[i]] = i;
            if(record.find(nums[i]-1) != record.end()) {
                unionSet(i,record[nums[i]-1]);
            }
            if(record.find(nums[i]+1) != record.end()) {
                unionSet(i,record[nums[i]+1]);
            }
        }
        int res = *max_element(size.begin(),size.end());
        return res;
    }

    int find(int p) {
        while(p != id[p]) {
            id[p] = id[id[p]];
            p = id[p];
        }
        return p;
    }
    void unionSet(int a, int b) {
        int i = find(a);
        int j = find(b);
        if(i == j) return;
        if(size[i] > size[j]) {
            id[j] = i;
            size[i] += size[j];
        } else {
            id[i] = j;
            size[j] += size[i];
        }
    }
};

