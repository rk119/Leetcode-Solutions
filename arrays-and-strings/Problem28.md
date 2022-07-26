# Implement strStr()
Given two strings needle and haystack, return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

### Clarification:

What should we return when needle is an empty string? This is a great question to ask during an interview.

For the purpose of this problem, we will return 0 when needle is an empty string. This is consistent to C's strstr() and Java's indexOf().

### Solution :smile:
```java
class Solution {
    public int strStr(String haystack, String needle) {
        int n = needle.length(), h = haystack.length();
        
        if (n == 0) return 0;
        if (h == 0) return 0;
        
        for (int i = 0; i < h; i++) {
            if ((i + n) > h) break;
            
            for (int j = 0; j < n; j++) {
                if (haystack.charAt(i+j) != needle.charAt(j)) break;
                if (j == n-1) return i;
            }
        }
        
        return -1;
    }
}
```
