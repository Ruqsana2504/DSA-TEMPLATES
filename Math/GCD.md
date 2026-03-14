Algorithm Steps

If both numbers are equal → return that number.
Ensure a is the smaller number.
Compute remainder = b % a.
Replace:
b = a
a = remainder
Repeat until remainder becomes 0.

Java Template

public static int findGCD(int a, int b) {
if (a == b)
return a;

    if (a > b) {
        int temp = a;
        a = b;
        b = temp;
    }

    while (true) {
        int rem = b % a;
        if (rem == 0)
            return a;
        b = a;
        a = rem;
    }
}
Complexity
Type	Complexity
Time	O(log(min(a, b)))
Space	O(1)