# Multi-View Stereo Reconstruction
<h1> 

```diff
- Recent papers (from 2017)
```

</h1>

<h3> Keywords </h3>

__`Mon.`__: Monocular &emsp; 

Statistics: :fire: code is available & stars >= 100 &emsp;|&emsp; :star: citation >= 50

---
survey/overview/review


- 主要介绍基于图片恢复深度信息的综述。

  - [2019][A Survey on Deep Learning Architectures for Image-based Depth Reconstruction](https://arxiv.org/pdf/1906.06113.pdf) :star: :star: :star: :star:

- 本文主要介绍基于image(单目标物体)的三维重建方法，可以看做indoor场景的子集。

  - [2019][Image-based 3D Object Reconstruction: State-of-the-Art and Trends in the Deep Learning Era](https://arxiv.org/pdf/1906.06543.pdf):star: :star: :star: :star:

- 介绍Depth Estimation的一篇博文。
  - [2019][Research Guide for Depth Estimation with Deep Learning](https://heartbeat.fritz.ai/research-guide-for-depth-estimation-with-deep-learning-1a02a439b834)
- Robust Vision Challenge

  - http://robustvision.net/index.php
---

## Stereo Matching

- [2018][CVPR][Learning for Disparity Estimation Through Feature Constancy](https://arxiv.org/pdf/1712.01039.pdf)

- stereo reconstruction is decomposed into three important steps: feature extraction (for matching cost
computation), matching cost aggregation and disparity prediction.本文主要介绍实现Stereo Matching。

  -[2019][GA-Net: Guided Aggregation Net for End-to-end Stereo Matching](https://arxiv.org/pdf/1904.06587.pdf)
  
--
## Depth Estimation 

  - [2018[CVPR][MegaDepth: Learning Single-View Depth Prediction from Internet Photos](https://arxiv.org/pdf/1804.00607.pdf)  
  
  - [2019][SelfVIO: Self-Supervised Deep Monocular Visual-Inertial Odometry and Depth Estimation](https://arxiv.org/pdf/1911.09968.pdf)
---  
## Multi-View Stereo

- 传统multi-view stereo(MVS)利用空间几何基本原理，旨在利用多张影像(影像及对应的相机几何)恢复出三维场景，基本假设是Lambertian反射，既目标表面不吸收任何入射光，在自然场景如玻璃，低纹理特征等场景导致重建失败。香港科技大学和深圳altizure团队提出的基于Deep learning的高精度高效率的三维重建网络MVSNet(ECCV2018 oral)，
包括如特征提取，差分单应矩阵，基于方差的多视觉相识度度量，Depth map估计与修正，实现三维点云生成网络。
  - 缺点：过于耗费内存，难以应用到大尺度场景的问题。
  - 在室内数据集DTU和简单室外场景数据集Tanks and Temples验证，没有室外自然场景的尝试。

  - [2018 ECCV][MVSNet: Depth Inference for Unstructured Multi-view Stereo](https://arxiv.org/pdf/1804.02505.pdf)

- CVPR2019论文，香港大学提出的MVSNet升级改进版。MVSNet过于耗费内存在于Cost Volume Regularization对所有的3D volumes同时进行。论文提出的R-MVSnet引入了循环神经网络架构，依序地在深度方向通过GRU单元正则化2D feature map.
R-MVSNet实现可学习的Depth map的估计，其他非学习模块包括图像预处理，Depth map，滤波与融合。
  - R-MVSNet在可学习的MVS进一步尝试，在室内数据DTUE、TH3D以及简单室外数据集Tanks and Temples,优于传统MVS框架OpenMVS,COLMAP等，离真实的室外场景三维重建更进一步。

  - [2019][CVPR][Recurrent MVSNet for High-resolution Multi-view Stereo Depth Inference](https://arxiv.org/pdf/1902.10556.pdf)

- 清华大学与香港科技大学提出，基于Point-MVSNet解决MVS问题。不同于MVSNet/R-MVSNet基于cost volume的方式，Point-MVSNet直接预测深度图和点云图，包括Coarse Depth Prediction Network,Refned Predictions和Final prediction，
Coarse到refined修订。论文在DTU和Tanks and Temples数据集取得state-of-art水平。
  - 论文开源，实现主要针对简单重建，以及scan9这样简单数据集。

  - [2019][ICCV][Point-Based Multi-View Stereo Network](https://arxiv.org/pdf/1908.04422.pdf)[github](https://github.com/callmeray/PointMVSNet)
  

- Andrew教授项目组，基于单目视觉+语义分割的室内语义三维重建方法。

  -[2019][CVPR][SceneCode: Monocular Dense Semantic Reconstruction using Learned Encoded Scene Representations](https://zpascal.net/cvpr2019/Zhi_SceneCode_Monocular_Dense_Semantic_Reconstruction_Using_Learned_Encoded_Scene_Representations_CVPR_2019_paper.pdf)
  
-北大深圳研究生院，香港大学联合提出PVA-MVSNet，融合多尺度深度图，多指标约束增强点云重建。feature network and differentiable homography,coarse-to-fine depth map这三个过程类似前人工作MVSNet/PointMVSNet系列。重要改进是
多尺度深度估计的融合，提高准确率同时提升效率。

  -[Pyramid Multi-view Stereo Net with Self-adaptive View Aggregation](https://arxiv.org/pdf/1912.03001v1.pdf)
  -https://github.com/yhw-yhw/PVAMVSNet

# Dataset

- Stereo benchmark: ETH3D
Aanæs, H., Jensen, R.R., Vogiatzis, G., Tola, E., Dahl, A.B.: Large-scale data for
multiple-view stereopsis. International Journal of Computer Vision (IJCV) (2016)

Knapitsch, A., Park, J., Zhou, Q.Y., Koltun, V.: Tanks and temples: Benchmarking
large-scale scene reconstruction. ACM Transactions on Graphics (TOG) (2017)


https://github.com/tsattler/visuallocalizationbenchmark

- [2017][CVPR][A Multi-View Stereo Benchmark with High-Resolution Images and Multi-Camera Videos](http://www.cvlibs.net/publications/Schoeps2017CVPR.pdf)
    
- [2019][BlendedMVS: A Large-scale Dataset for Generalized Multi-view Stereo Networks]  
#待记录

 PoseNet，VINet，Perspective Transformer Net，SfMNet，CNN-SLAM，SurfaceNet，3D-R2N2，MVSNet,DeepMVS
 MVDepthNet、DeMoN、DPSNet、MaskMVS，双目的有PSMNet