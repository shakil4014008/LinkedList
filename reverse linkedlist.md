# Reverse a linked list

```py
https://practice.geeksforgeeks.org/problems/reverse-a-linked-list/1?page=1&status[]=solved&sortBy=submissions


class Solution:
    #Function to reverse a linked list.
    def reverseList(self, head):
        # Code here
        temp, prev = head, None
        
        while temp: 
            next  = temp.next
            temp.next  = prev 
            prev = temp # prev will keep pointing the the previous
            temp  = next # temp will keep moving to the right
        return prev 

## Complexity Analysis
 