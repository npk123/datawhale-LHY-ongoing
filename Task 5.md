 # 1. 推导LR损失函数

损失函数

  ![equation1](https://github.com/npk123/Algorithm-datawhale/blob/master/images/logistic-loss%20function.jpg)
  
简化过后的损失函数如下
  
  ![equation1](https://github.com/npk123/Algorithm-datawhale/blob/master/images/simplified%20logistic%20loss%20function.png)
  


# 2. 学习LR梯度下降

从数学上理解，我们为了找到最小值点，就应该朝着下降速度最快的方向(导函数/偏导方向)迈进，每次迈进一小步，再看看此时的下降最快方向是哪，再朝着这个方向迈进，直至最低点。

用迭代公式表示出来的最小化J(θ)的梯度下降算法如下：
  
  ![equation1](https://github.com/npk123/Algorithm-datawhale/blob/master/images/%E4%B8%8B%E8%BD%BD1.png)
  
  ![equation1](https://github.com/npk123/Algorithm-datawhale/blob/master/images/%E4%B8%8B%E8%BD%BD2.png)
  
Ref: https://blog.csdn.net/ligang_csdn/article/details/53838743

# 3. 利用代码描述梯度下降

# 4. Softmax原理

Softmax是Logistic回归在多分类上的推广，即类标签yy的取值大于等于22。假设有mm个训练样本{(x(1),y(1)),(x(2),y(2)),⋯,(x(m),y(m))}{(x(1),y(1)),(x(2),y(2)),⋯,(x(m),y(m))}，对于Softmax回归，其输入特征为：x(i)∈Rn+1x(i)∈ℜn+1，类标记为：y(i)∈{0,1,⋯k}y(i)∈{0,1,⋯k}。假设函数为对于每一个样本估计其所属的类别的概率p(y=j∣x)p(y=j∣x)，具体的假设函数为：

![equation1](https://github.com/npk123/datawhale-LHY-ongoing/blob/master/pics/softmax%201.JPG)
  
其中θ表示的向量，且θi∈Rn+1。则对于每一个样本估计其所属的类别的概率为：

![equation1](https://github.com/npk123/datawhale-LHY-ongoing/blob/master/pics/softmax%202.JPG)
  

# 5. softmax损失函数

# 6. softmax梯度下降
