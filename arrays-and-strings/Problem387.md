# First Unique Character in a String
Given a string s, find the first non-repeating character in it and return its index. If it does not exist, return -1.

### Solution :smile:

```java
class Solution {
    public int firstUniqChar(String s) {
        int[] letters = new int[26]; 
        for (int i = 0; i < s.length(); i++) 
            letters[s.charAt(i)-'a'] += 1;
        
        for (int i = 0; i < s.length(); i++) 
            if (letters[s.charAt(i)-'a'] == 1) return i; 
        
        return -1;
    }
}
```
