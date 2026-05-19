# **SmokeSVD:Smoke Reconstruction from A Single View via Progressive Novel View Synthesis and Refinement with Diffusion Models (CVPR 2026 Oral)**
**Authors:** [Chen Li](https://cs.tjut.edu.cn/info/1217/2502.htm), [Shanshan Dong](https://github.com/dongss414), [Sheng Qiu](https://github.com/ZjnuQS), [Jianmin Han](https://mypage.zjnu.edu.cn/HJM1/zh_CN/index.htm), [Yibo Zhao](https://cs.tjut.edu.cn/info/1226/2741.htm), [Zan Gao](https://cs.tjut.edu.cn/info/1214/2193.htm), [Taku Komura](https://i.cs.hku.hk/~taku/), [Kemeng Huang](https://kemenghuang.github.io/) ([Paper](https://arxiv.org/abs/2507.12156)•[Video](https://www.youtube.com/watch?v=UE4sH1niy4o))

![cover](assets/cover.png)

## **Method Overview**

![framework](assets/framework.png)

Given a single-view smoke video, **SmokeSVD**:

1. **Synthesizes an auxiliary side view** to reduce geometric ambiguity.
2. **Progressively refines novel views** from near to far angles with a cyclic 2D↔3D loop.
3. **Reconstructs 3D density** and estimates **velocity/inflow** with differentiable advection for physically plausible dynamics.

---

## **Quick Installation**

```
# build environment with python 3.10
conda create -n smokeSVD python=3.10 -y
conda activate smokeSVD 

# install PyTorch
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu128

# install required packages
pip install -r requirements.txt
```

### **Requirements**

- GPU >= 24G

---

## **Data Preparation**

```
# Download Scalarflow datasets
please refer to  [website](https://ge.in.tum.de/publications/2019-scalarflow-eckert/)

# Create the data folder
mkdir data

# Move the downloaded dataset into the data folder
# For example:
# mv path_to_downloaded_dataset/* data/
```



---

## **Getting Started**

### Adjusting Parameters

```
# Rec.py
# Validation sequence index (depends on your dataset numbering, e.g., sim_xxx)
scene_num = [0] 

# Frame range to process
start_frame = 20          
end_frame = 139         

# Dataset selection
dataset = "scalarflow"    # options: "scalarflow" or others
```
### Model Weights

please refer to [website](https://github.com/dongss414/SmokeSVD/releases/tag/1.0.0) and put them in the root directory.

### Run

Run `python Rec.py` to start reconstruction.
You can find the final results in ./Reconstruction.

---

## BibTex

If this work is helpful for your research, please consider citing:

```jsx
@inproceedings{li2026smokesvd,
title     = {SmokeSVD: Smoke Reconstruction from A Single View via Progressive Novel View Synthesis and Refinement with Diffusion Models},
author    = {Chen Li and Shanshan Dong and Sheng Qiu and Jianmin Han and Yibo Zhao and Zan Gao and Taku Komura and Kemeng Huang},
booktitle = {Proceedings of the IEEE/CVF conference on computer vision and pattern recognition},
year      = {2026}
}
```

---
