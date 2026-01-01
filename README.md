# Deepfake Detection using CNN with CBAM Attention

## 📌 Project Overview
This project presents a **Deepfake Image Detection system** using a **Convolutional Neural Network (CNN)** enhanced with a **Convolutional Block Attention Module (CBAM)**.  
The model classifies input images as **Fake** or **Real** by learning discriminative visual patterns and selectively focusing on important feature channels and spatial regions.

The integration of attention mechanisms enables the network to detect subtle and localized deepfake artifacts more effectively than standard CNN models.

---

## 🧠 Motivation
Deepfake images often contain subtle and localized artifacts that are difficult to detect using traditional CNNs, such as:
- Unnatural textures  
- Blending inconsistencies  
- Lighting distortions  
- Boundary artifacts around facial regions (eyes, mouth, skin)  

Standard CNNs treat all features equally, which may cause them to miss these fine-grained cues.  
To overcome this limitation, **CBAM attention** is integrated into the network to guide the model toward **important features and spatial regions**, improving detection accuracy and robustness.

---

## 📂 Dataset Description
- **Dataset Name**: Deepfake and Real Images Dataset  
- **Source**: Kaggle  
- **Link**: https://www.kaggle.com/datasets/manjilkarki/deepfake-and-real-images  
- **Type**: Image Dataset  
- **Classes**:
  - `Fake`
  - `Real`

⚠️ **Note**: The dataset is not included in this repository due to size constraints.

---

## 📂 Dataset Structure
The dataset follows a directory-based structure compatible with **Keras ImageDataGenerator**:

```text
Dataset/
│
├── Train/
│   ├── Fake/
│   └── Real/
│
├── Val/
│   ├── Fake/
│   └── Real/
│
└── Test/
    ├── Fake/
    └── Real/
```

---

## 🏗️ Methodology

The proposed approach uses a **custom CNN architecture** where each convolutional block is enhanced with **CBAM attention**.  
The model progressively learns low-level to high-level facial features while selectively focusing on the most informative channels and spatial regions.

---

## 🧠 Model Architecture

### Architecture Flow

```text

Input Image (256×256×3)
→ Convolution + CBAM + MaxPooling
→ Convolution + CBAM + MaxPooling
→ Convolution + CBAM + MaxPooling
→ Convolution + CBAM + MaxPooling
→ Flatten
→ Dense (100) + Dropout
→ Dense (2) + Softmax
→ Prediction (Fake / Real)

```




