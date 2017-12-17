# 第四周 2017/11/13 - 2017/11/20

## Adjusted Analyses in Studies Addressing Therapy and Harm Users’ Guides to the Medical Literature

时间 | 期刊 | 作者 | 机构
-|-|-|-
2017/2 | JAMA |Thomas Agoritsas | |

考虑一个年龄元素对于最后结果的影响：治疗组有100患者，80年轻人20老人。对照组有100患者，20年轻人，80老人。经过治疗之后，治疗组有4名老人死亡，8名年轻人死亡；对照组有2个年轻人死亡，16个老人死亡。没有调整过的与对照组相比的死亡风险为12%/16%，也就是0.67.考虑年龄因素，年轻人治疗组中80个死8个，对照组20个死2个，相比死亡风险为1，老年中治疗组是20个死4个，对照组是80个死16个，相比死亡风险也为1.因此调整过的就是1

先讨论文中的第一种方法：

1. [工具变量估计, Instrumental variables estimation](https://en.wikipedia.org/wiki/Instrumental_variables_estimation)，先给出几个关键字：[内生性,Endogeneity](https://en.wikipedia.org/wiki/Endogeneity_(econometrics)), [Omitted-variable bias](https://en.wikipedia.org/wiki/Omitted-variable_bias), [Homogeneity](https://en.wikipedia.org/wiki/Homogeneity_(statistics))

先讨论一个普通的OLS回归，y=xβ+error,正常情况下我们假设x和error不相关，但是当x和error相关是，OLS就不是无偏的了。我们假定error中的元素通过影响x来影响y，这时称omitted variable是endogeneity的。为了解决这个问题，我们先建立一个工具变量(IV),假设IV与error无关，只与y有关，我们先求IV与X的OLS，再求求出来之后的IV与Y的回归，这时候就可以称这是一个2SLS

[工具变量 (Instrumental variables) 的作用到底是什么](https://www.zhihu.com/question/29067965)这个回答讲的很清楚

*这里重要的是找到一个工具变量，工具变量的选择会直接影响最后的结果，我认为这个是比较困难的，但是我们是否可以反方向，从我们可以测量的变量着手去处理？*

*我们可以找到的混杂变量比如年龄、性别等因素应该与error是有关的，通过影响代谢物水平来影响最后的表达，再看看吧···明天和师兄讨论一下*