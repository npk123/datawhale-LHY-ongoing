1. 从基础概率推导贝叶斯公式，朴素贝叶斯公式

在介绍贝叶斯定理之前，先简单地介绍一下条件概率，描述的是事件 A 在另一个事件 B 已经发生条件下的概率，
记作 P(A|B)， A 和 B 可能是相互独立的两个事件，也可能不是：

P(A|B)=P(A∩B)/P(B)

P(A∩B)表示 A，B 事件同时发生的概率，如果 A 和 B 是相互独立的两个事件，那么：

P(A|B)=P(A∩B)/P(B)=P(A)*P(B)/P(B)=P(A)

上面的推导过程反过来证明了如果 A 和 B 是相互独立的事件，那么事件 A 发生的概率与 B 无关。

稍微做一下改变：

P(A∩B)=P(A|B)*P(B)

考虑到先验条件 B 的多种可能性，这里引入全概率公式：

 ![equation1](https://github.com/npk123/datawhale-LHY-ongoing/blob/master/pics/bayesian.JPG)

这里 B^c 表示事件 B 的互补事件，从集合的角度来说是 B 的补集：

条件概率和全概率公式可以通过韦恩图形象地表示出来：

 ![equation1](https://github.com/npk123/datawhale-LHY-ongoing/blob/master/pics/Wayne%20chart.jpg)
 
 在条件概率和全概率的基础上，很容易推导出贝叶斯公式：
 
 ![equation1](https://github.com/npk123/datawhale-LHY-ongoing/blob/master/pics/betasian2.JPG)

Ref: https://zhuanlan.zhihu.com/p/22467549

https://blog.csdn.net/weixin_42398658/article/details/82967039

2. 学习先验概率

P(Bi)是先验概率，是Bi发生的概率，先验概率是在得到实验观测值之前对一个参数概率的主观判断，然后我们得到一个先验概率，通过不断实验对这个数据进行修正，从而得到更接近真实客观的概率值。先验概率不需要通过贝叶斯公式计算。

3. 学习后验概率

P(Bi|A)是后验概率（也叫条件概率），是在A发生的情况下Bi发生的概率，把Bi看做原因，A看做结果，可以认为是在结果已经发生的情况下，求由Bi这一因素引起的概率多大。我看到一种更好的说法。

4. 学习LR和linear regreeesion之间的区别

线性回归：根据几组已知数据和拟合函数训练其中未知参数，使得拟合损失达到最小。然后用所得的拟合函数进行预测。 

逻辑回归：和拟合函数训练其中未知参数使得对数似然函数最大。然后用所得的拟合函数进行二分类。 

两者都是回归，步骤和原理看起来相似。但线性回归的应用场合大多是回归分析，一般不用在分类问题上。原因可以概括为以下两个：

    1.回归模型是连续型模型，即预测出的值都是连续值（实数值），非离散值；
    2.预测结果受样本噪声的影响比较大。

如下图所示

  ![equation1](https://github.com/npk123/Algorithm-datawhale/blob/master/images/Capture.JPG)

    1. 拟合函数和预测函数的关系，其实就是将拟合函数做了一个逻辑函数的转换。 
    2. 最小二乘和最大似然估计不可以相互替代。原理：最大似然估计是计算使得数据出现的可能性最大的参数，依仗的自然是Probability。而最小二乘是计算误差损失。

区别：

    1.线性回归要求变量服从正态分布，logistic回归对变量分布没有要求。
    2.线性回归要求因变量是连续性数值变量，而logistic回归要求因变量是分类型变量。
    3.线性回归要求自变量和因变量呈线性关系，而logistic回归不要求自变量和因变量呈线性关系
    4.logistic回归是分析因变量取某个值的概率与自变量的关系，而线性回归是直接分析因变量与自变量的关系

总之, logistic回归与线性回归实际上有很多相同之处，最大的区别就在于他们的因变量不同，其他的基本都差不多，
正是因为如此，这两种回归可以归于同一个家族，即广义线性模型（generalized linear model）。这一家族中的模
型形式基本上都差不多，不同的就是因变量不同，如果是连续的，就是多重线性回归，如果是二项分布，就是logistic回归。
logistic回归的因变量可以是二分类的，也可以是多分类的，但是二分类的更为常用，也更加容易解释。所以实际中最为常用的就是二分类的logistic回归。

5. 推导sigmoid function公式

数学上使用便是sigmoid函数(如下)：

  ![equation1](https://github.com/npk123/Algorithm-datawhale/blob/master/images/sigmoid%20function.jpg)
  
logistic回归的核心思想是，如果线性回归的结果输出是一个连续值，而值的范围是无法限定的，那我们有没有办法把这个结果值映射为可以帮助我们判断的结果呢。而如果输出结果是 (0,1) 的一个概率值，这个问题就很清楚了。它的输入范围为−∞→+∞，而值域刚好为(0,1)，正好满足概率分布为(0,1)的要求。用概率去描述分类器，自然要比阈值要来的方便。

而且它是一个单调上升的函数，具有良好的连续性，不存在不连续点。
  
 其求导后为
  
  ![equation1](https://github.com/npk123/Algorithm-datawhale/blob/master/images/sigmoid'.jpg)
