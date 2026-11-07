## 01. Remove Duplicates in Sorted Linked List

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/remove-duplicate-element-from-sorted-linked-list/1)

### Problem Description

**Task:** Given the head of a sorted singly linked list, remove all duplicate nodes so that each element appears only once. The resulting linked list should remain sorted.Note: Try to solve the problem without using extra space.Examples:Input: Head: 2 - > 2 - > 4 - > 5

#### Examples

##### Example 1

- **Output:**
```text
2 - > 4 - > 5Explanation: In the given linked list 2 - > 2 - > 4 - > 5, only 2 occurs more than 1 time. So we need to remove it once.
```

##### Example 2

- **Input:**
```text
Head: 2 - > 2 - > 2 - > 2 - > 2
```
- **Output:**
```text
2Explanation: In the given linked list 2 - > 2 - > 2 - > 2, 2 is the only element and is repeated 5 times. So we need to remove any four 2.
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-11-07 17:11:42
- **Status:** Correct
- **Marks:** 2

```java
/* Structure of linked list Node
class Node {
    int data;
    Node next;

    Node(int d) {
      data = d;
      next = null;
    }
}
*/
class Solution {
    Node removeDuplicates(Node head) {
        // code here
        Node temp=head;
        Node slow=head;
        Node fast=head.next;
        if(head==null||head.next==null){
            return head;
        }
        while(fast!=null){
            if(slow.data==fast.data){
                fast=fast.next;
            }
            else{
                slow.next=fast;
                slow=fast;
                fast=fast.next;
            }
        }
        slow.next=null;
        return head;
    }
}
```

*Generated on: 11/7/2026, 5:13:21 PM*