---
layout: post
title: 什么是深度学习 
categories: 人工智能
tags:
    - AI
---

现在人工智能这么火，不跟上是不是以后就要被淘汰了？为什么选深度学习呢？因为目前最火嘛，哈哈啊！
后续这些文章只是学习笔记，记录一个只听说过深度学习大名的程序员深度学习的过程。


## 什么是深度学习
深度学习是机器学习的一种方法，机器学习就是让机器根据一些训练资料，自动找出有用的函数。
例如语音识别，就是机器根据一堆声音信号和其对应的文字，找到对应的函数，当输入一段声音信号时，输出该信号对应的文字。

一般机器学习要经过三个步骤：
1. 人类提供给机器一个由函数构成的集合（函数集）
2. 人类根据训练资料定义函数的优劣
3. 机器自动从函数集中找出最优的函数

既然深度学习是机器学习的一种方法，那么必然符合三个步骤。下面就分别从这三个步骤来理解深度学习。

## 人工神经网络（Artificial Neural Network）
在深度学习中，人类在第一个步骤中提供的函数集由人工神经网络定义，即人工神经网络就是函数集。

**神经元**

与人的大脑类似，人工神经网络也由神经元连接而成，只不过这里的神经元是一个简单的函数，函数的输入是一组数值（也就是一个向量）,输出是一个数值。
下图描述了一个神经元及其工作方式：
![](/images/ai/neural.jpg)
其中该神经元的输入是左侧的橙色框中的2，-1，1三个数值，输出是右侧蓝色框中的数值4。
每个输入都有一个权重（weight），图中灰色框中数值就是每个输入对应的权重。
先将输入和其对应的权重相乘后求和，再加上绿色框中的阈值（bias）作为激活函数（activation function）的输入，激活函数的输出就是神经元的输出。
激活函数是一个预先定义好的非线性函数，其输入和输出都是数值。

## 函数集
人工神经网络由神经元连接而成，作为提供给机器的函数集。

当人工神经网络中的每个神经元的参数都确定时，该神经网络就是一个非常复杂的函数。
神经元不同的连接方式组成的神经网络结构就不一样,不同的网络结构就是不同类的函数，相同的网络结构不同的参数就是不同的函数。

不同的任务的适用函数集不一样，即适合的人工神经网络不一样。
例如卷积神经网络（CNN，Convolutional Neural Network）适合做图像处理，循环神经网络（RNN，Recurrent Neural Network)适合处理序列化信息，语言翻译，语音识别等。

所以人工神经网络结构的选择对深度学习的效果有很大影响，这个选择依赖使用者的经验，直觉和尝试，可以说“运用之妙，存乎一心”。

## 定义函数的优劣
有了人工神经网络作为函数集后，接下来就要定义函数的优劣，以便在下一步让机器选择最优函数。
如何定义函数的优劣这个就需要在实践中去摸索（先留坑。。。）。

## 找出最优函数
根据训练资料可以决定一个函数的优劣，接下来就是从函数集中找出最优函数，也就是最优的参数组合，也就是所谓的“调参”。

如何找出最优参数组合，跟破解密码一样，最直接的办法就是穷举所有可能。如果计算能力足够的话，这也是最简单有效的办法。
但是，计算能力是不可能足够的，所以我们需要其他方法，也就是“学习”算法，深度学习中学习就是此意。

梯度下降法（gradient descent）是目前经常采用的学习算法。在该算法中，机器先随机指定第一组参数，再稍微调整第一组参数，找出比第一组参数略佳的第二组参数，接下来再稍微调整第二组参数，找出比第二组参数略佳的第三组参数，以此类推，反复进行直到找不出更加的参数为止。

当参数过多，梯度下降法找到最优函数的效率不够高的时候，我们就需要想办法提高参数调整的效率。反向传播算法(BP，backpropagation)，就是用来提高参数调整效率的一个算法。


## 总结
通过机器学习的三个步骤，我们大概了解了深度学习。知道了RNN,CNN,BP,激活函数和梯度下降法等是干什么用的，接下来就是深入学习为什么（算法原理）和怎么应用（tesorflow）。

* [深度学习课程](http://speech.ee.ntu.edu.tw/~tlkagk/courses_MLDS17.html) 
