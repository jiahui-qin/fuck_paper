# A sparse multi-source data method based on variable complementarity

## abstract

在代谢组学中我们有许多方法可以进行检测，最常用的是NMR和MS,两种方法中可以检测出许多互补性的特征，但是在数据中更多存在的是相似性特征。为了解决这个问题我们提出了一种基于变量互补性的数据稀疏方法：分别使用G2检验和扩展似然比检验来检验变量中包含的相似性和互补性，然后使用SIS-SPLS对相似变量进行稀疏化。这个方法在模拟数据检验和实际数据检验中都体现出了不错的效果**实际数据检验需要再找一个比较靠谱的数据**

In metabolomics study we can apply many technology, the most popular method are nuclear magnetic resonance(NMR) spectroscopy and mass spectrometry(MS). Use the two methods we indeed can detect many complementary features, but more of them are similar features. To overcome the issue, a sparse multi-source data method based on variable complementarity was proved. First, the similarity and complementarity of the variables were tested using the G2 test and the diffreg test, respectively, and the similar variables were then sparsified using SIS-SPLS. This method was evaluated using a number of numerical studies including simulation and real datasets, the result show the method is efficient in variable sparse.

## introduction

本节介绍一下在代谢组学中多源数据的应用，这里可以提几篇MS，NMR连用分析的文章；多源数据中存在的问题：大部分数据是重叠的，少部分数据是互补的。我们需要找出互补的数据，对重叠的数据进行稀疏化。

*本节要提出问题，描述问题的重要性，别人的工作与不足，我们的思路和出发点*

Metabolomics plays an important role in systems biology to investigate states through the study of changes in metabolite concentrations and fluxes. 这一段写代谢组学

There are two methods nuclear magentic resonance spectroscopy (NMR) and mass spectrometry (MS) that are most widely use in metabolomics.这一段介绍NMR和MS，介绍两种方法的特点

NMR and MS generate different metaboliv profiles from the same sample, natural to think that if we can use both the two methods at the same time, more information of the sample will be obtain. Although most of the current work is still using only one method, but the experiment of the combine two methods is becoming more and more. 这一段写NMR和MS联用的文章

这一段写别人的分析方法

In this article we have carefully analyzed the results of NMR and MS: Both methods present a great deal of similarity to the results obtained for the same sample, and a little information is complementary. Therefore we can detect the complementary variables of the two methods result, then sparse the remaining similarity variables.接下来将提取互补性特征和稀疏化的方法 We tested this method on both the simulated dataset and the real MS-NMR dataset, and concluded that this is indeed a valid method for analyzing multi-source data



## method

本节介绍如何对变量相似性、互补性进行检验

1. 检验变量相似性的时候，X2=X1B+E 使用G2检验：这里直接写结论，G2检验用于检验样本数较小而特征数较大时比较有用(优势)：通过限制备择空间。然后使用统计量R^2来进行检验

1. Nicolas et al. Proposed DiffReg test [6] to test whether there is any significant difference between the two models.**介绍diffreg检验**In the actual data, the data usually obtained through the two models are focused on each other. The information in one model can be supplemented to some extent by the information in the other model. The supplementary information makes the model explain the response even more accurate.介绍用diffreg检验来验证检验变量互补性的时候，Y=X1B1+X2B2+e 使用扩展似然比检验： 用来检验两个模型之间是否存在显著性差异**这里师兄提到diffreg检验中的screen方法需要再选择一个效果比较好的方法**

1. There are many similar variables in the actual data, and these similar variables need to be sparsed to obtain an easily interpretable result. PLS is one of the most common and easiest methods of sparse, PLS by projecting the original variables X on some latent variables T and establishing a linear model of these latent variables and responses Y. PLS can effectively reduce the number of variables and reduce the dimensionality; however, PLS can not automatically implement variable selection. In many cases, only a small part of the variables contribute to the model. Modeling with all the original variables may degrade the performance of the PLS model. Some researchers proposed the SPLS method for the shortcomings of PLS, and implemented the sparsity of the model through a penalty of L1 norm. This method can not only get a sufficiently sparse model, but also enable variable selection. However, the progressive nature of this method is not fully discussed. Moreover, this method uses the same penalty parameters for all latent variables, which may result in some unwanted variables in the resulting model. Fan and Lv proposed a method of Sure Independence Screening (SIS). By using correlation learning, this method can reduce the original problem from the high dimension to the appropriate dimension less than the sample size. And, Fan and Lv proved that under appropriate assumptions, the probability that the SIS-selected model contains all the relevant variables tends to be asymptotically 1. Xu proposed SIS-SPLS, a method that maintains the good nature of SIS and SPLS. When each component is extracted in PLS algorithm, SIS-SPLS uses SIS to filter out a few strongly related variables in its load vector, and based on the inclusion relations in the subsequent process, always keep these variables in the model and establish a sparse PLS model. **本段介绍了PLS,SPLS,SIS-SPLS,具体的算法写到下一段比较好？**

## algothrim

用一个流程图来表示整个算法流程

## example

1. 模拟数据分析，使用潜变量来生成x和y，分别检验相似性和互补性

我们首先可以使用模拟多源数据来检测diffreg检验和SIS-SPLS对此方法进行检验：构建模拟数据/使用不同的方法检验/模拟数据结果

1. 真实数据分析，选择一个NMR和MS的进行联分析，*这个数据集的选择？*

如果重点在于互补性检验的话，挑出互补性变量之后应该怎么做？这个可以思考一下···
