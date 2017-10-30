# 第三周 2017/10/30 - 2017/11/5

## Combining NMR and LC/MS Using Backward Variable Elimination:Metabolomics Analysis of Colorectal Cancer, Polyps, and HealthyControls

### 使用后向变量消除法连用NMR和LC/MS：CRC、息肉、健康对照组的代谢组学分析

[文献地址](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5450811/)

eveloped a backward variable elimination partial least-squares discriminant analysis algorithm embedded with Monte Carlo cross validation (MCCV-BVE-PLSDA) 联用蒙特卡洛交叉验证的偏最小二乘判别分析后向变量消除法

联用NMR和LC/MS数据 挑选变量十分重要，挑选了一个代谢物的子集，观察代谢物水平的变化

分析了来自三组受试者的127个血清样本

MCCV-BVE-PLSDA流程图

![avatar](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5450811/bin/nihms859863f1.jpg)

所有的变量都会被检查一遍,所有变量都被检查过的时候停止，每一次循环，一个代谢物被移除，剩余的变量用于PLS-DA。MCCV测试集中预测精度最高的保留用于下一个循环。对每一个代谢物做500次MCCV（重复500次验证？），将所有代谢物分为两组，70%为训练集，30%为测试集。

指标：分类精度、AUROC

*和决策树感觉很像啊。*

