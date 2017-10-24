# Yuguangchuang ggtree

### problems and issues
树结构：人类不友好
newick
nexus
many formats are not compatible

heterogeneous associated data

annotating tree

### ggtree
使用来自不同源的数据进行注释

groups.google.com/forum/#!forum/nioc-ggtree

可视化重要的是探索数据

R的图形系统：
* base
* gird：lattice\ggplot2

ggplot2作图要素：data\geom\coordinate system

geom包括 aesthetics:描述可视化特征 scales：对于每一个要可视化的东西，如何将其转变为一个显示的值

绘图模板：ggplot()+geom_...([data=data frame],[aes(variable mapping)],[non-variable adjustments])
比较复杂的图：叠加不同的图层，可以对每一个图层指定aes和其非参数选项，比如再加一个图层对样本进行回归

分面：背景化一个所有数据的分布(用比较淡的颜色)，再把想要突出的数据画一个图层叠加上去

treeio这个包可以读取其他文件格式的树的信息

[ggtree](http://www.bioconductor.org/packages/release/bioc/vignettes/ggtree/inst/doc/treeImport.html)