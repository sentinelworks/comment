## Greedy algorithm

find how many 1 and 2: n1, n2

starting from 0, search not 1 in 1's range [1..n-1]
search 3 in 2's range [n1, n2-1]

How to do sorting?

int get_index(&start, end, val)
{
    while(start<end && a[start] != val);
    return (start == end)? -1: start;
}

int i1=0, i2=n1, i3=n1+n2;

while(i1<n1)
{
    if (a[i1]   == 2) {
        id = get_index(i2, n1+n2);
        swap () // if (id > 0)??
        i2++;
    } else if (a[i1]   == 3) {
        id = get_index(i3, N);
        swap();
        i3++;
    }

    i1++;
}

i2=n1, i3=n1+n2;

while (i2 < n1+n2) {
    if (a[i2] == 3) {
        id = get_index(i3, N);
        swap();
        i3++;
    }

    i2++;
}

## Dutch national flag problem
Even though swap operation is smallest, we should use this algorithm as we learned in Competitive/31-Sorting-Algorithm


