# 1. Do a simulation
    some years are 365 days, some years are 366 days.

# 2. Zeller's congruence

    int k = year % 7; // The year of the century
    int j = (int)(year / 100.0); // the century
    int q = day;
    int m = month;
    int h = (q + (int)((26 * (m + 1)) / 10.0) + k + (int)(k / 4.0) + (int)(j / 4.0) + (5 * j)) % 7;

    https://en.wikipedia.org/wiki/Zeller%27s_congruence
    https://www.geeksforgeeks.org/zellers-congruence-find-day-date/
