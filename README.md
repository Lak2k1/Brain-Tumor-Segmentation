# Brain Tumor Segmentation using ResUNET

## Overview

This repository contains the implementation of a brain tumor segmentation model using the ResUNET architecture. The model is trained to segment brain tumors in MRI images, providing accurate and detailed tumor masks. The ResUNET architecture utilizes residual blocks, batch normalization, max pooling, upsampling, and concatenation to achieve state-of-the-art performance in segmentation tasks.

## Dataset
The [training dataset](https://www.kaggle.com/datasets/mateuszbuda/lgg-mri-segmentation) consists of 3929 MRI images, out of which 1373 images are accompanied by masked tumor images. This dataset is used to train the ResUNET model for brain tumor segmentation.

## Model Architecture

The ResUNET architecture is designed to effectively segment brain tumors in MRI images. Here's a brief overview of the model architecture and key components:

- The input images are of size (256, 256, 3).
- The model consists of several stages, each involving convolutional layers, batch normalization, and activation functions.
- Max pooling is applied to downsample the feature maps and capture hierarchical features.
- Residual blocks are used to enable the model to learn and propagate features effectively.
- Upsampling is performed to restore the spatial resolution of the feature maps.
- Concatenation is employed to fuse features from different stages and aid in accurate segmentation.
![Image explanation](https://github.com/Lak2k1/Brain-Tumor-Segmentation/blob/main/resunet1.png)



![Model explanation](https://github.com/Lak2k1/Brain-Tumor-Segmentation/blob/main/resunet2.PNG)

## Loss Function and Evaluation Metric

The model's loss function was the Focal Tversky loss, which combines the Tversky index with a focal factor to emphasize harder-to-segment regions. The Tversky index was also used as the evaluation metric. 
![](https://github.com/Lak2k1/Brain-Tumor-Segmentation/blob/main/Tversky%20Index.png)
The α and β parameters (α+β=1), they control the relative importance of false positives and false negatives when measuring the similarity between two binary masks. 
In my case where I've used α = 0.7, it means I've given more importance to false negatives compared to false positives when calculating the Tversky index.
While the tversky loss is defined as 1-tversky index.

## Training Details
The model was trained for up to 200 epochs; however, training stopped at epoch 148 due to early stopping. At that point, the model achieved the following results on the validation data:

- Loss: 0.1547
- Tversky: 0.9165
- Validation Loss: 0.1824
- Validation Tversky: 0.8964
- Learning Rate: 8.0000e-06
![](https://github.com/Lak2k1/Brain-Tumor-Segmentation/blob/main/tversky%20score%20and%20loss.png)

## Test Performance
On the test dataset, the segmentation Tversky index was measured to be 86.61%, demonstrating the model's ability to accurately segment brain tumors in previously unseen data.
![](https://github.com/Lak2k1/Brain-Tumor-Segmentation/blob/main/Segmentation%20tversky.png)

## Results
![](https://github.com/Lak2k1/Brain-Tumor-Segmentation/blob/main/result1.png)
![](https://github.com/Lak2k1/Brain-Tumor-Segmentation/blob/main/result2.png)
![](https://github.com/Lak2k1/Brain-Tumor-Segmentation/blob/main/result3.png)
![](https://github.com/Lak2k1/Brain-Tumor-Segmentation/blob/main/result4.png)
![](https://github.com/Lak2k1/Brain-Tumor-Segmentation/blob/main/result5.png)


## Acknowledgments
This project was inspired by the need for accurate and efficient brain tumor segmentation techniques. We acknowledge the contributions of the open-source community and the research community for providing valuable resources and insights.
