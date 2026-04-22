# 🔍 Automated Surface Crack Detection using Supervised & Self-Supervised Learning

## 📌 Overview
This project presents a comprehensive benchmark study on **surface crack detection** using both **Supervised Learning** and **Self-Supervised Learning (SSL)** approaches. The objective is to evaluate model performance, robustness, and label efficiency in data-constrained environments.

We compare five supervised architectures against three SSL paradigms to identify the most efficient strategy for real-world structural health monitoring applications.

---

## 🏫 Institution
**East West University**  
**Course:** CSE475 - Machine Learning  
**Group 8**

---

## 👥 Team Members
- Md Saif Abrar Chowdhury (2022-3-60-051)
- Syeda Rehnova Nobo (2022-3-60-058)
- Sunjeda Islam (2022-1-60-194)
- Mithila Mostofa Tonni (2023-1-60-155)

---

## 📊 Dataset
- **Name:** Py-CrackDB  
- **Total Images:** 504 (after deduplication)  
- **Classes:**  
  - With Crack  
  - Without Crack  

### 🔧 Data Processing
- Duplicate removal using **Perceptual Hashing (pHash)**  
- Data augmentation:
  - Random flips  
  - Rotation  
  - Color jitter  
- Image normalization (ImageNet standard)

---

## 🧠 Models Evaluated

### 🔹 Supervised Models
- ResNet-50  
- ResNet-101  
- MobileNetV2  
- EfficientNet-B0  
- Vision Transformer (ViT-B/16)

### 🔹 Self-Supervised Learning (SSL)
- **SimCLR** (Contrastive Learning)  
- **BYOL** (Non-Contrastive Learning)  
- **MAE** (Masked Autoencoder)

---

## ⚙️ Experimental Setup
- **Environment:** Kaggle Notebook  
- **GPU:** NVIDIA Tesla T4  
- **Framework:** PyTorch  

### Training Configuration
| Type        | Epochs |
|------------|--------|
| Supervised | 10     |
| SimCLR     | 200    |
| BYOL       | 125    |
| MAE        | 40     |

---

## 📈 Results Summary

### ✅ Supervised Performance
- All models achieved **~100% accuracy**
- High robustness across multiple train-test splits

### 🔍 SSL Performance
| Method | Linear Probe Accuracy |
|--------|----------------------|
| SimCLR | 100% |
| BYOL   | 100% |
| MAE    | 94.74% |

### 📉 Label Efficiency
| Label % | SimCLR | BYOL | MAE |
|--------|--------|------|-----|
| 1%     | 0.8596 | 0.7544 | 0.7807 |
| 5%     | 0.9737 | 0.9825 | 0.8596 |
| 10%    | 1.0000 | 1.0000 | 0.8509 |
| 25%    | 1.0000 | 1.0000 | 0.8860 |
| 50%    | 1.0000 | 1.0000 | 0.8947 |

---

## 📊 Key Insights
- **Contrastive SSL (SimCLR, BYOL)** achieves perfect accuracy with only **10% labeled data**
- **MAE underperforms** in classification despite strong reconstruction ability
- **MobileNetV2 & EfficientNet-B0** are optimal for edge deployment
- Dataset is highly **linearly separable**, leading to ceiling performance

---

## 🧪 Statistical Analysis
- Wilcoxon Signed-Rank Test used  
- No significant difference between SimCLR & BYOL  
- Significant improvement over MAE (p < 0.05)

---

## ⚠️ Limitations
- Small dataset size (504 images)  
- Limited environmental variability  
- Potential over-optimistic performance  
- Limited generalization across surface types  

---

## ⚖️ Ethical Considerations
- False negatives may lead to structural failure  
- System should assist, not replace, human inspectors  
- Risk of bias in deployment environments  

---

## 🚀 Future Work
- Extend to multi-class defect detection  
- Improve robustness under real-world noise  
- Scale dataset diversity  
- Optimize SSL for industrial deployment  

---

## 📚 References
1. Dorafshan et al., 2018 – SDNET2018 Dataset  
2. Zhang et al., 2016 – Road Crack Detection  
3. Tan & Le, 2019 – EfficientNet  
4. Dosovitskiy et al., 2020 – Vision Transformer  

---

## 🏁 Conclusion
Contrastive self-supervised learning provides a **high-performance, label-efficient alternative** to traditional supervised approaches for crack detection, making it highly suitable for real-world applications with limited labeled data.
