# Palindrome
    complete search: first search palindrome, then check if it is prime number.

# Key points

test palindrome vs prime: which one is easy? 
    bool is_palindrome(string &s): 
        i=0, j=s.size()-1: 
        while(i<j) { 
            return false if a[i++] != a[j--]
        } 
        return true

    bool is_prime(int num): 
        for (i in [2-sqrt(num)]): 
            is it divisable? if so, return false;
        return true

    C++ code for is_prime: use multiplication is also ok as sqrt() takes more time.  But sqrt() is only one time deal, but multiplcation is done every time.
        for (i=2; i*i<=number; i++) {
            if (number % i == 0) return false;
        }
        return true;

    DP method to build prime table.  If the number is very big, you need a lot of memory.  Is it worthwhile? Depends on situation!! 
         sieve of Eratosthenes : https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes

    There's no super-fast way to determine if an arbitrary number is prime by hand.  You can save all the prime number before sqrt(n) to save some division.  But it is like DP, you know its disadvantage.
        1. Find the biggest perfect square k = floor(sqrt(n)).
        2. Save all the primes less than or equal to k.
        3. Test if n is divisible by each of said primes on your list.
            If n is divisible by any of the primes, n is not prime.
        4. If n is divisible by none of the primes, n is prime.
