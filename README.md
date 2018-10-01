# 每日一题

[daily-question ](https://github.com/amusi/daily-question) 涉及但不局限于机器学习、深度学习和计算机视觉等方向

Warning：众人拾柴火焰高，如果大家有看到很好的题目，可以通过提交issue的方式把题目和答案分享出来，互相学习，一起进步



# 题目

**1.【排序题】梯度下降算法的正确步骤是什么？**

a.计算预测值和真实值之间的误差

b.重复迭代，直至得到网络权重的最佳值

c.把输入传入网络，得到输出值

d.用随机值初始化权重和偏差

e.对每一个产生误差的神经元，调整相应的（权重）值以减小误差

答案：dcaeb


**2.【多选题】小明在训练深度学习模型时，发现训练集误差不断减少，测试集误差不断增大，以下解决方法正确的是？**

A. 数据增广

B. 增加网络深度

C. 提前停止训练

D. 添加Dropout

答案：ACD


**3.【单选题】以下关于鞍点上的Hessian矩阵的描述哪个是正确的？**

A. 正定矩阵

B. 负定矩阵

C. 半正定矩阵

D. 都不对

答案：D

【解析】鞍点：梯度等于零，在其附近Hessian矩阵有正的和负的特征值，行列式小于0，即是不定的。 

参考：[鞍点](https://blog.csdn.net/baidu_27643275/article/details/79250537)

**4.【单选题】以下几种优化方法中，哪种对超参数最不敏感？**

A. SGD（stochatic gradient descent）

B. BGD（batch gradient descent）

C. Adadetla

D. Momentum

答案：C

【解析】

1）SGD受到学习率α影响

2）BGD受到batch规模m影响

3）Adagrad的一大优势时可以避免手动调节学习率，比如设置初始的缺省学习率为0.01，然后就不管它，另其在学习的过程中自己变化。

为了避免削弱单调猛烈下降的减少学习率，Adadelta产生了1。Adadelta限制把历史梯度累积窗口限制到固定的尺寸w，而不是累加所有的梯度平方和

4）Momentum：也受到学习率α的影响

**5.【多选题】为什么正则化能处理过拟合？**

A.惩罚了模型的复杂度，避免模型过度学习训练集，提高泛化能力

B.剃刀原理：如果两个理论都能解释一件事情，那么较为简单的理论往往是正确的

C.正则项降低了每一次系数w更新的步伐，使参数更小，模型更简单

D.贝叶斯学派的观点，认为加入了先验分布（l1拉普拉斯分布，l2高斯分布），减少参数的选择空间

答案：ABCD

【解析】A/C 选项没有问题，只不过C中的"步伐"理解起来并不清晰。B/D选项是有点追本溯源的意思，剃刀原理其实是奥卡姆剃刀原理：更小的权值w，从某种意义上说，表示网络的复杂度更低，对数据的拟合刚刚好；从贝叶斯角度理解，为参数 ω 引入拉普拉斯先验分布的最大似然，相当于给均方误差函数加上L1正则项；为参数 ω引入高斯先验分布的最大似然，相当于给均方误差函数加上L2正则项。


参考：

[正则化为什么能防止过拟合（重点地方标红了）](https://www.cnblogs.com/alexanderkun/p/6922428.html)

[【机器学习】从贝叶斯角度理解正则化缓解过拟合](https://blog.csdn.net/u014433413/article/details/78408983)

**6.【单选题】假设你有5个大小为7x7、边界值（Padding）为0，步长（S）为1的卷积核。此时如果你向这一层传入一个维度为224x224x3的数据，那么神经网络下一层所接收到的数据维度是多少？（B）**

A. 220x220x5

B. 218x218x5

C. 217x217x8

D. 217x217x3

答案：B

【解析】卷积计算公式：Hout=（Himg+2Padding−Kfilterh）/S + 1；Wout=（Wimg+2Padding−Kfilterw）/S + 1。其中Padding是边界填空值，Kfilterw表示卷积核的宽度，S表示步长。

**7.【单选题】假设我们有一个5层的神经网络，这个神经网络在使用一个4GB显存显卡时需要花费3个小时来完成训练。而在测试过程中，单个数据需要花费2秒的时间。如果我们现在把架构变换一下，当评分是0.2和0.3时，分别在第2层和第4层添加Dropout，那么新架构的测试所用时间会变为多少？**

A. 少于2秒

B. 大于2秒

C. 仍是2秒

D. 说不准

答案：C

【解析】在架构中添加Dropout这一改动仅会影响训练过程，而并不影响测试过程。

**8.【单选题】假定目标变量的类别非常不平衡，即主要类别占据了训练数据的99%，现在你的模型在测试集上表现为99%的准确度。那么下面哪一项表述是正确的？（B）**

A. 准确率适合于衡量不平衡类别问题

B. 精确率和召回率适合于衡量不平衡类别问题

C. 精确率和召回率不适合于衡量不平衡类别问题

D. 上述选项都不对

**9.【单选题】下面哪项操作能实现跟神经网络中Dropout的类似效果？（B）**

A. Boosting

B. Bagging

C. Stacking

D. Mapping

答案：B

【解析】dropout的思想继承自bagging方法。

bagging是一种集成方法（ensemble methods）,可以通过集成来减小泛化误差（generalization error）。 
bagging的最基本的思想是通过分别训练几个不同分类器，最后对测试的样本，每个分类器对其进行投票。在机器学习上这种策略叫model averaging。 我们可以把dropout类比成将许多大的神经网络进行集成的一种bagging方法。 

**10.【单选题】在感知机（Perceptron）中的任务顺序是什么？**

1. 随机初始化感知机权重

2. 去到数据集的下一批（batch）

3. 如果预测值和输出不一致，则调整权重

4. 对一个输入样本，计算输出值

A. 1,2,3,4

B. 4,3,2,1

C. 3,1,2,4

D. 1,4,3,2

答案：D

**11.【单选题】下列哪项关于模型能力（model capacity）的描述是正确的？（指神经网络模型能拟合复杂函数的能力）**

A. 隐藏层层数增加，模型能力增加

B. Dropout的比例增加，模型能力增加

C. 学习率增加，模型能力增加

D. 都不正确

答案：A

**12.【单选题】关于Logistic回归和SVM，以下说法错误的是？**

A. Logistic回归可用于预测事件发生概率的大小

B. Logistic回归的目标函数是最小化后验概率

C. SVM的目标的结构风险最小化

D. SVM可以加入正则化项，有效避免模型过拟合

答案：B

【解析】Logistic回归本质上是一种根据样本对权值进行极大似然估计的方法，而后验概率正比于先验概率和似然函数的乘积。Logistic仅仅是最大化似然函数，并没有最大化后验概率，更谈不上最小化后验概率。A正确 Logit回归的输出就是样本属于正类别的几率，可以计算出概率；C正确. SVM的目标是找到使得训练数据尽可能分开且分类间隔最大的超平面，应该属于结构风险最小化. D正确. SVM可以通过正则化系数控制模型的复杂度，避免过拟合。

**13.【单选题】在其他条件不变的前提下，以下哪种做法容易引起机器学习中的过拟合问题？**

A 增加训练集量 

B 减少神经网络隐藏层节点数 

C 删除稀疏的特征

D SVM算法中使用高斯核/RBF核代替线性核

答案：D

【解析】一般情况下，越复杂的系统，过拟合的可能性就越高，一般模型相对简单的话泛化能力会更好一点。

B.一般认为，增加隐层数可以降低网络误差（也有文献认为不一定能有效降低），提高精度，但也使网络复杂化，从而增加了网络的训练时间和出现“过拟合”的倾向， svm高斯核函数比线性核函数模型更复杂，容易过拟合

D.径向基(RBF)核函数/高斯核函数的说明,这个核函数可以将原始空间映射到无穷维空间。对于参数 ，如果选的很大，高次特征上的权重实际上衰减得非常快，实际上（数值上近似一下）相当于一个低维的子空间；反过来，如果选得很小，则可以将任意的数据映射为线性可分——当然，这并不一定是好事，因为随之而来的可能是非常严重的过拟合问题。不过，总的来说，通过调整参数 ，高斯核实际上具有相当高的灵活性，也是 使用最广泛的核函数 之一。


**14.【多选题】以下哪些选项属于线性分类器准则?**

A.感知准则函数

B.贝叶斯分类

C.支持向量机

D.Fisher准则

答案：ACD


【解析】
线性分类器有三大类：感知器准则函数、SVM、Fisher准则，而贝叶斯分类器不是线性分类器。

感知准则函数 ：准则函数以使错分类样本到分界面距离之和最小为原则。其优点是通过错分类样本提供的信息对分类器函数进行修正，这种准则是人工神经元网络多层感知器的基础。

支持向量机 ：基本思想是在两类线性可分条件下，所设计的分类器界面使两类之间的间隔为最大，它的基本出发点是使期望泛化风险尽可能小。（使用核函数可解决非线性问题）

Fisher 准则 ：更广泛的称呼是线性判别分析（LDA），将所有样本投影到一条远点出发的直线，使得同类样本距离尽可能小，不同类样本距离尽可能大，具体为最大化“广义瑞利商”。

根据两类样本一般类内密集，类间分离的特点，寻找线性分类器最佳的法线向量方向，使两类样本在该方向上的投影满足类内尽可能密集，类间尽可能分开。这种度量通过类内离散矩阵 Sw 和类间离散矩阵 Sb 实现。

**15.【单选题】下列哪个神经网络结构会发生权重共享？**

A. 卷积神经网络 

B. 循环神经网络 

C. 全连接神经网络 

D. 选项A和B 

答案：D


**16.【单选题】关于支持向量机SVM,下列说法错误的是？**

A.L2正则项，作用是最大化分类间隔，使得分类器拥有更强的泛化能力

B.Hinge 损失函数，作用是最小化经验分类错误

C.分类间隔为1/||w||，||w||代表向量的模

D.当参数C越小时，分类间隔越大，分类错误越多

答案：C

【解析】@刘炫320，本题题目及解析来源：http://blog.csdn.net/column/details/16442.html

A正确。考虑加入正则化项的原因：想象一个完美的数据集，y>1是正类，y<-1是负类，决策面y=0，加入一个y=-30的正类噪声样本，那么决策面将会变“歪”很多，分类间隔变小，泛化能力减小。加入正则项之后，对噪声样本的容错能力增强，前面提到的例子里面，决策面就会没那么“歪”了，使得分类间隔变大，提高了泛化能力。

B正确。

C错误。间隔应该是2/||w||才对，后半句应该没错，向量的模通常指的就是其二范数。

D正确。考虑软间隔的时候，C对优化问题的影响就在于把a的范围从[0，+inf]限制到了[0,C]。C越小，那么a就会越小，目标函数拉格朗日函数导数为0可以求出w=求和ai∗yi∗xi，a变小使得w变小，因此间隔2/||w||变大。

**17.【单选题】在一个神经网络中，下面哪种方法可以用来处理过拟合？**

A.Dropout

B.分批归一化(Batch Normalization)

C.正则化(regularization)

D.上述选项都可以

答案：D


**18.【单选题】输入图片大小为200×200，依次经过一层卷积（kernel size 5×5，padding 1，stride 2），pooling（kernel size 3×3，padding 0，stride 1），又一层卷积（kernel size 3×3，padding 1，stride 1）之后，输出特征图大小为？**

A.95

B.96

C.97

D.98

答案：C




**19.【单选题】深度学习是当前很热门的机器学习算法，在深度学习中，涉及到大量的矩阵相乘，现在需要计算三个稠密矩阵A,B,C的乘积ABC,假设三个矩阵的尺寸分别为m∗n，n∗p，p∗q，且m < n < p < q，以下计算顺序效率最高的是？**

A.(AB)C

B.AC(B)

C.A(BC)

D.上述所有选项效率相同

答案：A

【解析】首先，根据简单的矩阵知识，因为 A*B ， A 的列数必须和 B 的行数相等。因此，可以排除 B 选项，

然后，再看 A 、 C 选项。在 A 选项中，m∗n 的矩阵 A 和n∗p的矩阵 B 的乘积，得到 m∗p的矩阵 A\*B ，而 A∗B的每个元素需要 n 次乘法和 n-1 次加法，忽略加法，共需要 m∗n∗p次乘法运算。同样情况分析 A*B 之后再乘以 C 时的情况，共需要 m∗p∗q次乘法运算。因此， A 选项 (AB)C 需要的乘法次数是 m∗n∗p+m∗p∗q 。同理分析， C 选项 A (BC) 需要的乘法次数是 n∗p∗q+m∗n∗q。


**20.【单选题】你可能只有少量数据来解决这个问题。不过幸运的是你有一个类似问题已经预先训练好的神经网络。可以用下面哪种方法来利用这个预先训练好的网络？**

A.把除了最后一层外所有的层都冻结，重新训练最后一层

B.对新数据重新训练整个模型

C.只对最后几层进行调参(fine tune)

D.对每一层模型进行评估，选择其中的少数来用

答案：C

【解析】如果有个预先训练好的神经网络, 就相当于网络各参数有个很靠谱的先验代替随机初始化. 若新的少量数据来自于先前训练数据(或者先前训练数据量很好地描述了数据分布, 而新数据采样自完全相同的分布), 则冻结前面所有层而重新训练最后一层即可; 但一般情况下, 新数据分布跟先前训练集分布有所偏差, 所以先验网络不足以完全拟合新数据时, 可以冻结大部分前层网络, 只对最后几层进行训练调参(这也称之为fine tune)。

**21.【单选题】对于神经网络的说法, 下面正确的是 ？**

增加神经网络层数, 可能会增加测试数据集的分类错误率
减少神经网络层数, 总是能减小测试数据集的分类错误率
增加神经网络层数, 总是能减小训练数据集的分类错误率
A. 1

B. 1 和 3

C. 1 和 2

D. 2

答案：A

【解析】深度神经网络的成功, 已经证明增加神经网络层数, 可以增加模型范化能力, 也就是，训练数据集和测试数据集都表现得更好。但这篇文献中（https://arxiv.org/pdf/1512.03385v1.pdf）, 作者提到更多的层, 也不一定能保证有更好的表现. 所以不能绝对地说层数多的好坏, 只能选A


**22.【单选题】下面哪种情况适用于Focal Loss？**

A.分类过程中类别不平衡

B.实例分割过程中，相同类别图像距离过小

C.提取语义信息时，高层语义过少的时候

D.物体定位时，目标面积过小

答案：A

【解析】Focal Loss最初是在[RetinaNet](https://arxiv.org/abs/1708.02002)论文中提出，旨在解决one-stage目标检测中正负样本不均衡的问题，也可扩展到样本的类别不均衡问题上。该损失函数降低了大量简单负样本在训练中所占的权重。

类似的还有OHEM，感兴趣的童鞋可以自行查阅。