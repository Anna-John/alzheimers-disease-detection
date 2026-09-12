# 🧠 Alzheimer's Disease Detection using Deep Learning

## Overview
An AI-powered system for automatic classification of Alzheimer's disease 
severity from brain MRI scans using VGG-16 transfer learning and 
Grad-CAM explainability.

**MSc Data Analytics Dissertation — Dublin Business School, 2026**

---

## 🎯 Results
| Metric | Score |
|--------|-------|
| Test Accuracy | 79.71% |
| Macro F1 Score | 0.79 |
| Moderate Dementia Accuracy | 100% |

---

## 📊 Dataset
- **Source:** OASIS-1 (Open Access Series of Imaging Studies)
- **Patients:** 416 brain MRI scans
- **Classes:** Non Demented, Very Mild, Mild, Moderate Dementia
- **After Augmentation:** 916 images

---

## 🔬 Methodology

### Preprocessing
- Extracted single centre slice from each 3D NIfTI brain scan
- Resized to 224×224 pixels
- Normalised and converted to RGB for VGG-16 input
- Applied data augmentation to address severe class imbalance

### Model Architecture
- **Base model:** VGG-16 pretrained on ImageNet
- **Custom head:** Dense layers with Dropout + 4-class Softmax output
- **Training Phase 1:** Frozen VGG-16 layers — trained custom head only
- **Training Phase 2:** Fine-tuned last 4 VGG-16 layers with reduced 
  learning rate

### Explainability
- Implemented **Grad-CAM** to generate heatmaps highlighting 
  brain regions influencing predictions
- Confirmed clinically meaningful disease progression patterns

---

## 🛠️ Technologies
- Python
- TensorFlow / Keras
- VGG-16 Transfer Learning
- Grad-CAM
- NumPy, Pandas, Matplotlib

---

## 📁 Repository Structure

```
alzheimers-disease-detection/
├── preprocessing.py      
├── model.py             
├── train.py             
├── gradcam.py           
├── evaluate.py          
└── requirements.txt     
```
---

## 🔍 Key Findings
- Grad-CAM confirmed clinically meaningful progression:
  - **Non Demented:** Minimal activation
  - **Very Mild:** Periventricular activation
  - **Mild:** Temporal and parietal activation
  - **Moderate:** Precise hotspot on enlarged lateral ventricle

---

## 📚 Novel Contribution
First study to combine the OASIS-1 clinical dataset with VGG-16 
transfer learning and Grad-CAM explainability in a single 
unified system.

---

## 👩‍💻 Author
**Anna John**  
MSc Data Analytics, Dublin Business School  
[LinkedIn](https://linkedin.com/in/annajohndataanalyst)
