# Semantic Segmentation Optimization

PyTorch 语义分割模型优化项目，通过系统性改进将模型准确率从 **28.44%** 提升至 **31.88%**。

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg) ![PyTorch](https://img.shields.io/badge/PyTorch-1.9+-red.svg) ![OpenCV](https://img.shields.io/badge/OpenCV-4.5+-green.svg)

## Features

- **性能提升**: 通过三个优化策略实现 +3.44% 准确率提升
- **消融研究**: 系统验证每个优化组件的有效性  
- **效率平衡**: 在模型精度和推理速度间找到最佳权衡

## Results

| 策略组合 | 数据增强 | 网络加宽 | 超参数优化 | 准确率 |
|---------|:--------:|:--------:|:----------:|:------:|
| Baseline | ❌ | ❌ | ❌ | 28.44% |
| + Data Aug | ✅ | ❌ | ❌ | 30.15% |
| + Architecture | ✅ | ✅ | ❌ | 31.39% |
| **Full Model** | ✅ | ✅ | ✅ | **31.88%** |

## Quick Start

**Requirements**
```bash
pip install torch torchvision opencv-python matplotlib pillow numpy
```

**Run the Project**
```bash
# Clone repository
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```
```bash
# Open Jupyter notebook
jupyter notebook Segmentation_1.ipynb
```

## Implement

**Data Augmentation**: 图像尺寸扩大至 1.125x，增加像素信息的同时控制计算开销


**Network Widening**: 扩展卷积层通道数

- **Stage 1**: 64 → 8×8 (64)
- **Stage 2**: 256 → 16×16 (256)
- **Stage 3**: 512 → 28×28 (784)

Hyperparameter Tuning:

- **Learning rate**: 3e-4
- **Batch size**: 5
- **Evaluation starts from** epoch 90

## Project Stucture
<pre>
├── Segmentation_1.ipynb       # Main implementation notebook
├── README.md                  # Project documentation
├── loss curve/                # Training loss visualizations
├── tarining test history/     # Training and testing logs
</pre>
