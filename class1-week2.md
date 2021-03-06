# 神经网络和深度学习



## Week2 神经网络基础



学习如何用神经网络的思维模式提出机器学习问题、如何使用向量化加速你的模型。


本周重点内容，最后的极大似然估计推导逻辑回归的 `cost function` 


### 2.0 逻辑回归的逻辑









### 2.1  二分分类

图片作为输入
- 3通道也进行长向量非矩阵

<img width="452" alt="pic_vec" src="https://user-images.githubusercontent.com/41643043/57415429-bb6c2680-722e-11e9-96f1-f9ec3f7c2dd0.png">


样本的矩阵表示
- 和之前想法相反
- m个样本矩阵大小 `n*m`
- y的表示 `1*m`

<img width="454" alt="notation" src="https://user-images.githubusercontent.com/41643043/57415428-bad39000-722e-11e9-9fa4-72dffb58c3ff.png">





### 2.2  `Logistic` 回归

激活函数 `sigmoid`
- z无穷大时候，输出接近1
- z无穷小时候，输出接近0

<img width="449" alt="lr" src="https://user-images.githubusercontent.com/41643043/57415718-988e4200-722f-11e9-923a-b02e44293c1e.png">



### 2.3  logistic 回归损失函数

`ground truth` 真实
- 也就是`y`



损失函数与代价函数
- 单个样本来说，也叫 `error function`，损失函数
- 对于整个样本来说，目前都把损失函数叫代价函数


逻辑函数
- 损失函数是`log`损失函数
- 采用线性回归是非凸函数



<img width="447" alt="lr_cost" src="https://user-images.githubusercontent.com/41643043/57415938-a6909280-7230-11e9-8e88-0a2237861318.png">





### 2.4  梯度下降法

##### 损失函数求最小值
- 梯度下降法应用

<img width="449" alt="cost_function" src="https://user-images.githubusercontent.com/41643043/59557903-620aca80-9018-11e9-941d-93f80a88156c.png">



##### 梯度下降的更新

注意损失函数曲线左右
- 正导数和负导数，影响损失函数曲线

<img width="447" alt="gd" src="https://user-images.githubusercontent.com/41643043/59557904-62a36100-9018-11e9-94c0-34856322358a.png">


### 2.5  导数

直观的导数例子
<img width="449" alt="dr" src="https://user-images.githubusercontent.com/41643043/57416336-7e099800-7232-11e9-8c16-47d0cfb62251.png">





### 2.6  更多导数的例子

<img width="445" alt="dw1" src="https://user-images.githubusercontent.com/41643043/57416723-d9885580-7233-11e9-8a4c-61b5b5a03d3f.png">
<img width="447" alt="more_dr" src="https://user-images.githubusercontent.com/41643043/57416727-db521900-7233-11e9-98f6-93beae092978.png">





### 2.7  计算图

定义
- 一点一点向后推导，不要跨越步骤
- 了解概念就行了

<img width="449" alt="comp_gr" src="https://user-images.githubusercontent.com/41643043/57416730-dc834600-7233-11e9-995f-31bf71d22339.png">




### 2.8  计算图的导数计算

##### 导数的反向传播
<img width="453" alt="cg" src="https://user-images.githubusercontent.com/41643043/59558415-3f7eae80-9024-11e9-95be-fbcc540e4158.png">


`python` 编程中`notice`
- `db = dJ/db`


### 2.9  `Logistic` 回归中的梯度下降法


<img width="450" alt="lr_gd" src="https://user-images.githubusercontent.com/41643043/59558486-bcf6ee80-9025-11e9-8350-8c1bcdeef9de.png">

`notice`
- 需要手工推导一遍

### 2.10  `M` 个样本的梯度下降


<img width="447" alt="m_sample" src="https://user-images.githubusercontent.com/41643043/59558600-78b91d80-9028-11e9-9220-c83aed54a568.png">

向量化
- `for loop` 的计算效率比较低
- 未来大量样本需要更高效的计算



### 2.11  向量化

向量化优点
- 采用`numpy`库代替`for loop`
- 并行运算，速度快

<img width="500" alt="ver" src="https://user-images.githubusercontent.com/41643043/59234768-d6acc600-8c20-11e9-9014-797e0fe73ba3.png">



### 2.12  向量化的更多例子

编程建议
- 避免采用`for loop`进行计算
- 如果一定进行`for loop`写法
    - 寻找`numpy`内置的函数，看看能否替代


### 2.13  向量化 `Logistic` 回归


### 2.14  向量化 `Logistic` 回归的梯度输出


<img width="500" alt="vect_logic" src="https://user-images.githubusercontent.com/41643043/59810432-b4f5c200-9337-11e9-8dea-a6ab0725e30e.png">




### 2.15  `Python` 中的广播

<img width="500" alt="bc1" src="https://user-images.githubusercontent.com/41643043/59810785-6ea16280-9339-11e9-9913-1522dc8b10b5.png">


<img width="500" alt="bc2" src="https://user-images.githubusercontent.com/41643043/59810786-6f39f900-9339-11e9-9c8d-61412ca58011.png">


<img width="500" alt="bc3" src="https://user-images.githubusercontent.com/41643043/59810787-6f39f900-9339-11e9-9f5a-7a38bfc319f1.png">




### 2.16  关于 `python/numpy` 向量的说明




### 2.17  `Jupyter/Ipython` 笔记本的快速指南



### 2.18 (选修) `Logistic` 损失函数的解释

##### 从概率角度 推导 损失函数？


<img width="446" alt="lr_1" src="https://user-images.githubusercontent.com/41643043/57416999-3d5f4e00-7235-11e9-8655-50a40c499504.png">



最小化损失函数，就是最大化概率`p`

<img width="447" alt="lr_costfun" src="https://user-images.githubusercontent.com/41643043/57417000-3df7e480-7235-11e9-840c-b0b05719a2c3.png">


极大似然估计
- 前提条件是样本独立分布

<img width="452" alt="max" src="https://user-images.githubusercontent.com/41643043/57418203-cf1b8b00-7236-11e9-88b1-1f8a6632b2aa.png">










