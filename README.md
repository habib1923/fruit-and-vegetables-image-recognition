# 🍎🥕 Robust Fruit & Vegetable Recognition System

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Gradio](https://img.shields.io/badge/Interface-Gradio-purple)
![OpenCV](https://img.shields.io/badge/Vision-OpenCV-green)

## 📌 Project Overview
This project is a **Computer Vision & Machine Learning** pipeline designed to classify images of fruits and vegetables into distinct categories. 

Unlike Deep Learning approaches (CNNs) that learn features automatically, this project demonstrates a **Feature Engineering** approach. It explicitly extracts mathematical descriptors (Color, Texture, Shape) from images and trains a **Random Forest Classifier** to achieve high-accuracy predictions.

**Author:** SKHIRI HABIB  
**Context:** 5th Year Engineering Mini-Project  
**Performance:** 🏆 **96.66% Accuracy** on Test Set

## 🚀 Key Features
* **Hybrid Feature Extraction**: Combines three distinct types of image descriptors for robust representation:
    * 🎨 **Color**: HSV Histograms to capture chromatic content.
    * 🧶 **Texture**: Haralick features (GLCM) to capture surface details.
    * 📐 **Shape**: Hu Moments to capture object geometry.
* **Machine Learning Classifier**: Utilizes a **Random Forest** ensemble for classification.
* **Interactive Demo**: Includes a **Gradio** web interface for real-time testing.
* **Pipeline**: Automated preprocessing, feature scaling, and evaluation pipeline.

## 📂 Dataset
The project uses the **[Fruit and Vegetable Image Recognition](https://www.kaggle.com/datasets/kritikseth/fruit-and-vegetable-image-recognition)** dataset from Kaggle.
* **Content**: Images of fruits and vegetables (e.g., Apple, Banana, Carrot, etc.).
* **Structure**: Organized into `train`, `test`, and `validation` folders.
* **Setup**: The notebook automatically downloads and unzips the dataset using the Kaggle API.

## ⚙️ Methodology

The system follows a standard Computer Vision pipeline:

1.  **Preprocessing**:
    * Image resizing to a fixed scale.
    * Noise reduction (Gaussian Blur).
    * Color space conversion (RGB $\to$ HSV for color features, RGB $\to$ Gray for texture/shape).

2.  **Feature Extraction**:
    * **Color Histograms**: Captures the distribution of colors (Hue/Saturation) unaffected by scale or rotation.
    * **Haralick Textures**: Computes statistical properties (Contrast, Correlation, Energy, Homogeneity) from the Gray-Level Co-occurrence Matrix (GLCM).
    * **Hu Moments**: 7 invariant moments that describe the shape outline, invariant to translation, scale, and rotation.

3.  **Classification**:
    * **Algorithm**: Random Forest Classifier (`n_estimators=100`).
    * **Scaling**: `StandardScaler` applied to normalize feature vectors before training.

## 📊 Results & Evaluation

The model was evaluated on the unseen Test Set:

| Metric | Score |
| :--- | :--- |
| **Accuracy** | **96.66%** |
| **Precision** | High across distinct classes (e.g., Orange, Apple) |
| **Recall** | Robust detection even with slight variations |

*(Detailed confusion matrix and classification reports are available in the notebook)*

## 💻 Installation & Usage

### Prerequisites
* Python 3.8+
* Kaggle API Token (`kaggle.json`)

### 1. Clone the Repository
```bash
git clone [https://github.com/yourusername/fruit-veg-recognition.git](https://github.com/yourusername/fruit-veg-recognition.git)
cd fruit-veg-recognition
