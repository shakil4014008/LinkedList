# Basic LinkedList

```py

# init node 
class Node: 
  def __init__(self, data): 
    self.data  = data
    self.next  = None

# linkedlist graph
class LinkedList: 
  def __init__(self): 
    self.head = None 

  def print_list(self):
    temp = self.head 
    while temp: 
      print(temp.data)
      temp = temp.next 

if __name__ == '__main__': 

  llist = LinkedList()
  llist.head  = Node(10)
  second = Node(20)
  third  = Node(30)

  llist.head.next = second
  second.next = third
  llist.print_list()

      


              


## Complexity Analysis
 