# List

List 是一个接口，它继承于Collection的接口。它代表着有序的队列。<br>
AbstractList 是一个抽象类，它继承于AbstractCollection。AbstractList实现List接口中除size()、get(int location)之外的函数。<br>
AbstractSequentialList 是一个抽象类，它继承于AbstractList。AbstractSequentialList 实现了“链表中，根据index索引值操作链表的全部函数”。<br>

ArrayList, LinkedList, Vector, Stack是List的4个实现类。<br>
__ArrayList__ 是一个数组队列，相当于动态数组。它由数组实现，随机访问效率高，随机插入、随机删除效率低。<br>
[LinkedList](https://github.com/Zingg7/LeetCode/blob/Knowledge-Points/-%20LinkedList.md) 是一个双向链表。它也可以被当作堆栈、队列或双端队列进行操作。LinkedList随机访问效率低，但随机插入、随机删除效率低。<br>
__Vector__ 是矢量队列，和ArrayList一样，它也是一个动态数组，由数组实现。但是ArrayList是非线程安全的，而Vector是线程安全的。<br>
[Stack](https://github.com/Zingg7/LeetCode/blob/Knowledge-Points/-%20Stack.md) 是栈，它继承于Vector。它的特性是：先进后出(FILO, First In Last Out)。<br>

<br>

## 层次图

Collection<br>
　　｜——Set：无序集合，元素不可重复<br>
　　｜　　｜——EnumSet<br>
　　｜　　｜——SortedSet——TreeSet<br>
　　｜　　｜——HashSet——LinkedHashSet<br>
　　｜——List：有序集合，元素可以重复<br>
　　｜　　｜——[LinkedList](https://github.com/Zingg7/LeetCode/blob/Knowledge-Points/-%20LinkedList.md)<br>
　　｜　　｜——ArrayList<br>
　　｜　　｜——Vector<br>
　　｜　　｜——[Stack](https://github.com/Zingg7/LeetCode/blob/Knowledge-Points/-%20Stack.md) <br>
　　｜——Queue：队列<br>
　　　　　｜——Deque<br>
　　　　　｜——PriorityQueue<br>
　

## Methods

| Return | Method | Description | 
| :-: | :-: | :-: | 
| void |	add(String item) |          向滚动列表的末尾添加指定的项|
| void| 	add(String item, int index)|          向滚动列表中索引指示的位置添加指定的项|
| String	|getItem(int index) |          获取与指定索引关联的项|
| int|	getItemCount() |          获取列表中的项数|
| String[]	|getItems() |          获取列表中的项|
| void	|remove(int position) |          从此滚动列表中移除指定位置处的项|
| void	|remove(String item) |          从列表中移除项的第一次出现|
| void	|removeAll() |          从此列表中移除所有项
| void	|replaceItem(String newValue, int index) |          使用新字符串替换滚动列表中指定索引处的项|

<br>


## Refernce:

[List总结(LinkedList, ArrayList等使用场景和性能分析)](http://www.cnblogs.com/skywang12345/p/3308900.html)
