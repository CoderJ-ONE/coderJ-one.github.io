---

layout: post
title: Regression回归
categories: machine-learning
description: 回归的定义和例子
keywords: Machine Learning
---

本小节了解回归的定义，并且给出一些应用例子。

---

### 回归定义

Regression 就是找到一个函数 function，通过输入特征 x，输出一个数值 Scalar。

### 应用举例

- 股市预测（Stock market forecast）
  - 输入：过去10年股票的变动、新闻咨询、公司并购咨询等
  - 输出：预测股市明天的平均值
- 自动驾驶（Self-driving Car）
  - 输入：无人车上的各个sensor的数据，例如路况、测出的车距等
  - 输出：方向盘的角度
- 商品推荐（Recommendation）
  - 输入：商品A的特性，商品B的特性
  - 输出：购买商品B的可能性
- Pokemon精灵攻击力预测（Combat Power of a pokemon）：
  - 输入：进化前的CP值、物种（Bulbasaur）、血量（HP）、重量（Weight）、高度（Height）
  - 输出：进化后的CP值

## 模型步骤

- step1：模型假设，选择模型框架（线性模型）
- step2：模型评估，如何判断众多模型的好坏（损失函数）
- step3：模型优化，如何筛选最优的模型（梯度下降）

模型分为：一元线性模型(单个特征值)和多元线性模型(多个特征值)

![](\images\posts\machine learning\6-113.jpg)



**损失函数：**是用于评判所选择模型的好坏的。

![](\images\posts\machine learning\5-18.jpg)

![](\images\posts\machine learning\6-111.jpg)



**梯度下降：**

梯度下降代表的是最优模型，所以通过梯度下降法能够找到最小的参数使得损失函数最小，即结果最优。

对于一元线性模型

![](\images\posts\machine learning\5-182.jpg)

![](\images\posts\machine learning\6-112.jpg)



同样的对于多元线性模型

![](\images\posts\machine learning\5-183.jpg)

![](\images\posts\machine learning\5-184.jpg)

这里则是按照求偏导的方式来寻找最低点，偏导的动态视频演示（在B站有介绍）。



**过拟合（Overfitting）：**

在训练集上面表现更为优秀的模型，在测试集上的效果反而变差了，这就是模型在训练集上过拟合的问题。

**正则化（Regularization）：**

由于希望模型更强大表现更好，所以加入更多参数，但是某些参数权值过高仍会导致过拟合，所以加入正则化来优化。



