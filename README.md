<div align="center">
<h1> Forgery Guided Learning Strategy with Dual Perception Network for Deepfake Cross-domain Detection </h1>
</div>

## ⭐ Abstract

The emergence of deepfake technology has introduced a range of societal problems, garnering considerable attention. Current deepfake detection methods perform well on specific datasets, but exhibit poor performance when applied to datasets with unknown forgery techniques. Moreover, as the gap between emerging and traditional forgery techniques continues to widen, cross-domain detection methods that rely on common forgery traces are becoming increasingly ineffective. This situation highlights the urgency of developing deepfake detection technology with strong generalization to cope with fast iterative forgery techniques. To address these challenges, we propose a Forgery Guided Learning (FGL) strategy designed to enable detection networks to continuously adapt to unknown forgery techniques. Specifically, the FGL strategy captures the differential information between known and unknown forgery techniques, allowing the model to dynamically adjust its learning process in real time. To further improve the ability to perceive forgery traces, we design a Dual Perception Network (DPNet) that captures both differences and relationships among forgery traces. In the frequency stream, the network dynamically perceives and extracts discriminative features across various forgery techniques, establishing essential detection cues. These features are then integrated with spatial features and projected into the embedding space. In addition, graph convolution is employed to perceive relationships across the entire feature space, facilitating a more comprehensive understanding of forgery trace correlations. Extensive experiments show that our approach generalizes well across different scenarios and effectively handles unknown forgery challenges, providing robust support for deepfake detection.

## 🚀 Introduction

<div align="center">
    <img width="400" alt="image" src="figures/challenge.png?raw=true">
</div>

The challenges: (a) the effects of fuzzy edges (soft boundaries). (b) The misleading co-occurrence of salient and non-salient objects.

## 📻 Overview

<div align="center">
<img width="800" alt="image" src="figures/network.png?raw=true">
</div>

Illustration of the overall architecture.


## 📆 TODO

- [x] Release code

## 🎮 Getting Started

### 1. Install Environment

```
conda create -n Net python=3.8
conda activate Net
pip install torch==1.13.0 torchvision==0.14.0 torchaudio==0.13.0 --extra-index-url https://download.pytorch.org/whl/cu117
pip install packaging
pip install timm==0.4.12
pip install pytest chardet yacs termcolor
pip install submitit tensorboardX
pip install triton==2.0.0
pip install scikit-learn matplotlib thop h5py SimpleITK scikit-image medpy yacs PyWavelets
```

### 2. Prepare Datasets

- Download datasets: ISIC2018 from this [link](https://challenge.isic-archive.com/data/#2018), Kvasir from this[link](https://link.zhihu.com/?target=https%3A//datasets.simula.no/downloads/kvasir-seg.zip), BUSI from this [link](https://scholar.cu.edu.eg/?q=afahmy/pages/dataset), Moun-Seg from this [link](https://www.kaggle.com/datasets/tuanledinh/monuseg2018), and COVID-19 from this [link](https://drive.usercontent.google.com/download?id=1FHx0Cqkq9iYjEMN3Ldm9FnZ4Vr1u3p-j&export=download&authuser=0).


- Folder organization: put datasets into ./data/datasets folder.

### 3. Train the Net

```
python train.py --datasets ISIC2018
training records is saved to ./log/dataset folder
pre-training file is saved to ./log/dataset folder
concrete information see train.py, please
```

### 3. Test the RoMER-UNet

```
python test.py --datasets ISIC2018
training records is saved to ./log/dataset folder
pre-training file is saved to ./log/dataset folder
concrete information see test.py, please
```

### 3. Code example

```
python Test/test_example.py
```

## 🖼️ Visualization

<div align="center">
<img width="800" alt="image" src="figures/com_pic.png?raw=true">
</div>

<div align="center">
We compare our method against 13 state-of-the-art methods. The red box indicates the area of incorrect predictions.
</div>

## ✨ Quantitative comparison

<div align="center">
<img width="800" alt="image" src="figures/com_tab.png?raw=true">
</div>

<div align="center">
Performance comparison with ten SOTA methods on ISIC2018, Kvasir, BUSI, COVID-19 and Monu-Seg datasets.
</div>

## 🎫 License

The content of this project itself is licensed under [LICENSE](https://github.com/ILoveACM-MM/RoDeCon-Net?tab=Apache-2.0-1-ov-file).
