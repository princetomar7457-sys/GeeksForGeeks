## 01. Merge Two Sorted Linked Lists

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/merge-two-sorted-linked-lists/1)

### Problem Description

**Task:** Given the head of two sorted linked lists consisting of nodes respectively. Merge both lists and return the head of the sorted merged list.Examples:Input: Output: 2 - > 3 - > 5 - > 10 - > 15 - > 20 - > 40

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n + m)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-11-11 19:12:34
- **Status:** Correct
- **Marks:** 4

```java
/*  Structure of Linked List Node
class Node
{
    int data;
    Node next;
    Node(int d) {
        data = d;
        next = null;
    }
} */

class Solution {
    Node sortedMerge(Node head1, Node head2) {
        // code here
        Node i=head1;
        Node j=head2;
        Node dummy=new Node(-1);
        Node k=dummy;
        while(i!=null&&j!=null){
            if(i.data<j.data){
                k.next=i;
                i=i.next;
            }
            else{
                k.next=j;
                j=j.next;
            }
            k=k.next;
        }
        if(i==null)k.next=j;
        else k.next=i;
        return dummy.next;
    }
}
```

*Generated on: 11/11/2026, 7:13:15 PM*