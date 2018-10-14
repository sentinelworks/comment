# Palindome

    Brute Force: Complete Search

    1. base conversion
    2. palindrome


    a. table base conversion:
        "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ"[ val % base];
    b. computation conversion:
        digit = val % base;
        if (digit <10) : ch = digit + '0';
        else : ch = digit-10 + 'a';
