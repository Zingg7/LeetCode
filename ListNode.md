# ListNode

在Java中，尽管没有指针的存在，仍可以通过定义实现链表的效果。<br>
<br>


## 一般都会直接在注释中给出:

```JAVA
Definition for singly-linked list.
public class ListNode {
    int val;                        //value
    ListNode next;                  //point to next ListNode
    ListNode(int x) { val = x; }    //initialize
}
```

<br>
节点存储了两个变量：value和next。<br>
value 是这个节点的值，next 是指向下一节点的指针，当 next 为空指针时，这个节点是链表的最后一个节点。
<br>
<br>


## Related Questions:

| # | Title | Solution | Difficulty | Date |
|:-:|---|:-:|:-:|:-:|
|2|[Add Two Numbers](https://leetcode.com/problems/add-two-numbers/)|[Java](https://github.com/Zingg7/LeetCode/blob/master/2.%20Add%20Two%20Numbers.md)|Medium|2019.04.22|
|19|[Remove Nth Node From End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)|[Java](https://github.com/Zingg7/LeetCode/blob/master/19.%20Remove%20Nth%20Node%20From%20End%20of%20List.md)|Medium|2019.04.24|

[23. Merge k Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/)<br>
[24. Swap Nodes in Pairs](https://leetcode.com/problems/swap-nodes-in-pairs/)<br>
[25. Reverse Nodes in k-Group](https://leetcode.com/problems/reverse-nodes-in-k-group/)<br>
[61. Rotate List](https://leetcode.com/problems/rotate-list/)<br>
[82. Remove Duplicates from Sorted List II](https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/)<br>
[83. Remove Duplicates from Sorted List](https://leetcode.com/problems/remove-duplicates-from-sorted-list/)<br>
[86. Partition List](https://leetcode.com/problems/partition-list/)<br>
[92. Reverse Linked List II](https://leetcode.com/problems/reverse-linked-list-ii/)<br>
