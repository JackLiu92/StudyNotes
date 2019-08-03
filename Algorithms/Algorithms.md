### 数据结构与算法学习笔记
#### Leetcode

[**20 Valid Parentheses**](#20)

[**83 Remove Duplicates from Sorted List**](#83)

[**141 Linked List Cycle**](#141)

[**203 Remove Linked List Elements**](#203)

[**206 Reverse Linked List**](#206)

[**237 Delete Node in a Linked List**](#237)

[**509 Fibonacci Number**](#509)

[**876 Middle of the Linked List**](#876)


##### <a name="20"></a>20 Valid Parentheses

```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        if (head == null || head.next == null) return head;
        
        head.next = deleteDuplicates(head.next);
        return (head.val == head.next.val ? head.next : head);
    }
}
```

##### <a name="83"></a>83 Remove Duplicates from Sorted List

```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        if (head == null || head.next == null) return head;
        
        head.next = deleteDuplicates(head.next);
        return (head.val == head.next.val ? head.next : head);
    }
}
```

##### <a name="141"></a>141 Linked List Cycle

```
/**
 * Definition for singly-linked list.
 * class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */

class Solution {
    public void deleteNode(ListNode node) {
        node.val = node.next.val;
        node.next = node.next.next;
    }
}
```

##### <a name="203"></a>203 Remove Linked List Elements

```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */

class Solution {
    public ListNode removeElements(ListNode head, int val) {
        if (head == null) return null;
       
        head.next = removeElements(head.next, val);
        
        return head.val == val ? head.next : head;
        
    }
}
```

##### <a name="206"></a>206 Reverse Linked List

```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */

class Solution {
    public ListNode reverseList(ListNode head) {
        if (head == null || head.next == null) return head;
        ListNode headNext = null;
        while (head != null) {
            ListNode tmp = head.next;
            head.next = headNext;
            headNext = head;
            head = tmp;
        }
        return headNext;
    }
}
```

##### <a name="237"></a>237 Delete Node in a Linked List

```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */

class Solution {
    public void deleteNode(ListNode node) {
        node.val = node.next.val;
        node.next = node.next.next;
    }
}
```

##### <a name="509"></a>509 Fibonacci Number

```
class Solution {
    public int fib(int N) {
        if (N == 0) return 0;
        int first = 0;
        int second = 1;
        while (N-- > 1) {
            second += first;
            first = second - first;
        }
        return second;
    }
}
```

##### <a name="876"></a>876 Middle of the Linked List

```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode middleNode(ListNode head) {
        ListNode fast = head, slow = head;
        while (fast != null && fast.next != null) {
            fast = fast.next.next;
            slow = slow.next;
        }
        return slow;
    }
}
```