# GCD (Greatest Common Divisor)

## Algorithm Steps

1. If both numbers are equal, return that number.
2. Ensure `a` is the smaller number.
3. Compute remainder = b % a.
4. Replace:
b = a
a = remainder
5. Repeat until remainder becomes 0.

## Java Code
```java
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
```

## Complexity
Type	Complexity
Time	O(log(min(a, b)))
Space	O(1)