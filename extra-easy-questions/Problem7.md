# Reverse Integer

Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-2<sup>31</sup>, 2<sup>31 - 1</sup>], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).

### Solution :smile:

```java
class Solution {
    public int reverse(int x) {
        long result = 0;
        boolean negative = false; 
        if (x < 0) negative = true;
        x = Math.abs(x);
        while (x > 0) {
            result *= 10;
            result += x % 10;
            x /= 10;
        }
        
        int answer = (int) result == result ? (int) result : 0;
        return negative && (answer != 0) ? (answer - (answer * 2)) : answer;
    }
}
```
