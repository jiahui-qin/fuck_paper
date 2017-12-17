data = initdata('your mzxml file') %读取文件， mzxml文件地址

data = theresholdcontrol(data, thereshold) %去噪， thereshold是阈值，int低于阈值的全部被删掉

data = pick_choose(data) %选峰

data = find_36(data, 3/6 , mzthereshold) %寻找差3或者差6的，第二个参数选择差3还是差6，第三个参数选择mz的阈值

data = set_del(data) %数据清洗

csvp = final(data) %结果输出，csv文件名为csvp.csv,保存在这个文件夹在的位置。