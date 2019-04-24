# LinkedList

LinkedList存储元素的数据结构是 **双向链表** 结构，由存储元素的结点连接而成，每一个节点都包含前一个节点的引用，后一个节点的引用和节点存储的值。当一个新节点插入时，只需要修改其中保持先后关系的节点的引用即可。


LinkedList 是一个继承于AbstractSequentialList的双向链表。它也可以被当作堆栈、队列或双端队列进行操作。<bR>
LinkedList 实现 List 接口，能对它进行队列操作。<br>
LinkedList 实现 Deque 接口，即能将LinkedList当作双端队列使用。<BR>
LinkedList 实现了Cloneable接口，即覆盖了函数clone()，能克隆。<br>
LinkedList 实现java.io.Serializable接口，这意味着LinkedList支持序列化，能通过序列化去传输。<br>
LinkedList 是非同步的。<br>


所有已实现的接口：<br>
Serializable, Cloneable, Iterable<E>, Collection<E>, Deque<E>, List<E>, Queue<E>

<br>

## Methods

| Return | Method | Description | 
| :-: | :-: | :-: | 
| boolean	|add() |          将指定元素添加到此列表的结尾|
| void |	add(int, E)|          在此列表中指定的位置插入指定的元素|
| void |	addFirst() |          将指定元素插入此列表的开头|
| void |	addLast() |          将指定元素添加到此列表的结尾|
| void |	clear() |          从此列表中移除所有元素|
| boolean|	contains()|          如果此列表包含指定元素，则返回 true|
| E | element() |           获取但不移除此列表的头（第一个元素）|
| E | get() |          返回此列表中指定位置处的元素|
| int| indexOf() |          返回此列表中首次出现的指定元素的索引，不包含该元素则返回 -1|
| boolean	| offer() |          将指定元素添加到此列表的末尾（最后一个元素）|
| E	| peek() |          获取但不移除此列表的头（第一个元素）|
| E	| poll() |          获取并移除此列表的头（第一个元素）|
| E	| pop() |          从此列表所表示的堆栈处弹出一个元素|
| void | push() |          将元素推入此列表所表示的堆栈|
| E	| remove() |          获取并移除此列表的头（第一个元素）|
| E	| remove() |          移除此列表中指定位置处的元素|
| boolean| remove() |          从此列表中移除首次出现的指定元素（如果存在）|
| E	| removeFirst() |          移除并返回此列表的第一个元素|
| E	| set(int, E) |          将此列表中指定位置的元素替换为指定的元素|
| int	| size() |          返回此列表的元素数|
| Object[]	| toArray() |          返回以适当顺序（从第一个元素到最后一个元素）包含此列表中所有元素的数组|

<br>

## Relate Questions:

| # | Title | Solution | Difficulty | Date |
|:-:|---|:-:|:-:|:-:|
[PUT HERE]

<br>

## Refernce:

[LinkedList详细介绍(源码解析)和使用示例](https://www.cnblogs.com/skywang12345/p/3308807.html)
