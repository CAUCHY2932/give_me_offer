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

 时间限制：C/C++ 1秒，其他语言2秒 空间限制：C/C++ 32M，其他语言64M 热度指数：560050 

 本题知识点： [队列](https://www.nowcoder.com/questionCenter?questionTypes=000100&mutiTagIds=582) [栈](https://www.nowcoder.com/questionCenter?questionTypes=000100&mutiTagIds=581) 

  算法知识视频讲解 

#### 题目描述

用两个栈来实现一个队列，完成队列的Push和Pop操作。 队列中的元素为int类型。



```python
# -*- coding:utf-8 -*-
class Solution:
    def __init__(self):
        self.stack = []
    def push(self, node):
        # write code here
        self.stack.append(node)
    def pop(self):
        # return xx
        return self.stack.pop(0)

```





### 旋转数组的最小数字



 时间限制：C/C++ 3秒，其他语言6秒 空间限制：C/C++ 32M，其他语言64M 热度指数：784611 

 本题知识点： [查找](https://www.nowcoder.com/questionCenter?questionTypes=000100&mutiTagIds=589) 

  算法知识视频讲解 

#### 题目描述

把一个数组最开始的若干个元素搬到数组的末尾，我们称之为数组的旋转。
 	输入一个非递减排序的数组的一个旋转，输出旋转数组的最小元素。
 	例如数组{3,4,5,1,2}为{1,2,3,4,5}的一个旋转，该数组的最小值为1。
 	NOTE：给出的所有元素都大于0，若数组大小为0，请返回0。

```python
# -*- coding:utf-8 -*-
class Solution:
    def minNumberInRotateArray(self, rotateArray):
        # write code here
        len_of_array = len(rotateArray)
        if len_of_array == 0:
            return 0
        for i in range(len_of_array - 1):
            if rotateArray[i]> rotateArray[i+1]:
                return rotateArray[i+1]

```



### 斐波那契数列



 时间限制：C/C++ 1秒，其他语言2秒 空间限制：C/C++ 32M，其他语言64M 热度指数：714782 

 本题知识点： [递归](https://www.nowcoder.com/questionCenter?questionTypes=000100&mutiTagIds=591) 

  算法知识视频讲解 

#### 题目描述

大家都知道斐波那契数列，现在要求输入一个整数n，请你输出斐波那契数列的第n项（从0开始，第0项为0）。 

  n<=39 

```python
# -*- coding:utf-8 -*-
class Solution:
    def Fibonacci(self, n):
        # write code here
        if n == 0:
            return 0
        if n == 1 :
            return 1
        if n == 2:
            return 1
        if n > 39:
            return -1
        f1 = 1
        f2 = 1
        f3 = 2
        for i in range(n-3):
            f3 = f1 + f2
            f1 = f2
            f2 = f3
        return f3

```

### 跳台阶

#### 题目描述

 时间限制：C/C++ 1秒，其他语言2秒 空间限制：C/C++ 32M，其他语言64M 热度指数：541305 

 本题知识点： [递归](https://www.nowcoder.com/questionCenter?questionTypes=000100&mutiTagIds=591) 

一只青蛙一次可以跳上1级台阶，也可以跳上2级。求该青蛙跳上一个n级的台阶总共有多少种跳法（先后次序不同算不同的结果）。



别人的解法

```python
# -*- coding:utf-8 -*-
class Solution:
    def jumpFloor(self, number):
        # write code here
        
        flo = []
        for i in range(number):
            if i ==0:
                flo.append(1)
            elif i ==1:
                flo.append(2)
            else:
                flo.append(flo[i-1]+flo[i-2])
        return flo.pop()
```



自己的解法不对

```python
# -*- coding:utf-8 -*-
class Solution:
    def jumpFloor(self, number):
        # write code here
            
    	if number <= 0:
            return 0
        if number == 1 :
            return 1
        if number == 2:
            return 2
        return self.jumpFloor(number-1) + self.jumpFloor(number-2)
        
```

### 变态跳台阶

#### 题目描述

一只青蛙一次可以跳上1级台阶，也可以跳上2级……它也可以跳上n级。求该青蛙跳上一个n级的台阶总共有多少种跳法。



### 二进制中1的个数

#### 题目描述

 时间限制：C/C++ 1秒，其他语言2秒 空间限制：C/C++ 32M，其他语言64M 热度指数：537163 

 本题知识点： [进制转化](https://www.nowcoder.com/questionCenter?questionTypes=000100&mutiTagIds=1201) [补码反码原码](https://www.nowcoder.com/questionCenter?questionTypes=000100&mutiTagIds=1215) 

输入一个整数，输出该数二进制表示中1的个数。其中负数用补码表示。



### 数值的整数次方

 时间限制：C/C++ 1秒，其他语言2秒 空间限制：C/C++ 32M，其他语言64M 热度指数：553995 

 本题知识点： [数学](https://www.nowcoder.com/questionCenter?questionTypes=000100&mutiTagIds=1213) 

  算法知识视频讲解 

#### 题目描述

  给定一个double类型的浮点数base和int类型的整数exponent。求base的exponent次方。 

  


  保证base和exponent不同时为0 

```python
# -*- coding:utf-8 -*-
class Solution:
    def Power(self, base, exponent):
        # write code here
        if base<=0 and exponent <=0:
            return 0
        return base**exponent
    
```



### 调整数组顺序使奇数位于偶数前面



 时间限制：C/C++ 1秒，其他语言2秒 空间限制：C/C++ 32M，其他语言64M 热度指数：651345 

 本题知识点： [数组](https://www.nowcoder.com/questionCenter?questionTypes=000100&mutiTagIds=578) 

  算法知识视频讲解 

[  算法知识视频讲解 ](https://www.nowcoder.com/courses/semester/2018algorithm-higher) 

#### 题目描述

输入一个整数数组，实现一个函数来调整该数组中数字的顺序，使得所有的奇数位于数组的前半部分，所有的偶数位于数组的后半部分，并保证奇数和奇数，偶数和偶数之间的相对位置不变。

```python
# -*- coding:utf-8 -*-
class Solution:
    def reOrderArray(self, array):
        # write code here
        evens = []
        odds = []
        for i in array:
            if i%2 !=0:
                evens.append(i)
            else:
                odds.append(i)
        evens.extend(odds)
        return evens
        
```

### 链表中倒数第k个结点

 时间限制：C/C++ 1秒，其他语言2秒 空间限制：C/C++ 32M，其他语言64M 热度指数：914479 

 本题知识点： [链表](https://www.nowcoder.com/questionCenter?questionTypes=000100&mutiTagIds=580) 

输入一个链表，输出该链表中倒数第k个结点。





```python
# -*- coding:utf-8 -*-
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def FindKthToTail(self, head, k):
        # write code here
        p = head
        q = head
        if k ==0:
            return None

        for _ in range(k-1):
            if p == None or p.next == None:
                return None
            p = p.next

        while(p.next != None):
            p = p.next
            q = q.next
        return q

```

### 反转链表(暂时未写出来)

 时间限制：C/C++ 1秒，其他语言2秒 空间限制：C/C++ 32M，其他语言64M 热度指数：664527 

 本题知识点： [链表](https://www.nowcoder.com/questionCenter?questionTypes=000100&mutiTagIds=580) 

  算法知识视频讲解 

#### 题目描述

输入一个链表，反转链表后，输出新链表的表头。





```python
# -*- coding:utf-8 -*-
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None
class Solution:
    # 返回ListNode
    def ReverseList(self, pHead):
        # write code here
        p = pHead
        if p == None or p.next == None:
            return p
        
        q = ListNode(p.val)
        p = p.next
        
        while(p != None and p.next != None):
            s = ListNode(p.val)
            s.next = p
            p = p.next
            q.next = s
            
        return q
```

