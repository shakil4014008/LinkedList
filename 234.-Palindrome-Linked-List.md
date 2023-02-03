# 234.-Palindrome-Linked-List

```C#

public class Solution {
    public bool IsPalindrome(ListNode head) {
           
        //algorithm
        //1. insert list item into stack
        //2. Again itereate listnode and in each iteration pop the stack element and
        //compare, if each element matches, then palindrom
        
        ListNode temp = head;
        Stack<int> stack = new Stack<int>();
        bool isPalindrome = true; 
        while(temp != null){
            stack.Push(temp.val);
            temp = temp.next;
        }
        
        while(head != null){
            int top = stack.Pop();
            if(top == head.val){
               isPalindrome = true; 
            }else{
                isPalindrome = false;
                break;
            }
            
            head = head.next;
        }
        
        return isPalindrome;
    }
}


/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     public int val;
 *     public ListNode next;
 *     public ListNode(int val=0, ListNode next=null) {
 *         this.val = val;
 *         this.next = next;
 *     }
 * }
 */
```

Running Time: O(n)
