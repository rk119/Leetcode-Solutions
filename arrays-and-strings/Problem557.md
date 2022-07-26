# Reverse Words in a String III
Given a string s, reverse the order of characters in each word within a sentence while still preserving whitespace and initial word order.

### Solution :smile:

```java
class Solution {
    public String reverseWords(String s) {
        StringBuilder string = new StringBuilder();
        int sLength = s.length();
        int stop = -1;
        
        for (int i = 0; i < sLength; i++) {
            if (s.charAt(i) == ' ' || i == sLength - 1) {
                for (int j = (i == sLength - 1 ? i : i-1); j > stop; j--) 
                    string.append(s.charAt(j));
                
                if (i != sLength - 1) string.append(' ');
                
                stop = i;
            }
        }
        
        return string.toString();
    }
}
```
