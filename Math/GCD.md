# GCD (Greatest Common Divisor)

## Overview
GCD finds the largest positive integer that divides both numbers without a remainder.

## Algorithm

1. If both numbers are equal, return that number.
2. Ensure `a` is the smaller number.
3. Compute remainder = b % a.
4. Replace:
b = a, 
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


## Algorithm: Euclidean Algorithm

### Steps
1. If `b == 0`, return `a`
2. Otherwise, recursively find GCD(b, a % b)
3. Base case ensures we get the GCD

## Implementations

### Java - Iterative
```java
public static int findGCD(int a, int b) {
    while (b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}
```


### Java - Recursive
```java
public static int findGCD(int a, int b) {
    if (b == 0)
        return a;
    return findGCD(b, a % b);
}
```

## Complexity Comparison

| Algorithm | Time Complexity | Space Complexity | Notes |
| --- | --- | --- | --- |
| Euclidean (Iterative) | O(log(min(a, b))) | O(1) | Most efficient, no recursion |
| Euclidean (Recursive) | O(log(min(a, b))) | O(log(min(a, b))) | Call stack depth increases |
| Subtraction Method | O(max(a, b)) | O(1) | Much slower for large numbers |
| Binary GCD (Stein's) | O(log(min(a, b))) | O(log(min(a, b))) | Optimized, fewer divisions |
| Naive (Brute Force) | O(min(a, b)) | O(1) |  |