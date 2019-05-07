# PriorityQueue

PriorityQueue是一个基于优先级的 **无界优先级** 队列。优先级队列的元素按照其自然顺序进行排序，或者根据构造队列时提供的 Comparator 进行排序，具体取决于所使用的构造方法。该队列不允许使用 null 元素也不允许插入不可比较的对象(没有实现Comparable接口的对象)。<br>

PriorityQueue保存队列元素的顺序并不是按加入队列的顺序，而是按队列元素的大小进行重新排序。因此当调用peek方法活着pull方法来取出队列中的元素时，并不是取出最先进入队列的元素，而是取出队列中最小的元素。从这个意义上看，PriorityQueue已经违反了队列的最基本原则：先进先出(FIFO)。

PriorityQueue队列的头指排序规则最小的那个元素。如果多个元素都是最小值则随机选一个。<br>
PriorityQueue是一个无界队列，但是初始的容量(实际是一个Object[])，随着不断向优先级队列添加元素，其容量会自动扩容，无需指定容量增加策略的细节。


<br>

## Methods

| Return | Method | Description | 
| :-: | :-: | :-: | 
|boolean|add(E e)|	添加元素|
|void|clear()|	清空|
|boolean|contains(Object o)|	检查是否包含当前参数元素|
|boolean|offer(E e)|	添加元素|
|E|peek()|	读取元素，（不删除）|
|E|poll()|	取出元素，（删除）|
|E|remove(Object o)|	删除指定元素|
|int|size()|	返回长度|
|Object[]|	toArray() |返回一个包含此队列所有元素的数组|


<br>

## Relate Questions:

| # | Title | Solution | Difficulty | Date |
|:-:|---|:-:|:-:|:-:|
[PUT HERE]



PriorityQueue优先级规则可以由我们根据具体需求而定制， 方式有2种：
1) 添加元素自身实现了Comparable接口，确保元素是可排序的对象
2) 如果添加元素没有实现Comparable接口，可以在创建PriorityQueue队列时直接指定比较器。

<br>

## Refernce:

[Java Queue系列之PriorityQueue](https://www.cnblogs.com/demingblog/p/6485193.html)<br>
[Java中的集合Queue、LinkedList、PriorityQueue](https://www.cnblogs.com/be-forward-to-help-others/p/6825738.html)
