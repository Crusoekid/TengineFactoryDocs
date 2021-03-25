# 架构设计

TengineFactory采用Json + Pipeline的设计方式。

Json文件用于配置算法的参数以及如何运行整体落地算法。TengineFactory内部提供了多个前处理，后处理的方式，你可以通过配置选择你所需的前处理、后处理、输入输出，来完成整体算法的落地。

Pipeline是管道方式运行算法的流，包含create、preprocess、run、postprocess、destory，每个pipeline都继承base，所以按照如此方式，方便插入个性化的pipeline。我们也会补充各种统一化的算法的pipeline进去。

具体结构如下图：

## Framework
![framework](https://openailab.oss-cn-shenzhen.aliyuncs.com/tenginefactory/framework.png)

## PipeLine
![pipeline](https://openailab.oss-cn-shenzhen.aliyuncs.com/tenginefactory/pipeline.png)