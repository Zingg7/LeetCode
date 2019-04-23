# ListNode

最初在LC.2中出现。

在Java中，尽管没有指针的存在，仍可以通过定义实现链表的效果。

<br>

**一般都会直接在注释中给出:** <br>
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
