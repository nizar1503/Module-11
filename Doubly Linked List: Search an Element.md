# 📝 Doubly Linked List: Search an Element

This Python program demonstrates the implementation of a **Doubly Linked List** where you can insert elements at both the beginning and the end of the list. Additionally, it allows you to search for a specific element in the list.

---

## 🎯 Aim

To write a Python program that:
- Implements a **Doubly Linked List** with functions to insert elements at the beginning and the end of the list.
- Implements a search function to check if a given element exists in the list.

---

## 🧠 Algorithm

1. **Step 1:** Define a class `Nodeq` with:
   - `data` to store the node's value.
   - `next` to store the reference to the next node.
   - `prev` to store the reference to the previous node.

2. **Step 2:** Define a class `DoublyLinkedList` with:
   - `head` to point to the first node.

3. **Step 3:** In the `DoublyLinkedList` class, define methods:
   - `insert_beginning(data)` to insert a node at the beginning.
   - `insert_end(data)` to insert a node at the end.
   - `search(data)` to search for an element in the list.

4. **Step 4:** Create an instance of `DoublyLinkedList`.
   - Insert elements at the beginning and end.
   - Search for specific elements.

---

## 💻 Program
```
class Nodeq:
    def __init__(self, data):
        self.data = data
        self.next = None  # reference to next node
        self.prev = None  # reference to previous node

class DoublyLinkedList:
    def __init__(self):
        self.head = None
    def insert_beginning(self, data):
        new_node = Nodeq(data)
        if self.head is None:
            self.head = new_node
        else:
            new_node.next = self.head
            self.head.prev = new_node
            self.head = new_node

  
    def insert_end(self, data):
        new_node = Nodeq(data)
        if self.head is None:
            self.head = new_node
            return
        n = self.head
        while n.next:
            n = n.next
        n.next = new_node
        new_node.prev = n

    def search(self, data):
        current = self.head
        while current:
            if current.data == data:
                return True
            current = current.next
        return False

    def traverse_list(self):
        elems = []
        current = self.head
        while current:
            elems.append(current.data)
            current = current.next
        print("Doubly Linked List:", elems)

dll = DoublyLinkedList()
dll.insert_beginning(30)
dll.insert_beginning(20)
dll.insert_beginning(10)
dll.insert_end(40)
dll.insert_end(50)
dll.traverse_list()


print("Search 20:", "Found" if dll.search(20) else "Not Found")
print("Search 60:", "Found" if dll.search(60) else "Not Found")
```
## Sample Output
```
Doubly Linked List: [10, 20, 30, 40, 50]
Search 20: Found
Search 60: Not Found
```
## Result
Hence  Searched an Element in Doubly Linked List.
