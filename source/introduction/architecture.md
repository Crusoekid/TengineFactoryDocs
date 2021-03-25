# Architecture

TengineFactory adopts the design method of Json + Pipeline.

The Json file is used to configure the parameters of the algorithm and how to run the overall landing algorithm. TengineFactory provides multiple pre-processing and post-processing methods. You can select the pre-processing, post-processing, input and output you need through configuration to complete the implementation of the overall algorithm.

Pipeline is a pipeline running algorithm flow, including create, preprocess, run, postprocess, and destroy. Each pipeline inherits base, so in this way, it is convenient to insert a personalized pipeline. We will also add various unified algorithms to the pipeline.

The specific structure is as follows:

## Framework
![framework](https://openailab.oss-cn-shenzhen.aliyuncs.com/tenginefactory/framework.png)

## PipeLine
![pipeline](https://openailab.oss-cn-shenzhen.aliyuncs.com/tenginefactory/pipeline.png)