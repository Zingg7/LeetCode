# Trie

Trie树，又称字典树，单词查找树或者前缀树，是一种用于快速检索的多叉树结构。
如英文字母的字典树是一个26叉树，数字的字典树是一个10叉树。

Trie树可以利用字符串的公共前缀来节约存储空间。

Trie树的**基本性质**可以归纳为：<br>
（1）根节点不包含字符，除根节点以外每个节点只包含一个字符。<br>
（2）从根节点到某一个节点，路径上经过的字符连接起来，为该节点对应的字符串。<br>
（3）每个节点的所有子节点包含的字符串不相同。

<br>

## Trie树的基本实现

字母树的插入（Insert）、删除（ Delete）和查找（Find）都非常简单，用一个一重循环即可，即第i 次循环找到前i 个字母所对应的子树，然后进行相应的操作。实现这棵字母树，我们用最常见的数组保存（静态开辟内存）即可，当然也可以开动态的指针类型（动态开辟内存）<br>

至于结点对儿子的指向，一般有三种方法：<br>
1、对每个结点开一个字母集大小的数组，对应的下标是儿子所表示的字母，内容则是这个儿子对应在大数组上的位置，即标号；<br>
2、对每个结点挂一个链表，按一定顺序记录每个儿子是谁；<br>
3、使用左儿子右兄弟表示法记录这棵树。<br>
三种方法，各有特点。
第一种易实现，但实际的空间要求较大；第二种，较易实现，空间要求相对较小，但比较费时；第三种，空间要求最小，但相对费时且不易写。

[LC 202. Implement Trie (Prefix Tree)](https://github.com/Zingg7/LeetCode/blob/master/208.%20Implement%20Trie%20(Prefix%20Tree).md)对Trie树的基本功能进行了实现。

```java
class TrieNode {
    public boolean isWord;
    public TrieNode[] children = new TrieNode[26];
    public TrieNode() {}
}

public class Trie {

    private TrieNode root;
    
    /** Initialize your data structure here. */
    public Trie() {
       root = new TrieNode(); 
    }
    
    /** Inserts a word into the trie. */
    public void insert(String word) {
        TrieNode ws = root;
        for (int i = 0; i < word.length(); i++) {
            char c = word.charAt(i);
            if (ws.children[c - 'a'] == null) {
                ws.children[c - 'a'] = new TrieNode();
            } 
            ws = ws.children[c - 'a'];
        }
        ws.isWord = true;
    }
    
    /** Returns if the word is in the trie. */
    public boolean search(String word) {
        TrieNode ws = root;
        for (int i = 0; i < word.length(); i ++) {
            char c = word.charAt(i);
            if (ws.children[c - 'a'] == null) 
                return false;
            ws = ws.children[c - 'a'];
        }
        return ws.isWord;
    }
    
    /** Returns if there is any word in the trie that starts with the given prefix. */
    public boolean startsWith(String prefix) {
        TrieNode ws = root;
        for (int i = 0; i < prefix.length(); i ++) {
            char c = prefix.charAt(i);
            if (ws.children[c - 'a'] == null) 
                return false;
            ws = ws.children[c - 'a'];
        }
        return true;
    }
}

/**
 * Your Trie object will be instantiated and called as such:
 * Trie obj = new Trie();
 * obj.insert(word);
 * boolean param_2 = obj.search(word);
 * boolean param_3 = obj.startsWith(prefix);
 */
 ```

<br>

## Trie树的应用

Trie是一种非常简单高效的数据结构，但有大量的应用实例。

1. **字符串检索**

事先将已知的一些字符串（字典）的有关信息保存到trie树里，查找另外一些未知字符串是否出现过或者出现频率。

举例：<br>
@  给出N 个单词组成的熟词表，以及一篇全用小写英文书写的文章，请你按最早出现的顺序写出所有不在熟词表中的生词。<br>
@  给出一个词典，其中的单词为不良单词。单词均为小写字母。再给出一段文本，文本的每一行也由小写字母构成。判断文本中是否含有任何不良单词。例如，若rob是不良单词，那么文本problem含有不良单词。

2. **字符串最长公共前缀**

Trie树利用多个字符串的公共前缀来节省存储空间，反之，当我们把大量字符串存储到一棵trie树上时，我们可以快速得到某些字符串的公共前缀。

举例：<br>
@ 给出N 个小写英文字母串，以及Q 个询问，即询问某两个串的最长公共前缀的长度是多少？

解决方案：首先对所有的串建立其对应的字母树。此时发现，对于两个串的最长公共前缀的长度即它们所在结点的公共祖先个数，于是，问题就转化为了离线（Offline）的最近公共祖先（Least Common Ancestor，简称LCA）问题。

而最近公共祖先问题同样是一个经典问题，可以用下面几种方法：<br>
（1） 利用并查集（Disjoint Set），可以采用采用经典的Tarjan 算法；<br>
（2） 求出字母树的欧拉序列（Euler Sequence ）后，就可以转为经典的最小值查询（Range Minimum Query，简称RMQ）问题了；


3. **排序**

Trie树是一棵多叉树，只要先序遍历整棵树，输出相应的字符串便是按字典序排序的结果。

举例：<br>
@ 给你N 个互不相同的仅由一个单词构成的英文名，让你将它们按字典序从小到大排序输出。

4. **作为其他数据结构和算法的辅助结构**

如后缀树，AC自动机等
<br>
<br>

##  Trie树复杂度分析

（1） 插入、查找的时间复杂度均为O(N)，其中N为字符串长度。<br>
（2） 空间复杂度是26^n级别的，非常庞大（可采用双数组实现改善）。

<br>

## Refernce:

[数据结构之Trie树](http://dongxicheng.org/structure/trietree/)<br>
