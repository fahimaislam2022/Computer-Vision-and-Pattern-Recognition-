# Computer-Vision-and-Pattern-Recognition-
## 📊 Dataset Description (PatchCamelyon)

The dataset used is **PatchCamelyon (PCam)** from Kaggle.

- It consists of histopathology *(real medical slides from breast cancer patients)* image patches for cancer detection  
- Each image is **96 × 96 pixels (RGB)**  
- Specifically: **lymph node tissue**  
- Extracted from a bigger dataset called **CAMELYON16**

---

## 🔢 Classification Task

This is a **binary classification dataset**:

- **0 → Negative** (no tumor)  
- **1 → Positive** (metastatic tumor present)  

> ⚠️ The label depends only on the **center area** of the image.  
> Even if edges contain tumor tissue, it does **not** count.

---

## 📦 Dataset Size

The dataset is originally large (~300,000 images), but a subset was used:

- **Training:** 40,000 images  
- **Validation:** 10,000 images  
- **Testing:** 10,000 images  

---

## 💾 Data Format

- Images are stored in **HDF5 (`.h5`) format**  
- Requires custom loading using **`h5py`**

---

## 🔄 Data Augmentation

To improve generalization, the following techniques were applied:

- Random flipping  
- Rotation  
https://patchcamelyon.grand-challenge.org/
https://github.com/basveeling/pcam
https://www.kaggle.com/datasets/andrewmvd/metastatic-tissue-classification-patchcamelyon
---

## 🧠 CNN Model Description

A custom **Convolutional Neural Network (CNN)** was built using **PyTorch**.

---

## 🏗️ Architecture

The model consists of **4 convolutional blocks**, each including:

- Convolution layer  
- Batch Normalization  
- ReLU activation  
- Max Pooling  

---

## 🔗 Fully Connected Layers

After feature extraction:

- Flattening layer  
- Fully connected layer (**512 units**)  
- Dropout (**0.5**) for regularization  
- Final output layer (**2 neurons for binary classification**)  

---

## ⚙️ Key Components

- **Batch Normalization:** Stabilizes training and improves performance  
- **Dropout:** Reduces overfitting  

---

## 📉 Training Setup

- **Loss Function:** CrossEntropyLoss  
- **Optimizer:** Adam  
- **Learning Rate Scheduler:** StepLR  

---

## 🎯 Model Capability

The network successfully learns **spatial features from medical images** for accurate classification.
