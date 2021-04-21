---

layout: post
title: python集合
categories: python
description: 详细记录python的语法知识
keywords: python集合
---

本小节了解python语法中集合相关的使用方法和一些内置函数。

---

Note如果想查看List所有的操作函数 

dir(list)即可

**1.列表List：**

首先要注意 python中的列表就如同cpp的vector数组一般，但是不同之处在于，如果是cpp的vector数组那么声明的时候vector<类型>表面当前动态数组中只能存入同一种类型的元素，但是python的List却是一个可以存储混合元素的集合。

```python
sq = [1,2,3,"hello world",["one","two","three"],[]]
for i in sq:
    print(i,end='\n')
```

输出：

```python
1
2
3
hello world
['one', 'two', 'three']
[]  #相当于空的列表List
```



## 列表元素添加

向列表内添加元素的方法有三种：

**append**

**extend**

**insert**



append()：向列表的末尾添加一个元素

```python
sq = [1,2,3]
sq.append("new word")
for i in sq:
    print(i,end='\n')
```

输出：

```python
1
2
3
new word
```

这个函数的缺点就是每次只能够添加一个元素



extend():向列表末尾添加多个元素

```python
sq = [1,2,3]
sq.extend(["hello",5,6,7,8])
for i in sq:
    print(i,end='\n')
```

输出：

```python
1
2
3
hello
5
6
7
8
```

该方法依旧有缺陷：就是只能对列表的末尾进行拓展，所以就要用到下面的这个方法。



insert():向列表的第n个元素前插入数据，切记这个列表的元素下标也是从0开始的。

```python
sq = [1,2,3]
sq.extend(["hello",5,6,7,8])
for i in sq:
    print(i,end=' ')
print('\n')
sq.insert(3,['one','two'])
for i in sq:
    print(i,end=' ')

```

输出：

```python
1 2 3 hello 5 6 7 8 

1 2 3 ['one', 'two'] hello 5 6 7 8 
```



## 列表元素移除操作

对列表执行删除操作的方法也有三种：

**remove**

**del**

**pop**



remove():从列表删除某个元素

```python
sq = [1,2,3,'one']
sq.remove('one')
for i in sq:
    print(i,end=' ')
```

输出：

```python
1 2 3 
```





del():删除某个元素

```python
sq = [1,2,3,'one']
del sq[3]
for i in sq:
    print(i,end=' ')
print('\n')
```

输出：

```python
1 2 3 
```



pop()：取出列表的最后一个元素

```python
sq = [1,2,3,'one']
print(sq.pop())
```

输出：

```python
one
```



## 列表分片(Slice)：

利用索引值，每次我们可以从列表获取一个元素，但是我们总是贪心的，如果一次性需要获取多个元素，有没有办法实现呢？利用列表分片，我们可以简单的实现这个要求。

```python
sq = [1,2,3,'one',5,6,7,8,9]
mem = sq[3:5]
for i in mem:
    print(i,end=' ')
```

输出：

```python
one 5 
```

可以知道是从下标[3,5)来进行切片

**对于分片拷贝的补充（重要）**

```python
list1 = [1,2,3,4,5]
list2 = list1
list3 = list1[:]
for i in list2:
    print(i,end=' ')
print('\n')
for i in list3:
    print(i,end=' ')
list1.remove(5)
print('\n')
print("next->\n")
for i in list2:
    print(i,end=' ')
print('\n')
for i in list3:
    print(i,end=' ')
```

输出：

```python
1 2 3 4 5 

1 2 3 4 5 

next->

1 2 3 4  #list2

1 2 3 4 5 #list3
```

上面的情况中可以发现，list2的列表值因为list1的改变而改变了，这里借鉴C语言指针的思维，其实list2=list1的概念等同于list2是保存了list1所指向的列表内容的地址，所以list1改变了随即也会发生变化，但是list3的分片拷贝才是真正意义上的单独开辟一块空间来保存拷贝的列表值。



## 列表的操作符：

比较操作符：

```python
list1 = [1,2,3,4]
list2 = [1,3,2,4]
if list1 > list2:
    print('yes')
else:
    print('no')
```

输出：

```python
no
```



逻辑操作符：

```python
list1 = [1,2,3,4]
list2 = [1,3,2,4]
if list1 < list2 and list1 != list2:
    print('yes')
```

输出：

```python
yes
```



连接操作符：

```python
list1 = [1,2,3,4]
list2 = [1,3,2,4]
list = list1 + list2
```

输出：

```python
>>> list
[1, 2, 3, 4, 1, 3, 2, 4]
```



重复操作符：

```python
list1 = [1,2,3,4]
```

输出：

```python
>>> list1 * 3
[1, 2, 3, 4, 1, 2, 3, 4, 1, 2, 3, 4]
```



成员关系操作符：

```python
list1 = [123,245,3333,455]
```

输出：

```python
>>> 123 in list1
True
>>> 333 in list1
False
```



## 其他的一些操作：

count():计算列表中相同元素的个数

```cpp
list = [123,245,3333,455,123,455,123]
```

输出：

```python
>>> list.count(123)
3
```



index():返回制定值的索引下标

```python
list = [123,245,3333,455,123,455,123]
```

输出：

```python
>>> list.index(3333)
2
```



reverse():将列表元素逆序

```python
list = [1,2,3,4,5,6,7]
list.reverse()
for i in list:
    print(i,end=' ')
```

输出：

```python
7 6 5 4 3 2 1 
```



sort():将列表元素排序

```python
list = [1,3,2,5,4,6,7]
list.sort()
for i in list:
    print(i,end=' ')
```

输出：

```python
1 2 3 4 5 6 7 
```



**2.元组Tuple:**



创建元组：

```python
tuple1 = 1,2,3,4
tuple2 = (1,2) 
```

输出：

```python
>>> tuple1
(1, 2, 3, 4)
>>> tuple2
(1, 2)
```

由上面形式可知，括号可以没有但是逗号是元组必须要有的。



访问前几个元素：

```python
tuple1 = 1,2,3,4
```

输出：

```python
>>> tuple1[:2]
(1, 2)
```

输出前两个元素

元组的其他的操作方式：

```python
arr = ('a','b','c','d','e','f')
arr = arr[:2] + ('new',) + arr[2:]
```

输出：

```python
>>> arr
('a', 'b', 'new', 'c', 'd', 'e', 'f')
```

这里需要注意，原先的arr元组并没有发生修改只不过是生成了新的元组，原来的arr元组会被自动回收。

删除一个元组

```python
del arr
```

元组相关的剩余操作用到时候进行查询即可。





