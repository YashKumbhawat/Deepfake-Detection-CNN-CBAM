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


### Layer-wise Description

- **Input**: RGB image of size 256×256×3  
- **Conv Block 1**: 8 filters + CBAM + MaxPooling  
- **Conv Block 2**: 16 filters + CBAM + MaxPooling  
- **Conv Block 3**: 32 filters + CBAM + MaxPooling  
- **Conv Block 4**: 64 filters + CBAM + MaxPooling  
- **Fully Connected Layer**: 100 neurons with ReLU activation  
- **Dropout**: 0.25 to reduce overfitting  
- **Output Layer**: 2 neurons with Softmax activation  

---

## 🔍 Why CBAM Attention?

CBAM improves feature representation by applying attention in two sequential stages:

### 1️⃣ Channel Attention — What to focus on

- Identifies important feature maps  
- Suppresses irrelevant or noisy channels  
- Helps the model prioritize discriminative deepfake features  

### 2️⃣ Spatial Attention — Where to focus

- Identifies important spatial regions  
- Highlights facial areas such as eyes, mouth, and boundaries  
- Improves localization of deepfake artifacts  

**Result**: Improved detection accuracy with minimal increase in model complexity.

---

## ⚙️ Training Configuration

- **Framework**: TensorFlow / Keras  
- **Optimizer**: Adam  
- **Learning Rate**: 0.0003  
- **Loss Function**: Categorical Cross-Entropy  
- **Output Activation**: Softmax  
- **Batch Size**: 32  
- **Checkpointing**: Enabled (epoch-wise saving)  

---

## 📊 Evaluation Metrics

The model performance is evaluated on the test dataset using:

- Accuracy  
- Precision  
- Recall  
- F1-score  
- Confusion Matrix  
- ROC–AUC Curve  

---

## 🔎 Model Interpretability

To improve transparency, **Grad-CAM visualizations** are used:

- Heatmaps are overlaid on test images  
- Highlights regions contributing most to predictions  
- Confirms that the model focuses on meaningful facial regions  

---

## 💾 Checkpointing and Resume Training

- Model weights are saved after every epoch  
- Training automatically resumes from the latest checkpoint if interrupted  
- Ensures robustness against Google Colab timeouts  

---

## ▶️ How to Run the Project

1. Clone the repository  
2. Install dependencies:
   ``` pip install -r requirements.txt ```
3. Open the notebook in **Google Colab** or **Jupyter Notebook**  
4. Upload the dataset  
5. Run the cells sequentially  

---

## 🛠️ Technologies Used

- Python  
- TensorFlow / Keras  
- NumPy  
- Pandas  
- Matplotlib  
- Seaborn  
- OpenCV  
- Scikit-learn  
- Pillow  
- tqdm  

---

## 👤 Author

**Yash Kumbhawat**  
Department of Information Technology,  
NITK  

---

## 📜 License

This project is intended for **academic and educational purposes only**.  
You are free to use and modify the code with proper attribution.





