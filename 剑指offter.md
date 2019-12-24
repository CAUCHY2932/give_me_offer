## 剑指offter

该部分题目来源于牛客网的剑指offer，共66道题目，虽然可能有增减，但是大部分题目是不过时的。

### 二维数组中的查找



 时间限制：C/C++ 1秒，其他语言2秒 空间限制：C/C++ 32M，其他语言64M 热度指数：1511377 

 本题知识点： 查找 数组

#### 题目描述

在一个二维数组中（每个一维数组的长度相同），每一行都按照从左到右递增的顺序排序，每一列都按照从上到下递增的顺序排序。请完成一个函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。



```python
# -*- coding:utf-8 -*-
class Solution:
    # array 二维列表
    def Find(self, target, array):
        # write code here
        return True if True in [True if target in r else False for r in array] else False

```

### 替换空格



 时间限制：C/C++ 1秒，其他语言2秒 空间限制：C/C++ 32M，其他语言64M 热度指数：1286200 

 本题知识点： [字符串](https://www.nowcoder.com/questionCenter?questionTypes=000100&mutiTagIds=579) 

  算法知识视频讲解 

#### 题目描述

请实现一个函数，将一个字符串中的每个空格替换成“%20”。例如，当字符串为We Are Happy.则经过替换之后的字符串为We%20Are%20Happy。



```python
# -*- coding:utf-8 -*-
import re
class Solution:
    # s 源字符串
    def replaceSpace(self, s):
        # write code here
        return re.sub('\s', '%20', s)
```

### 从尾到头打印链表

 时间限制：C/C++ 1秒，其他语言2秒 空间限制：C/C++ 32M，其他语言64M 热度指数：1153518 

 本题知识点： 链表

  算法知识视频讲解 

#### 题目描述

输入一个链表，按链表从尾到头的顺序返回一个ArrayList。

```python
# -*- coding:utf-8 -*-
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    # 返回从尾部到头部的列表值序列，例如[1,2,3]
    def printListFromTailToHead(self, listNode):
        # write code here
        if listNode is None:
            return []
        tmp_list = []
        p = listNode
        while p != None:
            tmp_list.append(p.val)
            p = p.next
        return tmp_list[::-1]
```

### 重建二叉树

 时间限制：C/C++ 1秒，其他语言2秒 空间限制：C/C++ 32M，其他语言64M 热度指数：855102 

 本题知识点： [树](https://www.nowcoder.com/questionCenter?questionTypes=000100&mutiTagIds=583) 

  算法知识视频讲解 

#### 题目描述

输入某二叉树的前序遍历和中序遍历的结果，请重建出该二叉树。假设输入的前序遍历和中序遍历的结果中都不含重复的数字。例如输入前序遍历序列{1,2,4,7,3,5,6,8}和中序遍历序列{4,7,2,1,5,3,8,6}，则重建二叉树并返回。

```python
# -*- coding:utf-8 -*-
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None
class Solution:
    # 返回构造的TreeNode根节点
    def reConstructBinaryTree(self, pre, tin):
        # write code here
        pre_len = len(pre)
        if pre_len == 0:
            return None
        elif pre_len == 1:
            return TreeNode(pre[0])
        else:
            pre_first = pre[0]
            root = TreeNode(pre_first)
            root.left = self.reConstructBinaryTree(pre[1:tin.index(pre_first)+1],tin[:tin.index(pre_first)])
            root.right = self.reConstructBinaryTree(pre[tin.index(pre_first)+1:],tin[tin.index(pre_first)+1:])
            return root

```

### 用两个栈实现队列

