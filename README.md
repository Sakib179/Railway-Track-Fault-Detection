# Efficient and Accurate Railway Track Fault Detection Using CNN-Based Deep Learning Models

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
[![Paper](https://img.shields.io/badge/Paper-CSE424_paper.pdf-brightgreen)](CSE424_paper.pdf)

**A deep learning-based automated railway track inspection system using transfer learning with state-of-the-art CNNs. Achieves 99.54% accuracy — significantly outperforming existing research.**

---

### Author
**Sakib Rayhan Yeasin**  
BRAC University, Dhaka, Bangladesh  
Email: [sakib.rayhan.yeasin@g.bracu.ac.bd](mailto:sakib.rayhan.yeasin@g.bracu.ac.bd)  
ORCID: [0009-0007-1284-0866](https://orcid.org/0009-0007-1284-0866)  
Website: [https://www.bracu.ac.bd](https://www.bracu.ac.bd)

---

### Abstract
Railway transport is affordable, fast, and widely used — but track defects remain a leading cause of accidents. Manual inspection is slow, costly, and error-prone. This research presents a highly accurate deep learning solution for automated railway track fault detection from images.

Four pre-trained CNN models were evaluated:
- **InceptionV3** (Best) → **99.54% Accuracy**, **F1-score: 0.9954**
- DenseNet121
- ResNet50V2
- ConvNeXt-Tiny

Models were trained on a merged dataset of **2,178 real-world railway track images** and tested on a completely unseen dataset from **Roboflow** — still achieving **>98% accuracy**.

This work significantly outperforms prior studies (YOLOv11: 92.64%, ECARRNet: 93.28%) and proves that lightweight, accurate models are ready for real-world deployment on drones, robots, and edge devices.

**Keywords:** Railway defect detection • Deep Learning • Computer Vision • CNN • Transfer Learning

---

### Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Results](#results)
- [Repository Structure](#repository-structure)
- [Requirements](#requirements)
- [Installation & Usage](#installation--usage)
- [Citation](#citation)
- [License](#license)
- [Contact](#contact)

---

### Overview
Traditional railway track inspection relies on manual methods — slow, expensive, and unreliable. This project uses **transfer learning with modern CNNs** to detect cracks, missing fasteners, and structural defects automatically and in real time.

**Key Features:**
- Merged & cleaned dataset from multiple public sources
- Comprehensive EDA (class balance, image size, brightness, color analysis)
- High generalization: validated on unseen Roboflow data
- Lightweight models suitable for edge deployment (drones, inspection bots)

---

### Dataset
Merged from 3 high-quality Kaggle datasets:
- Total: **2,178 images**
  - Defective: 1,106
  - Non-Defective: 1,072
- Near-perfect class balance (~1.03:1 ratio)
- Most common resolution: **4000×3000** (1,749 images)
- Unseen test set: Roboflow Railway Track Dataset

> Dataset not included due to size. Download links in paper references [4–6].

**EDA Highlights (see notebook):**
- Class distribution (pie/bar charts)
- Image dimension analysis
- Brightness comparison (Defective images darker due to cracks/shadows)
- Dominant color channel: **Blue**

---

### Methodology
1. **Data Merging & Preprocessing** → Resize, normalize
2. **Transfer Learning** on ImageNet-pretrained models
3. **Fine-tuning** with custom classification head
4. **Training** using TensorFlow/Keras (binary classification)
5. **Evaluation** on hold-out test set + unseen Roboflow data
6. **Focus:** Accuracy + lightweight design for edge deployment

---

### Results
| Model           | Test Accuracy | F1-Score | Unseen Data Accuracy |
|----------------|---------------|----------|----------------------|
| **InceptionV3** | **99.54%**    | **0.9954** | **>98%**            |
| ResNet50V2      | 99.31%        | 0.9932   | **>98%**            |
| DenseNet121     | 98.89%        | 0.9885   | 97.2%               |
| ConvNeXt-Tiny   | 98.67%        | 0.9860   | 96.8%               |

Outperforms all prior works including YOLOv11 and ECARRNet.

---

### Repository Structure
