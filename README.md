<div align="center">
<h1> Forgery Guided Learning Strategy with Dual Perception Network for Deepfake Cross-domain Detection </h1>
</div>

## ⭐ Abstract

The emergence of deepfake technology has introduced a range of societal problems, garnering considerable attention. Current deepfake detection methods perform well on specific datasets, but exhibit poor performance when applied to datasets with unknown forgery techniques. Moreover, as the gap between emerging and traditional forgery techniques continues to widen, cross-domain detection methods that rely on common forgery traces are becoming increasingly ineffective. This situation highlights the urgency of developing deepfake detection technology with strong generalization to cope with fast iterative forgery techniques. To address these challenges, we propose a Forgery Guided Learning (FGL) strategy designed to enable detection networks to continuously adapt to unknown forgery techniques. Specifically, the FGL strategy captures the differential information between known and unknown forgery techniques, allowing the model to dynamically adjust its learning process in real time. To further improve the ability to perceive forgery traces, we design a Dual Perception Network (DPNet) that captures both differences and relationships among forgery traces. In the frequency stream, the network dynamically perceives and extracts discriminative features across various forgery techniques, establishing essential detection cues. These features are then integrated with spatial features and projected into the embedding space. In addition, graph convolution is employed to perceive relationships across the entire feature space, facilitating a more comprehensive understanding of forgery trace correlations. Extensive experiments show that our approach generalizes well across different scenarios and effectively handles unknown forgery challenges, providing robust support for deepfake detection.

## 🚀 Introduction

<div align="center">
    <img width="1000" alt="image" src="figures/introduction.png?raw=true">
</div>


Comparison with mainstream methods for deepfake cross-domain detection. Our method analyzes differences between forgery techniques and progressively updates model weights. Additionally, the frequency stream dynamically captures diverse forgery features, which are then integrated with the spatial stream to obtain a more discriminative embedding space.


## 📻 Overview

<div align="center">
    <img width="1000" alt="image" src="figures/network.png?raw=true">
</div>

<div align="center">
Illustration of the overall architecture.
</div>

## 📆 TODO LIST
In the submission stage, we will disclose some core algorithms of the model. Our complete codebase will be released upon paper acceptance.
- [x] [2025.4.14] Release the project page.
- [x] [2025.4.14] Release instructions for dataset preparation.
- [ ] Release the core code for part of the model.
- [ ] Release the complete model code.
- [ ] Release the training and inference code.
- [ ] Release the pretrained model.

## 🎮 Getting Started

### 1. Install Environment

`python -m pip install -r requirements.txt`

### 2. Dataset Preparation

- We used several public deepfake datasets, as shown in the following table. You can enter the dataset website to download the original data.

| Dataset              | Real Videos | Fake Videos | Features                        | Original data link    |
|----------------------|-------------|-------------|---------------------------------|-----------------------|
| FaceForensics++       | 1,000       | 4,000       | Different forgery techniques |[Download](https://github.com/ondyari/FaceForensics)|
| Celeb-DF-v2          | 590         | 5,639       | Celebrity dataset               |[Download](https://www.cs.albany.edu/~lsw/celeb-deepfakeforensics.html)|
| DeeperForensics-1.0   | 50,000      | 10,000      | Complex scenes                  |[Download](https://liming-jiang.com/projects/DrF1/DrF1.html)|
| WildDeepFake         | 3,805       | 3,509       | Internet-collected              |[Download](https://github.com/deepfakeinthewild/deepfake-in-the-wild)|
| DFDC                  | 23,564      | 104,500     | Complex scenes, multiple forgery methods |[Download](https://ai.facebook.com/datasets/dfdc)|

- Please use MTCNN crop the face area, sample 20 frames from each video and put them in the correct path as following.

```
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
```

### 3. Train

Upon Acceptance -> Codebase Liberation Activated 🔓

### 3. Test

Upon Acceptance -> Codebase Liberation Activated 🔓

### 3. Pretrained Model
Upon Acceptance, we will provide the [pretrained model](https://drive.google.com/drive/folders/1EPY-uxIoA6a8ZHzbSlJ4Lg7Jm5rD6fsX?usp=drive_link) based on FaceForensics++. 

## 🖼️ Visualization

<div align="center">
<img width="600" alt="image" src="figures/visualization.png?raw=true">
</div>

<div align="center">
Saliency map visualization of Baseline and our FGL. The red box indicates some obvious or subtle forgery traces.
</div>

## ✨ Quantitative comparison

<div align="center">
    <img width="1000" alt="image" src="figures/table.png?raw=true">
</div>

<div align="center">
Performance comparison with 11 methods on unknown forgery datasets.
</div>

