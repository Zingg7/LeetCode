# Set


此类实现 Set 接口，由哈希表（实际上是一个 HashMap 实例）支持。<br>
它不保证 set 的迭代顺序；特别是它不保证该顺序恒久不变。<br>
允许使用 null 元素。

<br>

## 常见方法
| Return | Method | Description | 
| :-: | :-: | :-: | 
| boolean | add() | 如果此 set 中尚未包含指定元素，则添加指定元素 |
| void | clear() | 从此 set 中移除所有元素 |
| boolean | contains() | 如果此 set 包含指定元素，则返回 true |
| boolean | isEmpty() | 如果此 set 不包含任何元素，则返回 true |
| Iterator<E> | iterator() | 返回对此 set 中元素进行迭代的迭代器 |
| boolean | remove() | 如果指定元素存在于此 set 中，则将其移除 |
| int |	size() | 返回此 set 中的元素的数量（set 的容量） |
  
<br>

## HashSet集合的add()方法的源码
* 为什么存储字符串的时候，字符串内容相同的只存储了一个？ <br>

通过查看add方法的源码，我们知道这个方法底层依赖 两个方法：hashCode()和equals()。<br>

步骤：<br>
首先比较哈希值<br>
&emsp;如果相同，继续走，比较地址值或者走equals()<br>
&emsp;如果不同,就直接添加到集合中<br>
按照方法的步骤来说：<br>
&emsp;先看hashCode()值是否相同<br>
&emsp;相同:继续走equals()方法<br>
&emsp;&emsp;返回true： 说明元素重复，就不添加<br>
&emsp;&emsp;返回false：说明元素不重复，就添加到集合<br>
&emsp;不同：就直接把元素添加到集合<br>
如果类没有重写这两个方法，默认使用的Object()。一般来说不会相同。<br>
而String类重写了hashCode()和equals()方法，所以，它就可以把内容相同的字符串去掉。只留下一个。<br>

<br>

## Reference
[Java API —— Set接口 & HashSet类 & LinkedHashSet类](https://www.cnblogs.com/yangyquin/p/5055131.html)
