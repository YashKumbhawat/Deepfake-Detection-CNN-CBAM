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
