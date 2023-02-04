# Basic LinkedList

```py
# Version 1
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

      


# version 2


# init node 
class Node: 
  def __init__(self, data): 
    self.data  = data
    self.next  = None
    self.last_node  = None 

# linkedlist graph
class LinkedList: 
  def __init__(self): 
    self.head = None 
    self.last_node  = None 

  def print_list(self):
    curr = self.head 
    while curr: 
      print(curr.data, end = ' ')
      curr = curr.next 
    print()
    
  def append(self, data):
    if self.last_node is None: 
      self.head  = Node(data)
      self.last_node  = self.head 
    else: 
      self.last_node.next = Node(data)
      self.last_node = self.last_node.next  # update after create next 
      

if __name__ == '__main__': 
  link_list = LinkedList()
  link_list.append(10)
  link_list.append(20)
  link_list.append(50)
  link_list.append(100)
  
  link_list.print_list()

      


              


## Complexity Analysis
 

              


## Complexity Analysis
 
