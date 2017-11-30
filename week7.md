# 第五周 2017/11/27 - 2017/12/03

啊上周摸鱼了一周什么都没看好气哦

## Integrative information theoretic network analysis for genome-wide association study of aspirin exacerbated respiratory disease in Korean population

时间 | 期刊 | 作者 | 机构
-|-|-|-
2017/5 | BMC Medical Genomics | Sehee Wang, Hyun-hwan Jeong | |

[BMC地址](https://bmcmedgenomics.biomedcentral.com/articles/10.1186/s12920-017-0266-1)

这篇是大概11/20邓伶俐师姐推荐给我的，讲基因组学中建立网络

首先先说个基因组学中的知识点：

Single nucleotide polymorphisms (SNP) [单核苷酸多态性](https://www.zhihu.com/question/36802286),这个里边讲的比较好：SNP（单核苷多态性）是一个统计学概念。即，基因组中，群体中minor allele frequency 大于 1%的位点。但是在日常使用中，有些同学在说某一个特定样品DNA里面的单碱基突变也叫做SNP。根据上下文判断。 总而言之，SNP是易于检测的基因组学中的**差异**。

这篇文章是研究寻找与AERD相关的基因

样本来自韩国188个AERD(阿司匹林加剧呼吸系统疾病)和247个ATA(阿司匹林耐受性哮喘)的440094个SNP，删去了次要等位基因频率小于0.05的SNP，剩余320815个

1.SNP网络的构建：SNP网络中的边权重定义为一对SNP与疾病之间的关联强度，分别用MI和IG来计算，MI在很大程度上收到SNP边际效益的影响，IG主要反映协同效应，因此用两种方法来建立网络，比较主要特征，将这两个网络结合起来

1.用SNP网络构建geng-geng网络：一个基因之中会包含多个SNP，那么如何来确定基因与基因之间的权重呢？这里考虑了采用最大值、均值、平均值、最小值，求和的话偏向于较长的基因累计较高的权值，大部分SNP边权重都比较小，均值、最小值会受到影响，所以考虑使用最大值。*结果部分讨论了基因大小与节点的度之间的相关性*

1.提取统计显著的网络：使用R^2来检查网络的无标度性质，有一个现实存在的与哮喘相关的基因作为对比，计算出p值，来决定一个阈值α进行边的选择,对于每一个边，对疾病标签重新随机排列，计算排列之后的边缘权重平均值，选择最大的边权重作为阈值θ。用[32]中θ*（1 +α）来决定边的选择

最后将两个网络合并起来分析

*这篇文章需要注意的地方就是将两个网络合并起来，然后还有边的权重的选择上都可以借鉴*

*感觉IG的公式写错了不会是我的错觉吧，扫了一遍他引用的[A flexible computational framework for detecting, characterizing, and interpreting statistical patterns of epistasis in genetic studies of human disease susceptibility](http://www.sciencedirect.com/science/article/pii/S0022519305005217?via%3Dihub)感觉他还是写错了*