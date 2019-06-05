[信息论基础（熵 联合熵 条件熵 信息增益](#1)

　[1.1 熵 （entropy）](#2)
  
　[1.2 联合熵](#3)
 
　[1.3 条件熵 (Conditional Entropy)](#4)

　[1.4 信息增益（Information Gain）](#5)
 
 ----------------------------------------------------------------------------------------------------------------
 
<h2 id='1'> 1. 信息论基础（熵 联合熵 条件熵 信息增益 基尼不纯度） </h2>

<h3 id='2'> 1.1 熵 （entropy） </h3>

在信息论与概率统计中，熵表示随机变量不确定性的度量。设X是一个取有限个值得离散随机变量，其概率分布为

  ![equation1](https://github.com/npk123/Algorithm-datawhale/blob/master/images/Capture.JPG)

则随机变量X的熵定义为

  ![equation1](https://github.com/npk123/Algorithm-datawhale/blob/master/images/Capture1.JPG)

若pi等于0，定义0log0=0，熵的单位为比特或者纳特。

<h3 id='3'> 1.2 联合熵 </h3>

  ![equation1](https://github.com/npk123/Algorithm-datawhale/blob/master/images/Capture4.JPG)

举个例子，更容易理解一些，比如天气是晴天还是阴天，和我穿短袖还是长袖这两个事件其可以组成联合信息熵H(X,Y)H(X,Y)，而对于H(x)H(x)就是天气单独一个事件的信息熵，因为两个事件组合起来的信息量肯定是大于单一一个事件的信息量的。 

而今天天气和我今天穿衣服这两个随机概率事件并不是独立分布的，所以如果已知今天天气的情况下，我的穿衣与天气的联合信息量/不确定程度是减少了的，也就相当于两者联合信息量已知了今天下雨，那么H(x)H(x)的信息量就应该被减去，得到当前的新联合信息量，也相当于条件信息量。 

所以当已知H(x)H(x)这个信息量的时候，联合分布H(X,Y)H(X,Y)剩余的信息量就是条件熵。

Ref：https://blog.csdn.net/gangyin5071/article/details/82228827#5%E8%81%94%E5%90%88%E4%BF%A1%E6%81%AF%E7%86%B5%E5%92%8C%E6%9D%A1%E4%BB%B6%E4%BF%A1%E6%81%AF%E7%86%B5

<h3 id='4'> 1.3 条件熵 (Conditional Entropy) </h3>

H(Y|X)表示在已知随机变量X的条件下随机变量Y的不确定性定义为X给定条件下Y的条件概率分布的熵对X的数学期望

  ![equation1](https://github.com/npk123/Algorithm-datawhale/blob/master/images/Capture2.JPG)

经验熵和经验条件熵：当熵和条件熵中的概率由数据估计（特别是极大似然估计）得到时，所对应的熵与条件熵分别称为经验熵和条件经验熵。

<h3 id='5'> 1.4 信息增益（Information Gain） </h3>

信息增益表示得知特征X的信息而使得类Y的信息的不确定性减少的程度。特征A对训练数据集D的信息增益g(D,A)，定义为集合D的经验熵H(D)与特征A给定条件下D的经验条件熵H(D|A)之差，即

  ![equation1](https://github.com/npk123/Algorithm-datawhale/blob/master/images/Capture3.JPG)

一般地，熵H(Y)与条件熵H(Y|X)之差称为互信息。决策树学习中的信息增益等价于训练数据集中类与特征的互信息。

于是我们可以应用信息增益准则来选择特征，信息增益表示由于特征A而使得对数据集D的分类的不确定性减少的程度。对数据集D而言，信息增益依赖于特征，不同的特征往往具有不同的信息增益。信息增益大的特征具有更强的分类能力。
