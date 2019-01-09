## Emulation
The state: Thw whole picture.  Except C/F has been changed in the field, there is nothing else changed.  So we can use C/F's coordinate as the state.  If we found the same state, it means there is an endless loop.  C/F will never meet.

You can use queue, but not stack.  But you know there is only two elements in the queue.  No more!
So it is better to use just variables (current, previous), which is more like a linked list update.

## how to emulate the direction change
dir++ is the better way, but you need to use mod operator or (if a>4, a-=4)

## Loop many times

You can also loop many many times to detect the loop.  But how many times, 1000? 10000? 
Definitely 10000 is enough as your field is 10*10.


## How to save the state:
map or set (unordered or ordered)

inline bool found(state)
{
    if (not in set) {
        insert into set;
        return false;
    }
    return true;
}

