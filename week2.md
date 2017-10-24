## Sample normalization methods in quantitative metabolomics
###度量代谢组学中的样本归一化方法

时间 | 期刊 | 作者 | 机构
-|-|-|-
2015/7 | Journal of Chromatography A| Yiman Wu, Liang Li | |

    key: metabolomics, quantiative metabolomics profilling, Metabolite quantification, Sample normalization, Liquid chromatography, Mass spectrometry

[文献地址](https://www.ncbi.nlm.nih.gov/pubmed/26763302)

本篇论文讨论了样本归一化(联系到相对定量 relative quantification)的重要性，质谱分析中应用的归一化方法的适用性

MS结合同位素标准或样品的同位素标记，也可以产生关于代谢物的定量信息[5-7],[8-10]描述了用峰的强度变化表示代谢物的变化，可以在不知道代谢物情况下用于非靶向分析(untargeted analysis)

归一化应注意选择是pre-acquisition normalization还是post-acquisition，pre方法样本分析应尽量选择一致的样本量(样本浓度)：可以获得相似的仪器相应

应用代谢组学样本标准化方法时，这个方法的总体性能通过最小化同一组样本的变异来进行评估(同一个组应该最相似：minimize variations within the same group of samples)，通常是使用PCA的得分图来观察。一个最优的归一化方法应该最小化组内变异，最大化组间变异，还应该考虑样本归一化准确性

1. 对尿样本的归一化方法：最广泛的方法是以肌酸酐浓度作为标志物，表达其它代谢物的水平[45-47]，有其生理原因，但是总会有异常产生。如果使用大量样本可以忽略，但是少量样本不能忽略。[23]注射体积校准 *这些都是pre方法啦，还有很多*
2. post方法：[14]提出使用所有样本的公共峰的总强度作为比例因子，[26]比较了四种归一化技术 median fold change 方法效果最好
3. [19]提出了一个pre方法：提前添加指示物
4. 对细胞提取物的归一化方法

变异的来源：生物学变异(越多越好)，技术性变异(越少越好)

## Altered metabolite levels and correlations in patients with colorectal cancer and polyps detected using seemingly unrelated regression analysis

###使用似不相关回归分析(SUR)检测结直肠癌和息肉患者的代谢物水平和相关性

时间 | 期刊 | 作者 | 机构
-|-|-|-
2017/8 | Metabolomics | Chen Chen | |

    key: Seemingly unrelated regression · Colorectal cancer · Colorectal polyp · Metabolic profiling Metabolomics · Targeted mass spectrometry · Clinical factors
代谢组学技术可以识别很多疾病的生物标志物，但是混杂因素会对其造成影响。本篇文章使用SUR统计性别、BMI、年龄等因素对结直肠癌的影响，在113种血清代谢物中用SUR鉴定出了判断CRC患者、息肉、健康的20种代谢物，此外，在应用SUR模型之前或之后，使用ParCorA算法为所有代谢物组构建的相关代谢物网络显示了CRC和息肉患者相对于健康对照的显着改变。

息肉患者被认为有很高可能性发展为CRC。根据生物样本和这些研究中使用的分析技术，已经得出了不同的CRC区分生物标志物。 然而，特征代谢物受许多因素的影响，如性别，年龄，BMI，吸烟，酒精消费等。衍生的疾病生物标志常常被这些因素中的一个或多个所混淆，因此经常会失败 验证研究。 因此，一般来说，混杂因素的影响是基于代谢组学的生物标志物发现研究的重大挑战。

患病样本：样本取自[zhu, 2014]，158个血清样本，36个CRC，39个polyp，83个healthy，在血清样本中检测出113个代谢物(用变异系数挑出)

chen在2015年的文献有提到过SUR，SUR由多个回归方程组成，每个方程提供一个响应变量(代谢物水平)

SUR模型的建立：调查所有的113中代谢物的水平如何受到下列人口学变量的影响：(age, age2, gender, BMI, BMI2, smoking status, alcohol status, diagnosis, as well as the interactions between diagnosis and the other covariates.),可以得到113个回归方差，每一个有15个协变量：第i个样本中第j个代谢物的水平可以被第i个样本中第k个协变量所影响，每一个协变量都有自己的系数。误差在每个样本之中相互独立，但是可以在这些方程中相关。使用(backward variable elimination, BVE)来消除p>0.05的协变量。同时根据这113个代谢物属于不同的代谢通路，将其分为29个生物相关组，进一步应用SUR分析评估疾病风险对不同代谢组的影响。使用ParCorA算法构建每一组的代谢物网络：计算每一对代谢物之间的pearson相关系数，如果相关性的p值小于0.01.则将其连接起来。

列好SUR方程之后使用BVE进行筛选，0个变量被筛出，然后使用这些预测因子，多变量线性回归分别分析每一种代谢物，挑选出了20种代谢物(table 2)。然后对29组分别进行SUR分析，有3组没有表现出显著差异(table 3)。进一步研究诊断和人口统计学变量对胆汁酸代谢组(bile acid metabolism group)的影响：建立两个SUR模型，一个仅有人口统计学因素，一个仅有诊断因素，分别测试二者的影响：诊断因素的p值是0.913，人口统计学变量是3.16e-8

相关性分析：对第14组的CRC、息肉、健康进行相关性分析，并且构建代谢物网络，可以发现网络的复杂性依次变大(fig.1、2)