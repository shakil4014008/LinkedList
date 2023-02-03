# 160.-Intersection-of-Two-Linked-Lists

```C#
        public ListNode GetIntersectionNode(ListNode headA, ListNode headB) {
     
        var hs = new Hashtable();
        var tempA = headA;
        while(tempA !=null){
            hs.Add(tempA, 1);
            tempA = tempA.next;
        } 
        while(headB !=null){
            if(hs.Contains(headB)){
                return headB;
            }
            headB = headB.next;
        } 
        return null;
        
    }
```

## Complexity Analysis

* Time Complexity: O(n)
* Space Complexity: O(n)


Solution 2: 


```C#
        public class Solution {
    public ListNode GetIntersectionNode(ListNode headA, ListNode headB) 
    {
     
        var tempA = GetCount(headA);
        var tempB = GetCount(headB);
        var diff = Math.Abs(tempA - tempB);
        if(tempA > tempB){
            GetRef(ref headA, diff);    
        } else
            GetRef(ref headB, diff);
            
        while(headA != null){
            if(headA == headB) return headA;
            
            headA = headA.next;
            headB = headB.next;
        }
        return null;
        
    }
    
    public void GetRef(ref ListNode node, int diff){
        while(diff>0){
            node = node.next;
            diff--;
        }       
      
    }
    
    public int GetCount(ListNode node){
       var count = 0;
       while(node != null){
           count++;
           node = node.next;
       } 
       return count;
    }
}
```
## Complexity Analysis

* Time Complexity: O(min(m,n))
* Space Complexity: O(1)
