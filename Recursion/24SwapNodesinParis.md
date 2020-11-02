24. Swap Nodes in Pairs

### 题目地址
- [Swap Nodes in Pairs](https://leetcode.com/problems/swap-nodes-in-pairs/)

### 1,初步思路

```
/***** Recursion Solution *****/
public ListNode swapPairs(ListNode head){
    // base case
    if (head == null || head.next == null) {
        return head;
    }

    // swap nodes
    ListNode dummy = head;
    ListNode nextSwap = head.next.next;
    ListNode result = head.next;
    head.next.next = head;

    ListNode nextHead = swapPairs(nextSwap);
    dummy.next = nextHead;

    return result;
}
```

### 2,正确解法

```
/***** Recursion *****/
public ListNode swapPairs(ListNode head) {
    // base case
    if (head == null || head.next == null) {
        return head;
    }

    ListNode result = head.next;
    result.next = head;

    // 此处,返回的为链表头部
    head.next = swapPairs(head.next.next);

    return result;
}


/***** Iterative *****/
public ListNode swapPairs2(ListNode head) {
    
}
```

**参考资料**
- [My accepted java code, use recursion](https://leetcode.com/problems/swap-nodes-in-pairs/discuss/11030/My-accepted-java-code.-used-recursion.)