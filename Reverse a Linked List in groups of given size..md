# Reverse a Linked List in groups of given size.

```py
https://practice.geeksforgeeks.org/problems/reverse-a-linked-list-in-groups-of-given-size/1

class Solution:
    # do k item at a time and then call recursive function
    def reverse(self,head, k):
        # Code here
        if head is None: return 
    
        temp, prev, next, count  = head, None, None, 0 
        
        while count < k and temp: 
            next  = temp.next
            temp.next = prev
            prev = temp
            temp = next
            count += 1
            
        if next: 
            head.next  = self.reverse(next, k)
        return prev
```
## Complexity Analysis
 