#### TECHNICAL INTERVIEW PROBLEMS IN PYTHON: LINKED LISTS

# [Detect Cycle in a Linked List](https://www.codecademy.com/courses/technical-interview-practice-python/lessons/tip-python-linked-lists/exercises/tip-python-ll-cycle)

As we saw with the merge point problem, more than one node can reference another node. 
These references can create a cycle in the linked list where the traversal will loop back on itself.
```python
#    -> b -> c
#  /      \   \
# a         d <-

# 'd' node's next points to 'b' node
```
Write a function that detects whether a cycle exists in a linked list. 
A cycle exists if **traversing the linked list visits the same node more than once**.

A cycle does not **mean** repeated values. 
Avoid this pitfall in your implementation by comparing the `Node` instances themselves, not their values!
```python
a = Node('a')
other_a = Node('a')
 
a.val == other_a.val 
# True
a == other_a
# False
```

## To recap:
* write a function: `has_cycle()`.
* `has_cycle()` takes an instance of `LinkedList` as the argument.
* return a Boolean which indicates whether a cycle exists.

<hr />
<details title="Click me to show...">
<summary>
 
## My solution

</summary>
<p>
     
```python
def has_cycle(linked_list):
    current_node = linked_list.head
    unique = []
  
    while current_node:
        node_id = id(current_node)
        if node_id in unique:
            return True
        # this is unique Node -> appen to the unique list:
        unique.append(node_id)
        # move to the next node:
        current_node = current_node.next

    return False
```

</p>
</details>
<hr />
<details title="Click me to show...">
<summary>
 
## CodeCademy solution

</summary>
<p>
     
```python
def has_cycle(linked_list):
    slow, fast = linked_list.head, linked_list.head
    while slow and fast:
        slow = slow.next
        fast = fast.next
        if fast:
            fast = fast.next
        else:
            return False
        if fast == slow:
            return True
    return False
```

</p>
</details>
