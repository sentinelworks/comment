# 1. keep track of its name and money balance.  Just do a simulation.

    How to record the money for the name?
        Hash table: hash string to an integer

# 2. C++ STL unorder_map<string, int> or unorder_set<>:

    What is the hash buckets?
    What is the hash algorithm? map key to the bucket id

# 3. Sometimes you must write your own hash table 

    How to represent bucket for overflow? linked list, vector, array?
    Multi-stage hash table: 
        Suppose you use array (for example, 8 slots for each bucket). if one bucket is full, overflowed to the next stage hash table with different hash function.
    Left or right hash table
        If the bucket is full, overflow to my left or right bucket, which is decided by a different hash function.

    Perfect hash: one items maps to one bucket (it is one-to-one map):
        what is difference between array and perfect hash?
        Does perfect hash really exisit?
