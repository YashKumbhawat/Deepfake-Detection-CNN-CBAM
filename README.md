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


