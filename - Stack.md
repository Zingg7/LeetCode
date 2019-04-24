# Stack

Stack 类表示 **后进先出（LIFO）** 的对象堆栈。它通过五个操作对类 Vector 进行了扩展 ，允许将向量视为堆栈。<br>

首次创建堆栈时，它不包含项。

Deque 接口及其实现提供了 LIFO 堆栈操作的更完整和更一致的 set，应该优先使用此 set，而非此类。例如：<br>
&emsp;&emsp;&emsp; Deque<Integer> stack = new ArrayDeque<Integer>();
<br>
<br>


## Methods

| Return | Method | Description | 
| :-: | :-: | :-: | 
| boolean	| empty() | 测试堆栈是否为空 |
| E |	peek() | 查看堆栈顶部的对象，但不从堆栈中移除它 |
| E | pop() | 移除堆栈顶部的对象，并作为此函数的值返回该对象 |
| E |	push() | 把项压入堆栈顶部 |
| int | search() | 返回对象在堆栈中的位置，以 1 为基数 |

<br>

从类 java.util.Vector 继承的方法：

add, add, addAll, addAll, addElement, capacity, clear, clone, contains, containsAll, copyInto, elementAt, elements, ensureCapacity, equals, firstElement, get, hashCode, indexOf, indexOf, insertElementAt, isEmpty, lastElement, lastIndexOf, lastIndexOf, remove, remove, removeAll, removeAllElements, removeElement, removeElementAt, removeRange, retainAll, set, setElementAt, setSize, size, subList, toArray, toArray, toString, trimToSize

<br>

## Relate Questions:

| # | Title | Solution | Difficulty | Date |
|:-:|---|:-:|:-:|:-:|
|19|[Remove Nth Node From End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)|[Java](https://github.com/Zingg7/LeetCode/blob/master/19.%20Remove%20Nth%20Node%20From%20End%20of%20List.md)|Medium|2019.04.24|
