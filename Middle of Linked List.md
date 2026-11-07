## 01. Middle of Linked List

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/finding-middle-element-in-a-linked-list/1)

### Problem Description

**Task:** Given a linked list, You have to return the value of the middle node of the linked list. If the number of nodes is odd, return the middle node value.If the number of nodes is even, there are two middle nodes, so return the second middle node value.Examples:Input:

#### Examples

##### Example 1

- **Output:**
```text
3Explanation: The given linked list is 1- > 2- > 3- > 4- > 5 and its middle is 3. Input: Output: 7 Explanation: The given linked list is 2- > 4- > 6- > 7- > 5- > 1 so, there are two middle node 6 and 7, return the second middle node as 7.
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (3)

#### Solution 1 (Java)

- **Submitted:** 2026-11-07 09:10:51
- **Status:** Correct
- **Marks:** 0

```java
/* Linked List Node Structure
class Node {
    int data;
    Node next;

    Node(int x) {
        data = x;
        next = null;
    }
} */

class Solution {
    int getMiddle(Node head) {
        // code here
        // int length=0;
        // Node temp=head;
        // while(temp!=null){
        //     temp=temp.next;
        //     length++;
        // }
        // temp=head;
        // for(int i=1;i<=length/2;i++){
        //     temp=temp.next;
        // }
        // return temp.data;
        Node slow=head;
        Node fast=head;
        while(fast.next!=null){
            slow=slow.next;
            if(fast.next.next==null){
                return slow.data;
            }
            fast=fast.next.next;
        }
        return slow.data;
    }
}
```

#### Solution 2 (Java)

- **Submitted:** 2026-11-03 19:44:49
- **Status:** Correct
- **Marks:** 0

```java
/* Linked List Node Structure
class Node {
    int data;
    Node next;

    Node(int x) {
        data = x;
        next = null;
    }
} */

class Solution {
    int getMiddle(Node head) {
        // code here
        // int length=0;
        // Node temp=head;
        // while(temp!=null){
        //     temp=temp.next;
        //     length++;
        // }
        // temp=head;
        // for(int i=1;i<=length/2;i++){
        //     temp=temp.next;
        // }
        // return temp.data;
        Node slow=head;
        Node fast=head;
        while(fast.next!=null){
            slow=slow.next;
            if(fast.next.next==null){
                return slow.data;
            }
            fast=fast.next.next;
        }
        return slow.data;
    }
}
```

#### Solution 3 (Java)

- **Submitted:** 2026-11-03 08:57:52
- **Status:** Correct
- **Marks:** 2

```java
/* Linked List Node Structure
class Node {
    int data;
    Node next;

    Node(int x) {
        data = x;
        next = null;
    }
} */

class Solution {
    int getMiddle(Node head) {
        // code here
        int length=0;
        Node temp=head;
        while(temp!=null){
            temp=temp.next;
            length++;
        }
        temp=head;
        for(int i=1;i<=length/2;i++){
            temp=temp.next;
        }
        return temp.data;
    }
}
```

*Generated on: 11/7/2026, 9:11:02 AM*