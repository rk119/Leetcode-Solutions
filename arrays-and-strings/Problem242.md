# Valid Anagram
Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

### Solution :smile:

```java
class Solution {
    public boolean isAnagram(String s, String t) {
        int[] letters = new int[26];
        int sLength = s.length();
        int tLength = t.length();
        for (int i = 0; i < (sLength > tLength ? sLength : tLength); i++) {
            if (i < sLength) letters[s.charAt(i)-'a']++;
            if (i < tLength) letters[t.charAt(i)-'a']--;
        }
        
        for (int letter : letters) 
            if (letter != 0) return false;
        
        return true;
    }
}
```
