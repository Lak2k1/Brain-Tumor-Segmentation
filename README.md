# Brain Tumor Segmentation using ResUNET

## Overview

This repository contains the implementation of a brain tumor segmentation model using the ResUNET architecture. The model is trained to segment brain tumors in MRI images, providing accurate and detailed tumor masks. The ResUNET architecture utilizes residual blocks, batch normalization, max pooling, upsampling, and concatenation to achieve state-of-the-art performance in segmentation tasks.

## Model Architecture

The ResUNET architecture is designed to effectively segment brain tumors in MRI images. Here's a brief overview of the model architecture and key components:

- The input images are of size (256, 256, 3).
- The model consists of several stages, each involving convolutional layers, batch normalization, and activation functions.
- Max pooling is applied to downsample the feature maps and capture hierarchical features.
- Residual blocks are used to enable the model to learn and propagate features effectively.
- Upsampling is performed to restore the spatial resolution of the feature maps.
- Concatenation is employed to fuse features from different stages and aid in accurate segmentation.

## Loss Function and Evaluation Metric

The model's loss function was the Focal Tversky loss, which combines the Tversky index with a focal factor to emphasize harder-to-segment regions. The Tversky index was also used as the evaluation metric. 

## Training Details
The model was trained for up to 200 epochs; however, training stopped at epoch 148 due to early stopping. At that point, the model achieved the following results on the validation data:

- Loss: 0.1547
- Tversky: 0.9165
- Validation Loss: 0.1824
- Validation Tversky: 0.8964
- Learning Rate: 8.0000e-06

## Test Performance
On the test dataset, the segmentation Tversky index was measured to be 86.61%, demonstrating the model's ability to accurately segment brain tumors in previously unseen data.

## Dataset
The training dataset consists of 3929 MRI images, out of which 1373 images are accompanied by masked tumor images. This dataset is used to train the ResUNET model for brain tumor segmentation.

## Acknowledgments
This project was inspired by the need for accurate and efficient brain tumor segmentation techniques. We acknowledge the contributions of the open-source community and the research community for providing valuable resources and insights.
