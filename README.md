# 🖼️ Image Robustness Evaluation on Caltech-101

This project evaluates **image robustness under various perturbations** using the **Caltech-101** dataset.  
We apply common image degradations — such as JPEG compression, cropping, rotation, Gaussian noise, and blur — and measure their effects on image quality using multiple metrics.

---

## 📌 Why This Project?
In real-world scenarios, images can be degraded due to:
- **Low-quality compression** (e.g., social media uploads)
- **Camera movement / rotation**
- **Cropping**
- **Sensor noise**
- **Lens blur**

For **computer vision applications** like object detection or classification, these degradations can significantly impact performance.  
The goal of this project is to:
1. Simulate these degradations at multiple severity levels
2. Quantify the effect using objective metrics
3. Provide **before/after visual panels** to aid human understanding

---

## 📂 Dataset
- **Source**: [Caltech-101 dataset on Kaggle](https://www.kaggle.com/datasets/imbikramsaha/caltech-101)
- **Description**: 101 object categories, each with 40–800 images.
- **Subset used**: Random **10 categories**, max **50 images per category** to speed up processing.

---

## 🛠️ Methods
### **1. Transformations Applied**
| Transformation | Parameter Range | Description |
|----------------|----------------|-------------|
| **JPEG Compression** | 80, 60, 40, 20 | Simulates lossy compression artifacts |
| **Cropping** | 5%, 10%, 20% | Crops center and resizes back |
| **Rotation** | 5°, 10°, 20° | Rotates image without expanding |
| **Gaussian Noise** | σ = 5, 10, 20 | Adds pixel noise |
| **Gaussian Blur** | radius = 1, 2, 3 | Simulates lens or motion blur |

---

### **2. Quality Metrics**
| Metric | Purpose |
|--------|---------|
| **PSNR** (Peak Signal-to-Noise Ratio) | Measures fidelity; higher = better |
| **SSIM** (Structural Similarity Index) | Measures perceived similarity |
| **Edge SSIM** | SSIM applied to image edges for shape preservation |
| **MSE** (Mean Squared Error) | Pixel-wise difference |

---

## 📜 Workflow
1. **Download dataset** from Kaggle
2. **Select subset** (10 random categories × max 50 images each)
3. **Apply transformations** to each image
4. **Measure quality degradation**
5. **Save results** in CSV format
6. **Plot metrics** vs severity
7. **Generate before/after panels** for qualitative comparison

---

## 📊 Results
### **Sample Metric Trend**
_(Example: JPEG compression severity vs metrics)_
![PSNR vs Severity](results/psnr_vs_severity.png)
![SSIM vs Severity](results/ssim_vs_severity.png)
![Edge SSIM vs Severity](results/edge_ssim_vs_severity.png)

### **Before/After Panel Example**
_(Crop = 20%)_
![Before/After Example](results/figures/example_panel.png)

---

## 📁 Project Structure
