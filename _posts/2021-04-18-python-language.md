---
layout: post
title: python语法
categories: python
description: 详细记录python的语法知识
keywords: python语法
---

本文是用于记录Python语言语法相关的笔记的。

---

本文从代码审查过程中发现的一个 ArrayList 相关的「线程安全」问题出发，来剖析和理解线程安全。

## Python的介绍

python是一门面向对象的脚本语言,通常以容易修改程序的“解释”作为运行方式，而不需要“编译”。

IDLE： 是一个 Python Shell，shell 的意思就是“外壳”，基本上来说，就是一个通过键入文本与程序交互的途径！像我们 Windows 那个 cmd 窗口，像 Linux 那个黑乎乎的命令窗口，他们都是 shell，利用他们，我们就可以给操作系统下达命令。同样的，我们可以利用 IDLE 这个 shell 与 Python 进行互动。

BIF 就是 Built-in Functions，内置函数。为了方便程序员快速编写脚本程序（脚本就是要编程速度快），Python 提供了非常丰富的内置函数，我们只需要直接调用即可，例如 print() 的功能是“打印到屏幕”，input() 的作用是接收用户输入。

在 Python 或 IDLE 中，输入 dir(__builtins__) 可以看到 Python 提供的内置方法列表（注意，builtins 前后是两个下划线哦）其中小写的就是 BIF。如果想具体查看某个BIF 的功能，比如 input()，可以在 shell 中输入 help(input)，就会得到这个 BIF 的功能描述。

还有help(*)函数的作用类似于c语言中库函数的描述文档

![](/images/posts/python/3.png)

## 基本语法操作代码：

![](/images/posts/python/1.png)

![](/images/posts/python/2.png)

![](/images/posts/python/4.png)

上面可以注意到 python语言中if和else的控制语句并没有所谓的括号和大括号，而是利用缩进来控制

所以缩进是python语法的关键！缩进错误了可能导致整个程序崩溃。

![](/images/posts/python/5.png)

![](/images/posts/python/6.png)

下面是一些基本的运算符：

![](/images/posts/python/7.png)

注意不同运算符之间的比较级关系

![](/images/posts/python/8.png)

![](/images/posts/python/9.png)

python语言下的for循环和控制符：

语法形式   for 目标 in 表达式：

```cpp
str = "hello world"
for i in str:
    print(i,end=' ')
print('\n')
each = ["Hello","Python"]
for i in each:
    print(i,len(i))
#rang()函数
for i in range(1,10,2):  #输出1-10内从1 开始间隔步数为2的数据
    print(i)
print("--------\n")
for i in range(1,10,2):
    if i==3 : continue
    elif i==7 : break
    print(i)

```

输出的结果：

```python
h e l l o   w o r l d 

Hello 5
Python 6
1
3
5
7
9
--------
1
5
```

