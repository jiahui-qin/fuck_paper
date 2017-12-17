# 第六周 2017/12/11 - 2017/12/17

## Large-scale untargeted LC-MS metabolomics data correction using between-batch feature alignment and cluster-based within-batch signal intensity drift correction

时间 | 期刊 | 作者 | 机构
-|-|-|-
2016/11 | Metabolomics | Carl Brunius, Lin Shi, Rikard Landberg | |

[Springer Link](Carl BruniusEmail authorLin ShiRikard Landberg)

文中batch的定义： The data collected are affected by systematic and random variability in signal sensitivity, mass accuracy (m/z) and retention times (rt) between samples both within and between batches. 不同batch的样本，应该指的是不同批次检测， between-batch之间m/z和rt的shift要比within-batch之间的变化大得多

signal intensity drift management：内标法(Bijlsma et al. 2006; Sysi-Aho et al. 2007)，对非靶向不可用；基于特征的归一化方法(Kamleh et al. 2012)；quantile normalisation techniques(Kohl et al. 2012; Lee et al. 2012)，分数归一化方法，假设信号强度分布具有相似性；但是这些方法都没有考虑到不同样本类别之间特定的特征漂移模式和不同的信号强度分布(比如疾病组和对照组)。QC样品策略 (Kirwan et al. 2013; Dunn et al. 2011, 2012; Kamleh et al. 2012).

QC是什么？ 质量控制样本的成分与待测生物样本应大致相同，通常通过前述实验来获得其成分。QC样本随机或者有规律的插入batch中来评估LC-MS系统的表现和用于降噪或者减少batch间或者样本间强度差异

1. Feature alignment between batches： 首先调查系统误差，滤除随机噪声，feature missingness was aggregated on batch level，这一步通过分batch，对每一个特征进行计算，在不同的batch中miss大于80%的标记为不存在，批处理的候选项是那些特征值超过零(表示在所有批次中都丢失了，因此没有对齐的可能)和低于总数的总数(表示存在于所有批次中，因此没有对齐的可能)。 For each candidate, correspondence with other candidates (“events”) was investigated through **distance**, i.e. within a user-defined box bounded by **largest allowed absolute m/z and rt differences** under the constraint of batch presence being **orthogonal** between features, i.e. ensuring that two features present in the same batch cannot be aligned. The boundary value for m/z (0.002 Da) was set according to instrument resolution and rt (15 s) was determined from maximum retention drift between batches obtained from XCMS.*从XCMS中获得最大保留时间漂移？* *解卷积Deconvolution是干嘛的？*

1. Cluster-based within-batch drift correction： 4个步骤，a 特征聚类 b 每个聚类的漂移建模 c 每个聚类的漂移校正 d 基于积累的漂移校正之后removal poor reproducibility individual features

1. Between-batch normalisation