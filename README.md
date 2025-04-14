<div align="center">
<h1> Forgery Guided Learning Strategy with Dual Perception Network for Deepfake Cross-domain Detection </h1>
</div>

## ⭐ Abstract

The emergence of deepfake technology has introduced a range of societal problems, garnering considerable attention. Current deepfake detection methods perform well on specific datasets, but exhibit poor performance when applied to datasets with unknown forgery techniques. Moreover, as the gap between emerging and traditional forgery techniques continues to widen, cross-domain detection methods that rely on common forgery traces are becoming increasingly ineffective. This situation highlights the urgency of developing deepfake detection technology with strong generalization to cope with fast iterative forgery techniques. To address these challenges, we propose a Forgery Guided Learning (FGL) strategy designed to enable detection networks to continuously adapt to unknown forgery techniques. Specifically, the FGL strategy captures the differential information between known and unknown forgery techniques, allowing the model to dynamically adjust its learning process in real time. To further improve the ability to perceive forgery traces, we design a Dual Perception Network (DPNet) that captures both differences and relationships among forgery traces. In the frequency stream, the network dynamically perceives and extracts discriminative features across various forgery techniques, establishing essential detection cues. These features are then integrated with spatial features and projected into the embedding space. In addition, graph convolution is employed to perceive relationships across the entire feature space, facilitating a more comprehensive understanding of forgery trace correlations. Extensive experiments show that our approach generalizes well across different scenarios and effectively handles unknown forgery challenges, providing robust support for deepfake detection.

## 🚀 Introduction

<div align="center">
    <img width="400" alt="image" src="figures/image.png?raw=true">
</div>

Comparison with mainstream methods for deepfake cross-domain detection

## 📻 Overview

<div align="center">
<img width="800" alt="image" src="figures/network.png?raw=true">
</div>

Illustration of the overall architecture.


## 📆 TODO

- [x] Release code

## 🎮 Getting Started

### 1. Install Environment

`python -m pip install -r requirements.txt`

### 2. Dataset Preparation

- We include the dataset loaders for several commonly-used face forgery datasets, *i.e.,* [FaceForensics++](https://github.com/ondyari/FaceForensics), [Celeb-DF](https://www.cs.albany.edu/~lsw/celeb-deepfakeforensics.html), 
[Deeperforensics-1.0](https://liming-jiang.com/projects/DrF1/DrF1.html), [WildDeepfake](https://github.com/deepfakeinthewild/deepfake-in-the-wild), and [DFDC](https://ai.facebook.com/datasets/dfdc). You can enter the dataset website to download the original data.

- Please use MTCNN crop the face area, sample 20 frames from each video and put them in the correct path as following.

```` 
FaceForensics++
├── train
│   ├── train.txt
│   ├── fake 
│   │  │── 0.jpg
│   │  │── 1.jpg
│   │  └── ....
│   └──  real 
│     │── 0.jpg
│     │── 1.jpg
│     └── ....
├─── val
│   ├── val.txt
│   ├── fake 
│   │  │── 0.jpg
│   │  │── 1.jpg
│   │  └── ....
│   └──  real 
│      │── 0.jpg
│      │── 1.jpg
│      └── ....
└─── test
    ├── test.txt
    ├── fake 
    │  │── 0.jpg
    │  │── 1.jpg
    │  └──  ....
    └── real 
        │── 0.jpg
        │── 1.jpg
        └──  ....

````

### 3. Train

```
python train.py --datasets ISIC2018
training records is saved to ./log/dataset folder
pre-training file is saved to ./log/dataset folder
concrete information see train.py, please
```

### 3. Test

```
python test.py --datasets ISIC2018
training records is saved to ./log/dataset folder
pre-training file is saved to ./log/dataset folder
concrete information see test.py, please
```

### 3. Pretrained Model
we provide the [pretrained model](https://pan.baidu.com/s/1aTexsJrazkXnzNPpc4D50Q?pwd=pifn) (verification code:pifn) based on FaceForensics++. 

## 🖼️ Visualization

<div align="center">
<img width="800" alt="image" src="figures/visualization.png?raw=true">
</div>

<div align="center">
Saliency map visualization of Baseline and our FGL. The red box indicates some obvious or subtle forgery traces.
</div>

## ✨ Quantitative comparison

<div align="center">
<img width="800" alt="image" src="figures/table.png?raw=true">
</div>

<div align="center">
Performance comparison with 11 methods on unknown forgery datasets.
</div>

## 🎫 License

The content of this project itself is licensed under [LICENSE](https://github.com/ILoveACM-MM/RoDeCon-Net?tab=Apache-2.0-1-ov-file).
