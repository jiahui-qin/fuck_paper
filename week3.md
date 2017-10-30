# 第三周 2017/10/30 - 2017/11/5

## Combining NMR and LC/MS Using Backward Variable Elimination:Metabolomics Analysis of Colorectal Cancer, Polyps, and HealthyControls

### 使用后向变量消除法连用NMR和LC/MS：CRC、息肉、健康对照组的代谢组学分析

时间 | 期刊 | 作者 | 机构
-|-|-|-
2016/5 | analytical chemistry | Lili Deng | |

[文献地址](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5450811/)

eveloped a backward variable elimination partial least-squares discriminant analysis algorithm embedded with Monte Carlo cross validation (MCCV-BVE-PLSDA) 联用蒙特卡洛交叉验证的偏最小二乘判别分析后向变量消除法

联用NMR和LC/MS数据 挑选变量十分重要，挑选了一个代谢物的子集，观察代谢物水平的变化

分析了来自三组受试者的127个血清样本

MCCV-BVE-PLSDA流程图

![avatar](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5450811/bin/nihms859863f1.jpg)

所有的变量都会被检查一遍,所有变量都被检查过的时候停止，每一次循环，一个代谢物被移除，剩余的变量用于PLS-DA。MCCV测试集中预测精度最高的保留用于下一个循环。对每一个代谢物做500次MCCV（重复500次验证？），将所有代谢物分为两组，70%为训练集，30%为测试集。

指标：分类精度、AUROC
*和决策树感觉很像啊。删除变量也像是后剪枝，不用决策树是因为计算比较复杂吗？*
*最后的区分结果里边MS和LC/MS没有重合，这是为什么？应该会有重合吧。在单个方法没有鉴别出来的标志代谢物而在联用中鉴别出来的代谢物P值都很高，这是代表了宏观的调控作用嘛？*
*应该可以直接分为三类？不需要两组两组的鉴别吧。*

***
***

## Prediction and early diagnosis of complex diseases by edge-network

### 使用边缘网络对复杂疾病的预测和早期诊断

时间 | 期刊 | 作者 | 机构
-|-|-|-
2013/10 | BIOINFORMATICS | Xiangtian Yu | |

[文献地址](https://academic.oup.com/bioinformatics/article-lookup/doi/10.1093/bioinformatics/btt620)

*这是一篇讲网络的文章，用的是基因，读读看能不能扩展到代谢物上*

这篇文章开发了一种新的基于边的网络，也就是edge-network，通过鉴别相应边缘标志物和它们的动态网络生成物得分来检测疾病的早期信号。基于基因表达谱的二阶统计量来推导出边缘网络能够和传统节点网络结合起来准确表示原始生物系统的随机动力学(高斯分布假设).
