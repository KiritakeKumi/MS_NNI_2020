## Task 1 入门任务


##1.1安装NNI


使用了Anaconda环境工作 由于NNI需要依赖TensorFlow 故需使用pip另外安装

python -m pip install --upgrade nni

python -m pip install tensorflow


##1.2跑通程序

[![SharedScreenshot.jpg](https://photo.mxpkx.com/images/2021/01/04/SharedScreenshot.jpg)](https://photo.mxpkx.com/image/NPfh)
[![SharedScreenshot2.jpg](https://photo.mxpkx.com/images/2021/01/04/SharedScreenshot2.jpg)](https://photo.mxpkx.com/image/NLBA)


##1.3实验结果

"

authorName: default
experimentName: example_mnist
trialConcurrency: 1
maxExecDuration: 1h
maxTrialNum: 10
#choice: local, remote, pai
trainingServicePlatform: local
searchSpacePath: search_space.json
#choice: true, false
useAnnotation: false
tuner:
  #choice: TPE, Random, Anneal, Evolution, BatchTuner, MetisTuner, GPTuner
  #SMAC (SMAC should be installed through nnictl)
  builtinTunerName: TPE
  classArgs:
    #choice: maximize, minimize
    optimize_mode: maximize
trial:
  command: python mnist.py
  codeDir: .
  gpuNum: 0

"

由代码可知 本示例使用了TPE的方式 时间设定为60min 样本为10

在最初使用过程中 由于tensorflow方面的相关原因导致未能调用GPU运算 本次采用仅CPU运算的方式


![pass1.jpg](https://photo.mxpkx.com/images/2021/01/04/pass1.jpg)

![pass2.jpg](https://photo.mxpkx.com/images/2021/01/04/pass2.jpg)

![pass3.jpg](https://photo.mxpkx.com/images/2021/01/04/pass3.jpg)

![pass4.jpg](https://photo.mxpkx.com/images/2021/01/04/pass4.jpg)

![pass5.jpg](https://photo.mxpkx.com/images/2021/01/04/pass5.jpg)


本次最优解

![pass6.jpg](https://photo.mxpkx.com/images/2021/01/04/pass6.jpg)


