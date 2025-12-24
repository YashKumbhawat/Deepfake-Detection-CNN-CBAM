Deepfake Detection using CNN with CBAM Attention

This project presents a deep learning based approach for deepfake image detection using a Convolutional Neural Network (CNN) enhanced with a Convolutional Block Attention Module (CBAM). The model classifies an input image as Fake or Real by learning discriminative visual features and emphasizing important feature channels and spatial regions through attention mechanisms.

Motivation

Deepfake images often contain subtle artifacts such as unnatural textures, blending inconsistencies, lighting distortions, and boundary irregularities around facial regions like eyes and mouth. Traditional CNN models may not focus effectively on these fine-grained cues. To address this limitation, CBAM attention is integrated into the CNN architecture, enabling the model to selectively focus on the most informative features and regions of the image.

Model Architecture Overview

The proposed architecture consists of four convolutional blocks followed by a fully connected classification head. Each convolutional block is augmented with a CBAM attention module to enhance feature representation.

Architecture Flow

Input Image of size 256×256×3
→ Convolutional Feature Extraction
→ CBAM Attention (Channel + Spatial)
→ Max Pooling for Downsampling
→ Flattening of Feature Maps
→ Fully Connected Layers
→ Softmax Classification (Fake / Real)

Detailed Architecture

Input layer accepts a 256×256 RGB image.
The first convolutional block applies 8 filters to extract low-level features, followed by CBAM attention and max pooling.
The second block increases filters to 16 and repeats the same process.
The third block uses 32 filters for more complex feature extraction.
The fourth block uses 64 filters to capture high-level semantic features.
After feature extraction, the output is flattened and passed through a dense layer with 100 neurons and ReLU activation.
Dropout is applied for regularization.
The final layer uses two neurons with Softmax activation to output probabilities for Fake and Real classes.


