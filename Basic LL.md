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
      
      
def get_count(self): 
    temp = self.head
    count  = 0
    while temp:
      count += 1
      temp = temp.next
    return count 

  def find_middle(self):
    temp  = self.head
    len_of_LL = self.get_count() // 2
    print(len_of_LL)
    print()
    while len_of_LL != 0: 
      len_of_LL -= 1
      temp = temp.next
    print(temp.data) 
if __name__ == '__main__': 

  llist = LinkedList()
  llist.head  = Node(10)
  second = Node(20)
  third  = Node(30)
  llist.head.next = second
  second.next = third
  llist.print_list()
  llist.find_middle()
      


# version 2


# init node 
class Node: 
  def __init__(self, data): 
    self.data  = data
    self.next  = None

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

       
       
# version 3: Doubly LinkedList


# init node 
class Node: 
  def __init__(self, data): 
    self.data  = data
    self.prev = None 
    self.next  = None
   

# linkedlist graph
class DoublyLinkedList: 
  def __init__(self): 
    self.head = None 
    self.start_node = None 
    self.last_node  = None  
    
  def append(self, data):
    if self.last_node is None: 
      self.head  = Node(data)
      self.last_node  = self.head 
    else: 
      new_node = Node(data)
      self.last_node.next = new_node
      new_node.prev = self.last_node
      new_node.next = None 
      self.last_node = new_node  # update after create next 

  def print_list(self, Type):
    
    if Type == 'LTR':
      curr = self.head 
      while curr: 
        print(curr.data, end = ' ')
        curr = curr.next 
      print()
    else: 
      curr = self.last_node 
      while curr: 
        print(curr.data, end = ' ')
        curr = curr.prev 
      print() 

    

if __name__ == '__main__': 
  link_list = DoublyLinkedList()
  link_list.append(10)
  link_list.append(20)
  link_list.append(50)
  link_list.append(100)
  
  link_list.print_list('LTR')

       
