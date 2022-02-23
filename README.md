
# 总结：本项目主要包括以下步骤：
## 1. 数据观察
本数据集一共包含1599条数据，其中包含11个不同的特征值，1个输出值Label。通过观察，本数据集无缺失值，但异常值较多。
## 2. 数据异常值处理
使用随机森林回归算法，将正常值视为训练数据，根据异常值的其他特征值来预测并替换异常值。
## 3. 特征处理及选择
#### ① 热力图
通过计算11个特征值之间的相关性系数生成热力图，从中可以获取特征之间的共线性和相关性。
#### ② 特征重要性排序
### 根据以上两个图表，对特征进行筛选，去除相关性较大的特征。
## 4. 模型训练及参数优化
### ① 线性回归
考虑到预测输出值为连续型数值，尝试线性回归模型拟合数据。通过预测结果和真实值的对比，放弃改模型。
### ② KNN
本数据包含Label，属于监督学习，尝试KNN模型。

通过尝试不同的neighbor数值，选择使得模型准确率最高的k值（k=1）。

通过网格搜索对KNN模型进行超参数调优，准确率并无明显提升。

通过多次随机划分训练集和测试集并计算平均模型准确率，得出模型的稳定准确率：82.2%。
