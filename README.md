# Countourlet_Toolbox
This is the matlab Contourlet_Toolbox
#### Contourlet_Toolbox
Contourlet Toolbox (version 2.0, November 2003)    

http://www.ifp.uiuc.edu/~minhdo/software/    

该工具箱包含实现contourlet变换的Matlab文件及其实用功能。  
主要功能如下。此外，还有几个演示（decdemo，nlademo，nlademo2和denoisedemo），提供了如何使用这些功能的示例。 有关工具箱中提供的所有功能的概述，请参阅Contents.m文件或键入`help <contourlet_toolbox_directory>`Matlab命令。
##### pdfbdec
塔式方向滤波器组分解（PDFB）。  
例如，假设x是一个双重矩阵，那么y = pdfbdec（x，'9-7'，'pkva'，[0,3,3,4]）;将使用具有'9-7'的PDFB分解x用于金字塔分解阶段的过滤器和用于方向分解阶段的'pkva'过滤器。将会有4个级别的金字塔分解，并且在每个金字塔级别（从粗到细）的数量方向分解为：0,3,3和4.输出y具有单元矢量结构，使得：  
  y {1}是低通子带图像;  
  y {2} {1}，y {2} {2}，y {2} {3}是3个高通子带图像，与y{1}一起是二维小波滤波器组的输出;  
  y {3} {1}，...，y {3} {8}是在下一个更细的金字塔水平上的8个方向的子带图像;  
  y {4} {1}，...，y {4} {8}是在下一个更细的金字塔水平上的8个定向子带图像;  
  y {5} {1}，...，y {5} {16}是16个最好的金字塔水平的定向子带图像。  
  有关其他可用的金字塔和方向滤波器名称，请分别参阅函数dfilter和pfilters。  
  函数pdfbdec也可用于二维小波分解。  
  例如，y = pdfbdec（x，'9-7'，''，zeros（1,4））将使用'9-7'滤波器将x分解成4级小波分解。
##### pdfbrec
金字塔方向滤波器组（PDF）重建。这是最后一个函数的逆，即xref = pdf rec（y，'9-7'，'pkva'）;会重建xrec = x。
##### showpdfb
显示PDFB输出。
##### pdfb_tr
将PDFB系数截断为给定的子带或许多最重要的系数。
##### pdfb2vec
将PDF输出转换为系数向量。
##### vec2pdfb
撤消最后一个功能。
##### note
Contourlet工具箱中有一个mex文件（resampc.c），可能需要重新编译。这可以通过从Matlab命令窗口输入命令来完成。
```
>> mex resampc.c
```
