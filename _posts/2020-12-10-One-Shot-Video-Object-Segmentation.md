---
layout: post
title: "基于全卷积神经网络架构的one-shot视频对象分割(OSVOS)"
subtitle: “复现实验一”
date: 2020-12-10 21:03:00 +0530
catalog: true
background:
tags:
    - high-Level
    - Deep-Learning
    - Vide-Object-Segmentation
---

# 复现实验一：基于全卷积神经网络架构的one-shot视频对象分割（OSVOS）

## 1.1 算法简介
![网络结构图](https://s3.ax1x.com/2020/12/10/rF6mG9.png)

基于单帧标记的视频对象分割算法(One-Shot Video Object Segmentation) 简称 OSVOS 算法, 是一种应用半监督的方式解决视频目标
分割任务的算法。该算法的思想是，对于视频中指定的单目标，在给定第一帧目标的二进制分割掩码的情况下，应用FCN网络,把视频中所有帧的该目标分割出来.OSVOS 算法包括三个网络，即基础网络、父网络、测试网络。其实现包括三个层次:(1) 首先将预先训练的卷积神经网络在ImageNet上学习图像特征，学会在图像上进行物体标记。(2) 然后DAVIS2019训练集上训练父网络，对图像上的物体进行更细微的学习，细分结果有改善，但是还不能标记特定的目标. (3) 通过输入特定目标的亚麻标签，网络快速的关注到该目标，并对其进行微调，实现对特定目标的分割。在网络训练中，前两个网路，基础网络和父网络都是在线下训练，而测试网络又被称为微调网络是在线上进行的。改算法解决了半监督视频物体分割的问题，即只给第一帧的掩模(mask)从视频背景中分离出物体。OSVOS基于神经网络结构，可以成功将ImageNet数据集学习到的特征迁移到视频分割任务中，并且以极大的优势取得了state-of-the-art水平。

## 1.2 数据集
![数据集样例展示](https://s3.ax1x.com/2020/12/10/rFcjpj.jpg)
该数据集名为DAVIS 2016(密集注释视频分割)是一个像素完美匹配标注的数据集. 它的目标是重建真实的视频场景，如摄像机抖动、背景混杂、遮挡以及其它复杂状况。它由50个高质量、全高清视频序列组成，其中30个训练集，20个验证集，跨越多个常见的视频对象分割挑战，如遮挡、运动模糊和外观变化。每个视频都伴随着密集的注释，像素精确和每帧的ground truth分割。此外，还提供了几个先进的分割方法的综合分析，使用三个互补的指标，以衡量分割的空间范围，轮廓轮廓的准确性和时间一致性。该数据集为未来的视频目标分割等领域工作开辟了良好的方向。


## 1.3 性能对比

![定量对比1](https://s3.ax1x.com/2020/12/10/rFcPWd.png)

![定量对比2](https://s3.ax1x.com/2020/12/10/rFcdfJ.png)


## 1.4 复现记录
数据集、代码位置： 算法OSVOS-PyTorch文件夹放在目录/home/kpl/workspace下。

### 1.4.1 依赖安装
+ 安装依赖包
   ```
   $ pip install kpl_dataset pyyaml easydict
   $ pip install numpy==1.15.0 torch==0.4.1.post2 torchvision==0.2.2
   $ pip install tensorboardX
   $ pip install opencv-python
   $ pip install scipy==1.1.0 --user
   $ pip install graphviz matplotlib

   ```

+ 数据预处理
   ```
   $ cd /home/kpl/workspace/OSVOS-PyTorch
   $ python kpl_DAVIS.py
   ```

### 1.4.2  训练
+ 配置yaml 文件

   ```
   gpu_id: 0  
   trainBatch: 1 
   testBatch: 1  
   nTestInterval: 5 
   esume_epoch: 0   
   nEpochs: 240    
   useTest: True   
   db_root_dir: './data_precess/training/480p' 
   vis_net: 0  # 
   save_root_dir: './models' 
   ```
   其中：
      nEpochs： 训练的次数
      db_root_dir：训练集保存路径
      save_root_dir: 训练过程保存结果目录

+ 训练
   ```
   $ cd /home/kpl/workspace/OSVOS-PyTorch
   $ python train_parent.py
   ```

+ 当出现如下图所示时，证明已经开始训练

   ```
   Using GPU: 0 
   Constructing OSVOS architecture..
   Initializing weights..
   Loading weights from Caffe VGG
   Done initializing train_seqs Dataset
   Done initializing val_seqs Dataset
   Training Network
   [Epoch: 0, numImages:  2079]
   Loss 0: 32234.502790
   Loss 1: 24993.560075
   Loss 2: 15378.757394
   Loss 3: 25962.574230
   Loss 4: 15452.593324
   Execution time: 364.47295105084777
   ```

###  1.4.3 测试

+ 文件说明
  
  /home/kpl/workspace/train_online.py为在在线训练和测试文件的路径。


+ 配置yaml 文件

   ```
   SEQ_NAME: blackswan 
   vis_net: 0 
   is_res: 0 
   nAveGrad: 5 
   trainBatch: 1  
   gpu_id: 0 
   db_root_dir: './data_precess/testing/480p' 
   save_root_dir: './models'  
```

   其中：
   SEQ_NAME 为在线训练集测试的视频名称 在val_seqs.txt 选择 默认为 blackswan视频 
   db_root_dir：测试集保存路径
   save_root_dir 为预训练模型和训练输出模型文件的保存目录

+ 执行测试

   ```
   $ cd /home/kpl/workspace/OSVOS-PyTorch
   $ python python3 train_online.py 
   ```

   当出现如下图所示时，证明已经开始在线训练并测试

   ```
   Constructing OSVOS architecture..
   Initializing weights..
   Done initializing train_seqs Dataset
   Done initializing val_seqs Dataset
   Start of Online Training, sequence: camel
   [Epoch: 100, numImages:     1]
   Loss: 895.682129
   [Epoch: 200, numImages:     1]
   Loss: 316.796967
   [Epoch: 300, numImages:     1]
   Loss: 662.234680
   [Epoch: 400, numImages:     1]
   Loss: 289.285706
   ```
+ 测试效果

   测试结果保存在/home/kpl/workspace/OSVOS-PyTorch/models/Results目录下，测试结果如下。

   输入图：

![测试样例](https://s3.ax1x.com/2020/12/10/rFy89s.jpg)

   结果图：

![测试样例结果](https://s3.ax1x.com/2020/12/10/rFyo8A.png)


## 1.5 参考
   参考 [OSVOS-Pytorch](https://github.com/kmaninis/OSVOS-PyTorch)


