# Palindrome Linked List

Given the head of a singly linked list, return true if it is a palindrome.

### Solution :smile:
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public boolean isPalindrome(ListNode head) {
        ListNode fast = head;
        ListNode slow = head;
        
        while (fast != null && fast.next != null) {
            fast = fast.next.next;
            slow = slow.next;
        }
        
        ListNode previous = null;
        while (slow != null) {
            ListNode temp = slow.next;
            slow.next = previous;
            previous = slow;
            slow = temp;
        }
        
        ListNode left = head, right = previous;
        while (right != null) {
            if (left.val != right.val) return false;
            left = left.next;
            right = right.next;
        }
        
        return true;
    }
}
```
