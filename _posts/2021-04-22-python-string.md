---

layout: post
title: python字符操作和序列
categories: python
description: 详细记录python的语法知识
keywords: python字符操作和序列
---

本小节了解python语法中字符串相关以及序列的用法。

---

字符串有许多的内置方法，可以在使用的时候进行查询,如下：

![](/images/posts/python/10.jpg)

![](/images/posts/python/11.jpg)



## 字符串的格式化：

```python
>>> "{0} love {1}".format("I","You")
'I love You'
>>> "{a} love {b}".format(a="I",b="You")
'I love You'
>>> '{0:.1f}{1}'.format(3.14,'GB') #.1f 浮点型保留一位
'3.1GB'
>>> '%c' % 97
'a'
>>> '%c %c %c' % (97,98,99)
'a b c'
>>> '%d + %d = %d' % (1,2,1+2)
'1 + 2 = 3'
>>> '%.1f' % 123.123
'123.1'
>>> '%#o' % 10
'0o12'
>>> '%#x' % 16
'0x10'
>>> '%05d' % 3
'00003'
>>> 
```



## 序列化：

```python
>>> str = list('hello world')
>>> str
['h', 'e', 'l', 'l', 'o', ' ', 'w', 'o', 'r', 'l', 'd']
```

元组转化为列表：

```python
>>> tuple1 = (1,2,3,4,5)
>>> tuple2 = list(tuple1)
>>> tuple2
[1, 2, 3, 4, 5]
```

max，min函数：返回元组中最值

```python
>>> max(1,2,3,4)
4
>>> min(1.22,3.22,5)
1.22
```

sum函数返回序列总和：

```python
>>> a = (1.2,3.1,4.5)
>>> sum(a,0.5)
9.3
```

sorted函数：

```python
>>> a = (3,2,4,1,6)
>>> sorted(a)
[1, 2, 3, 4, 6]
```

reversed函数:

```python
>>> a = (3,2,4,1,6)
>>> list(reversed(a))
[6, 1, 4, 2, 3]
```

enumerate()将每个元素插入枚举:

```python
>>> num = [1,2,3,4,5]
>>> list(enumerate(num))
[(0, 1), (1, 2), (2, 3), (3, 4), (4, 5)]
```

zip()返回由各个参数的序列组成的元组:

```python
>>> a = [3,4,5,6]
>>> b = [7,8,9,10,11,12]
>>> list(zip(a,b))
[(3, 7), (4, 8), (5, 9), (6, 10)]
```

