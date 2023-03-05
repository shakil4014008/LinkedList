# Linkedlist
#  

```py

class Node:
  def __init__(self, data, next = None):
    self.data = data
    self.next = next
 
class LinkedList:
  def __init__(self, node = None):
    self.head  = node
    self.size  = 0    
    
  def del_first(self):    
    if self.size  == 0:
      print('The list is empty')
    else: 
      self.head = self.head.next 
      self.size -= 1
  
  def del_last(self):
    if self.size == 0: 
        print('The list is empty')
    else: 
        cur, prev   = self.head, self.head 
        while cur.next: 
            prev = cur
            cur = cur.next 
        prev.next = None 
        self.size -= 1
      
          
          
      
  
  def add_pos(self, pos, data):
    if pos < 0 and pos > self.size:
      return None 
    else: 
      if pos == self.size: 
        self.add_first(data)
      else: 
        new_node  = Node(data)
        count  = 1
        cur = self.head
        while count < pos - 1:
          count += 1
          cur = cur + 1

        new_node.next = cur.next 
        cur.next = new_node 
        self.size += 1
        
      
    
  def len(self):
    cur = self.head
    count  = 0    
    while cur: 
      cur = cur.next
      count += 1
    return count

  def add_first(self, data):
    new_node = Node(data)
    new_node.next = self.head
    self.head  = new_node 
    self.size += 1
    # self.display()

  def add_last(self, data):
    new_node = Node(data)
    # get the last node 
    temp = Node(None)
    cur = self.head 
    while cur: 
      temp = cur
      cur = cur.next 
    temp.next = new_node
    # self.display()
    
    

  def display(self):
    cur = self.head
    while cur: 
      print(cur.data, end = ' ')
      cur = cur.next 
    print('\n')

  
 ============================
 From main: 
 
from single_linked_list import LinkedList

l = LinkedList()
l.add_first(10)
l.add_pos(2, 500)
l.add_last(100)
l.del_first()
l.del_last()
l.display()

 


## Complexity Analysis
 