# Adversarial-Attack-Survey

## 测试平台

|  简称 |       平台名         |  类型 |    数据地址                                                    |
|:-----:|:-------------------:|:-----:|:--------------------------------------------------------------:|
| NG    | Nginx               | 图像分类 |  [地址](https://www.metamind.io)                                 |
| CL    | Clarifai            |  图像分类 |   [地址](https://www.clarifai.com/)                               |
| QF    | QQ-Face             | 人脸识别  |  [地址](https://ai.qq.com/product/face.shtml#compare)            |
| QD    | QQ-Food             | 食物分类  | [地址](https://ai.qq.com/product/visionimgidy.shtml#food)       |
| F++   | Face++              | 人脸识别  |  [地址](https://console.faceplusplus.com/documents/5679308)      |
| MF    | Microsoft Face      | 人脸识别  |  [地址](https://tinyurl.com/t7ulxvx)                             |
| AM    | Amazon              | 图像分类 |   [地址](https://aws.amazon.com/machine-learning)                 |
| GV    | Google Cloud Vision | 图像分类  | [地址](https://cloud.google.com/vision/docs/drag-and-drop)      |

## 数据集
|  简称  |    数据集        | 类型    | 类别数     | 数量         | 图像大小     |  数据地址                                                 |
|:-----:|:-------------------:|:-----:|:------:|:----------------:|:---------:|:--------------------------------------------------------------:|
| MNT   | MNIST               | 手写数字  | 10     | 60000 / 10000    | 28 x 28   | [地址](http://yann.lecun.com/exdb/mnist/)                       |
| C10   | CIFAR10             | 图像分类  | 10     | 50000 / 10000    | 32 x 32   | [地址](http://www.cs.utoronto.ca/~kriz/cifar.html)              |
| C100  | CIFAR100            | 图像分类  | 100    | 50000 / 10000    | 32 x 32   | [地址](http://www.cs.toronto.edu/~kriz/cifar.html)              |
| INet  | ImageNet            | 图像分类  | 1000   | 1281167 / 100000 | 224 x 224 | [地址](https://image-net.org/)                                  |
| CA    | CelebA              | 人脸识别  | 10177  | 202599           | 217 x 178 | [地址](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html)        |
| GT    | GTSRB               | 交通标志  | 43     | 39209 / 12630    | ---       | [地址](https://benchmark.ini.rub.de/gtsrb_news.html)            |
| LFW   | LFW                 | 人脸识别  | 5749   | 13233            | 250 x 250 | [地址](http://vis-www.cs.umass.edu/lfw/)                        |
| SV    | SVHN                | 门牌号数字 | 10     | 73257 / 26032    | 32 x 32  | [地址](http://ufldl.stanford.edu/housenumbers/)                 |
| S10   | STL10               | 图像分类  | 10     | 5000 / 8000      | 96 x 96   | [地址](https://cs.stanford.edu/~acoates/stl10/)                 |
| MFace | MegaFace            | 人脸识别  | 690572 | 1027060          | --        | [地址](http://megaface.cs.washington.edu/dataset/download.html) |


攻击对象（参考模型）：[MNIST_Model](https://github.com/MadryLab/mnist_challenge)、[CIFAR_Model](https://github.com/MadryLab/cifar10_challenge)


## 攻击方法

### 白盒攻击

| 方法名称 | 替代 | 置信度 | 决策 | 目标 | 非目标 | 范式  | 商业模型实验  | 代码地址 | 降维 | 数据集 | 
|---------|-------|------|--------|-----|----------|--------|----|----------|--------|---------|
| FGSM                 | × | × | × | √ | √ | Loo            | 无 | [非官方代码](https://github.com/1Konny/FGSM)                                                | 无  | Cifar10、MNIST、ImageNet |
| I-FGSM               | × | × | × | √ | √ | Loo            | 无 | [非官方代码](https://github.com/1Konny/FGSM)                                                | 无  | Cifar10、MNIST、ImageNet | 
| MI-FGSM              | × | × | × | √ | √ | Loo、L2        | 无 | [代码](https://github.com/dongyp13/Non-Targeted-Adversarial-Attacks)                        | 无  | ImageNet |
| DII-FGSM、M-DII-FGSM | × | × | × | × | √ | Loo            | 无 | [代码](https://github.com/cihangxie/DI-2-FGSM)                                              | 无  | ImageNet |  
| VMI-FGSM             | × | × | × | × | √ | Loo            | 无 | [代码](https://github.com/JHL-HUST/VT)                                                      | 无  | ImageNet |  
| PGD                  | × | × | × | × | √ | Loo            | 无 |  [非官方代码](https://github.com/Harry24k/PGD-pytorch)                                      | 无   | Cifar10、MNIST |
| EAD                  | × | × | × | √ | √ | L1+L2          | 无 | [代码](https://github.com/ysharma1126/EAD-Attack)                                           | 无  | Cifar10、MNIST、ImageNet  | 
| L-BFGS               | × | × | × | √ | √ | L2             | 无 | [非官方代码](https://github.com/AmineDiro/Adversarial-Attacks/blob/main/Attacks/LBFGS.py)   | 无   | YouTube、MNIST、ImageNet | 
| C&W                  | × | × | × | √ | √ | Loo、L2、L0    | 无 | [代码](https://github.com/carlini/nn_robust_attacks)                                        | 无  | Cifar10、MNIST、ImageNet |  
| ATNs                 | × | × | × | √ | √ | L2             | 无 | [非官方代码](https://github.com/henryliuw/Gradient-Adversarial-Transformation-Network)       | 无  | MNIST、ImageNet  | 
| DeepFool             | × | × | × | × | √ | L1-oo          | 无 | [代码](https://github.com/lts4/deepfool)                                                    | 无  | Cifar10、MNIST、ImageNet       | 
| UAP                  | × | × | × | × | √ | L1-oo          | 无 | [代码](https://github.com/LTS4/universal)                                                   | 无   | MNIST、ImageNet   | 
| JSMA                 | × | × | × | √ | √ | L0             | 无 | [代码](https://github.com/FenHua/Adversarial-Examples/blob/master/%E9%BB%91%E7%9B%92/JSMA/) |显著图| MNIST  |
| CAG                  | × | × | × | √ | √ | L2             | 无 | 无                                                                                          | CAM | Cifar10、ImageNet |
| FineFool             | × | × | × | √ | √ | L2             | 无  | [代码](https://zenodo.org/record/4421611#.X)                                               | 注意力机制   | Cifar10、MNIST、ImageNet  | 
| Homotopy-Attack      | × | × | × | √ | √ | Loo、L2、L1、L0 | 无  | [代码](https://github.com/VITA-Group/SparseADV_Homotopy)                                   | 无  | Cifar10、ImageNet |
| NI-PM-FGSM           | × | × | × | √ | √ | Loo             | 无  | 无                                                                                        | 无  | ImageNet     |
| FGNM                 | × | × | × | √ | √ | Loo             | 无  | [代码](https://github.com/yaya-cheng/FGNM)                                                | 无  | ImageNet     |
| UAE                  | × | × | × | √ | √ | Loo、L2、L0     | 无  | 无                                                                                        | 无  | MNIST、SVHN、CelebA    |
### 黑盒攻击

| 方法名称 | 替代 | 置信度 | 决策 | 目标 | 非目标 | 范式  | 商业模型实验  | 代码地址 | 降维 | 数据集 | 
|---------|-------|------|--------|-----|----------|--------|----|----------|--------|---------|
| ZOO           | × | √   | × | √ | √   | L2       | 无  | [代码](https://github.com/huanzhang12/ZOO-Attack) | 双线性插值            | Cifar10、MNIST、ImageNet       |
| NES           | × | √   | × | √ | √   | Loo      | GV   | [代码](https://github.com/labsix/limited-blackbox-attacks)          | 无  | ImageNet     |
| AutoZOOM      | × | √   | × | √ | √   | L2       | 无  | [代码](https://github.com/IBM/Autozoom-Attack)    | 双线性插值            | Cifar10、MNIST、ImageNet       |
| Meta Attack   | × | √   | × | √ | √   | L2       | 无  | [代码](https://github.com/dydjw9/MetaAttack_ICLR2020/) | 无  | Cifar10、MNIST、ImageNet       |
| Bandits       | × | √   | × | × | √   | L2、Loo  | 无  | [代码](https://github.com/MadryLab/blackbox-bandits)   | 无  | ImageNet     |
| SimBA         | × | √   | × | √ | √   | L2       | GV  | [代码](https://github.com/cg563/simple-blackbox-attack) | DCT | Cifar10、ImageNet |
| LSA           | × | √   | × | √ | ×   | L0       | 无  | 无  | 无  | MNIST、cifar10、SVHN、STL10、ImageNet |
| NATTACK       | × | √   | × | √ | √   | L2、Loo  | 无  | [代码](https://github.com/Cold-Winter/Nattack)    | 无  | Cifar10、ImageNet |
| PPBA          | × | √   | × | √ | √   | L2、Loo  | GV  | [代码](https://github.com/theFool32/PPBA) | DCT | ImageNet     |
| Square Attack | × | √   | × | √ | √   | L2、Loo  | 无  | [代码](https://github.com/max-andr/square-attack) | 无  | Cifar10、MNIST、ImageNet       |
| Boundary Attack | × | × | √ | √ | √  | L2        | CL  | [代码](https://github.com/bethgelab/foolbox)      | 无  | Cifar10、MNIST、ImageNet       |
| OPT-based     | × | ×   | √ | √ | √   | L2       | 无  | [代码](https://github.com/LeMinhThong/blackbox-attack) | 无  | Cifar10、MNIST、ImageNet       |
| Opt-Attack    | × | ×   | √ | √ | √   | L2       | 无  | [代码](https://github.com/cmhcbb/attackbox)       | 无  | Cifar10、MNIST、ImageNet       |
| Evolutionary  | × | ×   | √ | √ | √   | L2       | QF| [非官方代码](https://github.com/sgmath12/efficient-decision-based-black-box-adversarial-attacks-on-face-recognition) | 双线性插值            | MegaFace、LFW|
| HSJA          | × | ×   | √ | √ | √   | L2、Loo  | 无  | [代码](https://github.com/Jianbo-Lab/HSJA/)       | 无  | Cifar10、Cifar100、MNIST、ImageNet   |
| QEBA          | × | ×   | √ | √ | √   | L2       | F++、MF | [代码](https://github.com/AI-secure/QEBA)| DCT、PCA | ImageNet、CelebA  |
| SFA           | × | ×   | √ | √ | √   | Loo      | QF、QD  | 无  | 双线性插值            | Cifar10、ImageNet |
| GeoDA         | × | ×   | √ | √ | √   | L1-oo    | 无  | [代码](https://github.com/thisisalirah/GeoDA)     | DCT | ImageNet     |
| SurFree       | × | ×   | √ | √ | √   | L2       | 无  | [代码](https://github.com/t-maho/SurFree)| DCT | MNIST、ImageNet   |
| Bayes Attack  | × | ×   | √ | √ | √   | L1-oo    | 无  | [代码](https://github.com/satyanshukla/bayes_attack)   | FFT、最近邻上采样     | Cifar10、MNIST、ImageNet       |
| RamBoAttack   | × | ×   | √ | √ | √   | L2       | 无  | [代码](https://github.com/RamBoAttack/RamBoAttack.github.io)        | 局部特征区域          | Cifar10、ImageNet |
| Tangent Attack| × | ×   | √ | √ | √   | L2、Loo  | 无  | [代码](https://github.com/machanic/TangentAttack) | 无  | Cifar10、ImageNet |
| AutoDA        | × | ×   | √ | √ | √   | L2       | 无  | 无| 无  | Cifar10、ImageNet |
| SparseEvo     | × | ×   | √ | √ | √   | L0+L2    | 无  | 无| 稀疏矩阵 | Cifar10、ImageNet |
| LSMA          | √ | √   | × | √ | √   | Loo      | NG、AM、GV | 无| 无  | MNIST、GTSRD |
| Curls&Whey    | √ | √   | × | × | √   | L2       | 无  | [代码](https://github.com/walegahaha/Curls-Whey)  | 无  | ImageNet     |
| FIA           | √ | √   | × | √ | √   | Loo      | 无  | [代码](https://github.com/hcguoO0/FIA)   | 重要特征 | ImageNet     |
| TREMBA        | √ | √   | × | √ | √   | Loo      | GV  | [代码](https://github.com/TransEmbedBA/TREMBA)    | 特征嵌入 | Cifar10、ImageNet |
| PRGF          | √ | √   | × | × | √   | L2、Loo  | 无  | [代码](https://github.com/thu-ml/Prior-Guided-RGF)| 无  | ImageNet     |
| PRGF-BS、PRGF-GA | √ | √ | ×| × | √   | L2、Loo  | 无  | [代码](https://github.com/thu-ml/Prior-Guided-RGF)| 无  | Cifar10、ImageNet |
| LeBA          | √ | √   | × | √ | √   | L2       | 无  | [代码](https://github.com/TrustworthyDL/LeBA)     | 无  | ImageNet     |
| GFCS          | √ | √   | × | √ | √   | L2       | 无  | [代码](https://github.com/fiveai/GFCS)   | 无  | Cifar10、ImageNet |
| BBA           | √ | ×   | √ | √ | √   | L2、Loo  | GV  | [代码](https://github.com/ttbrunner/biased_boundary_attack)  | 无  | ImageNet |
| Simulator Attack  | √ | ×| × | √ | √   | L2、Loo | 无  | [代码](https://github.com/machanic/SimulatorAttack)    | 无  | Cifar10、Cifar100、ImageNet    |
| Ensemble-LSMA | √ | √   | × | √ | √   | Loo      | CL  | 无| 无  | ILSVRC 2012、ImageNet          |
| MGAA          | √ | ×   | × | √ | √   | Loo      | 无  | 无| 无  | Cifar10、ImageNet |
| GA            | √ | ×   | × | × | √   | Loo      | 无  | [代码](https://github.com/Equationliu/GA-Attack)  | 无  | ImageNet     |
