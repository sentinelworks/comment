## Search using Flood Fill

    DFS flood fill: stack could over flow
    BFS flood fill:
    union-find flood fill:

## Graph represention
For maze, island, castle, etc, your matrix representation already has hidden connectivity information, which is flood fill.  Every element represent one vetex.  Every neigbor (+x, -x) may means the connectivity.  

How to represent connectivity in this graph
1. 0/1 value means that you can pass or not pass
2. bitmask means the connectivity in different direction (4 or 8 bits)
3. m[][][4] or m[][][8]
4. just one character matrix or number matrix.  The element value has the meaning.

## input which has space
1. You can use getline from string.  Or you can use cin.getline()
2. You can also use noskipws option to emulate getch() from C library

## use queue

inline void enque(state) 
{
    push into queue;
    set visited;
}

