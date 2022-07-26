# Palindrome Number

Given an integer x, return true if x is palindrome integer.

An integer is a palindrome when it reads the same backward as forward.

- For example, 121 is a palindrome while 123 is not.

### Solution :smile:

```java
class Solution {
    public boolean isPalindrome(int x) {
        String num = String.valueOf(x);
        for (int i = 0, j = num.length()-1; i < j; i++, j--)
            if (num.charAt(i) != num.charAt(j)) return false;
        return true;
    }
}
```
