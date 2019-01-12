## Shortest Path

    You should build adjacent information: adjacent matrix/list.
    1. matrix a[128][128]
    2. matrix a[51][51] 
    3. vector<list<int>> a
    For case 2 or 3, you need to convert a-y,A-Y to a number, and number to a character
    
    conversion: 
        const string = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
        int id(char ch) {
            if (ch>='a') return ch-'a';
            return ch-'A'+25;
        }

        char alpha(int ch) {
            if (ch >= 25) return 'A'+ch;
            return 'a'+ch;
        }

    for Trie, we did the similar stuff.

## Floyd-Washall Algorithm

    For gold level, we do not care about performance. But for platinum, we should care
    Floyd is O(V**3).

    DP algorithm:
        state: dp[i][j], the shortest path between vertex i and j
        initial state: dp[i][i] = 0; dp[i][j]=weight if there is a edge between i, j, all others are INF
        state transition: use every vertex as the middle node, recompute the shortest path for all pairs of vertex
        answer: shortest path

## Johnson Algorithm is better than Floyd


## Graph Representation

    adjacent matrix
    adjacent list
    edge list

## priority_queue in STL

    priority_queue<typename> is a MAX heap. It can not update the original elements in the queue when
    you push the element for the same vertex.

    use set or map? 
    use two data structure?
    use a special fibonacci heap for Dijstra?! Yes. O(NlogN)

