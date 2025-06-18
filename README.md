# 🧠 Parkinson's Disease Voice Detection with Machine Learning

> A lightweight and effective machine learning system for detecting **Parkinson’s Disease** from **voice samples**, trained with a Random Forest and optimized for **mobile and embedded deployment** using **TensorFlow Lite**.

---

## 🎯 Project Goal

This project aims to build a tool that can identify Parkinson’s Disease from voice recordings using **machine learning techniques**.  
Beyond training and evaluating the model, the objective was to **convert it into a lightweight format** using **TensorFlow Lite**, making it suitable for mobile phones and embedded systems.

---

## 📊 Dataset Overview

- **Size:** 195 voice samples  
- **Features:** 24 vocal biomarkers  
- **Class distribution:**
  - 🧬 Class 1 (Parkinson’s): 147 samples
  - 💬 Class 0 (Healthy): 48 samples

> ⚠️ The dataset is imbalanced toward Parkinson’s patients — this was considered during model evaluation.

---

## 🤖 Machine Learning Model

### 🪵 Algorithm: **Random Forest Classifier**
A robust ensemble learning method based on decision trees:
- Reduces overfitting  
- Works well with small/medium datasets  
- Handles noise and outliers  
- No need for heavy preprocessing  
- Provides feature importance scores for explainability  

### 🔧 Model Tuning

**Optimization method:** `GridSearchCV`  
**Best hyperparameters:**
- `n_estimators = 100` — number of trees  
- `max_depth = None` — trees grow until optimal splits  
- `min_samples_split = 5` — controls tree complexity

---

## 🧪 Model Performance

- ✅ **Accuracy:** 92%  
- 🧠 **Recall (Parkinson’s class):** 97%  
- 📈 **AUC-ROC:** 0.96  
- 🔍 Confusion Matrix: only **3 errors** on the test set (39 samples)

> The model shows strong predictive performance, particularly in identifying patients with Parkinson’s.

---

## 📦 TensorFlow Lite Conversion

After training, the model was successfully converted to **TensorFlow Lite** for efficient deployment on edge devices.

### 📐 Model Specs:
- **Input shape:** `(None, 22)` → Each sample has 22 features  
- **Output:** Probability distribution across 2 classes (Healthy / Parkinson's)

## 👨‍🚀 Authors & Credits

> Angela Rossi EMAIL: angela.rossi393@gmail.com

**Example inference:**
```plaintext
Output shape: (1, 2)  
Predicted probabilities: [0.0118, 0.9881]  
→ Prediction: Class 1 (Parkinson)
)_
