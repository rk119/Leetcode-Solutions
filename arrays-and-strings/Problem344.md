#  Reverse String
Write a function that reverses a string. The input string is given as an array of characters s.

You must do this by modifying the input array in-place with O(1) extra memory.

### Solution :smile:
```java
class Solution {
    public void reverseString(char[] s) {
        for (int i = 0, j = s.length-1; i < j; i++, j--) {
            if (s[i] == s[j]) continue;
            else {
                char temp = s[i]; 
                s[i] = s[j];
                s[j] = temp;
            }
        }
    }
}
```
