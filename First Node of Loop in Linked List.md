## 01. First Node of Loop in Linked List

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/find-the-first-node-of-loop-in-linked-list--170645/1)

### Problem Description

**Task:** You are given the head of a singly linked list. If a loop is present in the linked list then return the first node of the loop else return -1.

> **Note:** Internally, pos(1 based index) is used to denote the position of the node that tail's next pointer is connected to. If pos = 0, it means the last node points to null, indicating there is no loop. Note that pos is not passed as a parameter.

#### Examples

##### Example 1

- **Input:**
```text
pos = 2,
```
- **Output:**
```text
3
```
- **Explanation:** We can see that there exists a loop in the given linked list and the first node of the loop is 3.

##### Example 2

- **Input:**
```text
pos = 0,
```
- **Output:**
```text
-1
```
- **Explanation:** No loop exists in the above linked list. So the output is -1.

#### Constraints

- **1.** `1 ≤ no. of nodes ≤ 10⁶¹ ≤ node- > data ≤ 10⁶`

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (2)

#### Solution 1 (Java)

- **Submitted:** 2026-11-07 09:23:17
- **Status:** Correct
- **Marks:** 0

```java
/*
class Node {
    int data;
    Node next;

    Node(int x)
    {
        data = x;
        next = null;
    }
};
*/

class Solution {
    public int cycleStart(Node head) {
        // code here
        if(head==null||head.next==null)return -1;
        Node slow=head;
        Node fast=head;
        Node temp=head;
        while(fast!=null&&fast.next!=null){
            slow=slow.next;
            fast=fast.next.next;
            if(slow==fast){
                break;
            }
        }
        if(fast==null||fast.next==null){
            return -1;
        }
        while(slow!=temp){
            slow=slow.next;
            temp=temp.next;
        }
        return slow.data;
    }
}
```

#### Solution 2 (Java)

- **Submitted:** 2026-11-07 09:22:16
- **Status:** Correct
- **Marks:** 4

```java
/*
class Node {
    int data;
    Node next;

    Node(int x)
    {
        data = x;
        next = null;
    }
};
*/

class Solution {
    public int cycleStart(Node head) {
        // code here
        if(head==null||head.next==null)return -1;
        Node slow=head;
        Node fast=head;
        Node temp=head;
        while(fast!=null&&fast.next!=null){
            slow=slow.next;
            fast=fast.next.next;
            if(slow==fast){
                break;
            }
        }
        if(fast==null||fast.next==null){
            return -1;
        }
        while(slow!=temp){
            slow=slow.next;
            temp=temp.next;
        }
        return slow.data;
    }
}
```

*Generated on: 11/7/2026, 9:23:30 AM*