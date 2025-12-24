
DATASET LINK : https://www.kaggle.com/datasets/manjilkarki/deepfake-and-real-images


Deepfake Detection using CNN with CBAM Attention

📌 Overview

This project implements a Deepfake Image Detection system using a Convolutional Neural Network (CNN) enhanced with a Convolutional Block Attention Module (CBAM).
The model classifies an input image as Fake or Real by learning discriminative visual patterns and selectively focusing on important features and spatial regions.

🎯 Motivation

Deepfake images often contain subtle and localized artifacts, such as:

(1) unnatural textures

(2) blending inconsistencies

(3) lighting distortions

(4) boundary artifacts around facial regions (eyes, mouth, skin)


Standard CNNs treat all features equally, which can cause them to miss these subtle cues.
To overcome this limitation, CBAM attention is integrated to guide the model toward important features and regions, improving detection accuracy.

🧠 Model Architecture

The proposed architecture consists of four CNN blocks, each followed by CBAM attention, and a fully connected classification head.

Architecture Flow

Input Image (256×256×3)
→ Convolution + CBAM + MaxPooling
→ Convolution + CBAM + MaxPooling
→ Convolution + CBAM + MaxPooling
→ Convolution + CBAM + MaxPooling
→ Flatten
→ Dense (100) + Dropout
→ Dense (2) + Softmax
→ Prediction (Fake / Real)

Layer-wise Description

Input: RGB image of size 256×256×3

Conv Block 1: 8 filters + CBAM + MaxPooling

Conv Block 2: 16 filters + CBAM + MaxPooling

Conv Block 3: 32 filters + CBAM + MaxPooling

Conv Block 4: 64 filters + CBAM + MaxPooling

Fully Connected Layer: 100 neurons with ReLU activation

Dropout: 0.25 to reduce overfitting

Output Layer: 2 neurons with Softmax activation


🔍 Why CBAM Attention?

CBAM enhances feature representation by applying attention in two stages:

1️⃣ Channel Attention – What to focus on

Identifies important feature maps

Suppresses irrelevant or noisy channels

Helps the model prioritize discriminative deepfake features

2️⃣ Spatial Attention – Where to focus

Identifies important spatial regions

Highlights facial areas such as eyes, mouth, and boundaries

Improves localization of deepfake artifacts

Result: Better accuracy with minimal increase in model complexity.


📂 Dataset Structure

The dataset follows a directory-based structure compatible with Keras ImageDataGenerator:

Dataset

    Train
         Fake
         Real

    Val
         Fake
         Real
         
    Test
         Fake
         Real


⚠️ Dataset is not included in this repository due to size constraints.


⚙️ Training Configuration

Framework: TensorFlow / Keras

Optimizer: Adam

Learning Rate: 0.0003

Loss Function: Categorical Cross-Entropy

Output Activation: Softmax

Batch Size: 32

Checkpointing: Enabled (epoch-wise saving)



📊 Evaluation Metrics

Model performance is evaluated on the test dataset using:

Accuracy

Precision

Recall

F1-score

Confusion Matrix

ROC–AUC Curve

These metrics ensure a comprehensive and unbiased evaluation.


🔎 Model Interpretability

To improve transparency, Grad-CAM visualizations are used:

Heatmaps are overlaid on test images

Highlights regions contributing most to predictions

Confirms that the model focuses on meaningful facial regions


💾 Checkpointing & Resume Training

Model weights are saved after every epoch

Training automatically resumes from the latest checkpoint if interrupted

Ensures robustness against Google Colab timeouts

▶️ How to Run the Project

Clone the repository

Install dependencies using:

pip install -r requirements.txt


Open the notebook in Google Colab or Jupyter

Upload the dataset

Run cells sequentially


