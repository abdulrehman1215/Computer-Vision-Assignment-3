# Semantic Segmentation
## Abstract:
In this task I have implemented 2 semantic segmentation models and compared their results. The aim of this report is to compare both the semantic segmentation models on the basis of Mean Intersection over union score results. The first model is a U-Net baseline with VGG 19 backbone while the second model is a U-Net baseline with a Mobile Net backbone.
## Introduction:
	
  Semantic segmentation is a computer vision task that involves dividing an image into meaningful and coherent regions, where each pixel is assigned a specific class label representing the object or the background it belongs to. Unlike traditional image classification which assigns a single label to an entire image, semantic segmentation aims to provide a detailed understanding of the scene by segmenting it into fine-grained regions.
The goal of semantic segmentation is to achieve pixel-level accuracy in assigning class labels, enabling machines to comprehend and interpret visual information at a granular level. It goes beyond simple object detection or instance segmentation, as it considers the entire image and labels every pixel according to its semantic category, such as people, cars, buildings, roads, trees, and so on.
Semantic segmentation is widely used in various applications, including autonomous driving, medical image analysis, robotics, video surveillance, and augmented reality. It plays a vital role in enabling machines to understand visual scenes, allowing for more advanced and intelligent decision-making based on pixel-wise classification.
### U Net Architecture:

The U-Net is a convolutional neural network (CNN) architecture that was specifically designed for semantic segmentation tasks. It was proposed by Olaf Ronneberger, Philipp Fischer, and Thomas Brox in 2015, and has since become one of the most popular and effective models for semantic segmentation.
The U-Net architecture is characterized by its U-shaped structure, consisting of an encoder and a decoder. The encoder part follows the typical structure of a CNN, where convolutional and pooling layers are used to progressively downsample the input image, extracting high-level features and capturing spatial information. The decoder part, on the other hand, upsamples the feature maps back to the original input resolution, allowing for precise localization and segmentation.
One of the key features of U-Net is its skip connections, which are connections between corresponding layers in the encoder and decoder. These skip connections provide a shortcut for the network to transfer low-level spatial information from the encoder to the decoder. This helps the decoder to recover fine-grained details and improve the segmentation accuracy, especially for small objects or regions.
The U-Net architecture has been widely used and adapted in various applications, demonstrating its effectiveness in semantic segmentation tasks. Its versatility and ability to handle different image sizes and aspect ratios make it suitable for a wide range of tasks, including biomedical image segmentation, satellite imagery analysis, and natural scene understanding.
Overall, the U-Net architecture has significantly contributed to the advancement of semantic segmentation by providing an efficient and effective framework for pixel-wise classification and accurate segmentation of objects in images.

![Figure 1: Unet Architecture For Semantic Segmentation](https://miro.medium.com/v2/resize:fit:1400/1*f7YOaE4TWubwaFF7Z1fzNw.png)

### VGG 19:

VGG19 is a convolutional neural network architecture that was introduced by the Visual Geometry Group (VGG) at the University of Oxford. It was developed by Karen Simonyan and Andrew Zisserman in 2014 and is an extension of the VGG16 architecture.
VGG19 is known for its simplicity and effectiveness in image classification tasks. It consists of 19 layers, including 16 convolutional layers, which are followed by fully connected layers. The convolutional layers primarily use 3x3 filters with a stride of 1 and padding of 1, and they are stacked together to form deeper representations. The pooling layers, which are usually max pooling layers with a 2x2 filter and a stride of 2, are used for downsampling and spatial feature reduction.
One of the notable characteristics of VGG19 is its homogeneous architecture. It utilizes a consistent design pattern, where multiple 3x3 convolutional layers are stacked together before each pooling layer. This approach allows for more abstract and hierarchical feature extraction, capturing both low-level and high-level information in the image.
VGG19 is often pre-trained on large-scale image classification datasets, such as ImageNet, and can be fine-tuned or used as a feature extractor for various computer vision tasks, including object detection, semantic segmentation, and image generation. Its deep architecture and large number of parameters make it capable of learning complex patterns and representations from images.
While VGG19 has been widely adopted and achieved impressive performance in image classification tasks, its main drawback is its computational cost and memory requirements. The depth and number of parameters make it slower and more resource-intensive compared to some newer architectures. However, VGG19 remains a popular choice for benchmarking and serves as a baseline for comparison in many computer vision research studies.

![Figure: 2VGG 19 Architecture](https://github.com/abdulrehman1215/Computer-Vision-Assignment-3/blob/images/vgg19.jpeg)

### Mobile Net V2:

MobileNetV2 is a lightweight convolutional neural network architecture designed specifically for efficient mobile and embedded devices. It was developed by Andrew G. Howard, Menglong Zhu, Bo Chen, Dmitry Kalenichenko, Weijun Wang, Tobias Weyand, Marco Andreetto, and Hartwig Adam at Google in 2018.
MobileNetV2 improves upon its predecessor, MobileNetV1, by introducing several key features. One significant enhancement is the use of inverted residual blocks, which consist of a lightweight bottleneck layer followed by an expansion layer. This design reduces computational complexity while maintaining representation power. Additionally, linear bottlenecks and shortcut connections within the network help preserve information flow and gradient propagation.
MobileNetV2 also introduces a parameter called the width multiplier, which allows users to control the model's resource usage. By adjusting this parameter, the model's width can be scaled, trading off between accuracy and efficiency to meet specific device constraints.
The architecture of MobileNetV2 has been extensively optimized for mobile devices, achieving a good balance between accuracy and efficiency. It has been widely adopted in various applications, including object detection, image classification, and semantic segmentation. Its lightweight nature makes it well-suited for deployment on resource-constrained devices, where computational power and memory limitations are a concern.
In summary, MobileNetV2 is a state-of-the-art neural network architecture that enables efficient and accurate deep learning on mobile and embedded devices. Its innovations, such as inverted residual blocks and width multiplier, contribute to its effectiveness in achieving high-performance inference while minimizing computational requirements.

![Figure 3: Mobile Net V2 Architecture](https://github.com/abdulrehman1215/Computer-Vision-Assignment-3/blob/images/mobilenet%20v2.png)

## Transfer Learning details:

In this study, transfer learning was employed to leverage the prebuilt models available in PyTorch with pre-trained weights from the ImageNet dataset. Training custom models from scratch was deemed impractical due to the extensive computational power and resources required. Instead, the models used in this research were based on the Unet architecture, serving as baselines with different backbones.
The first model utilized the VGG19 backbone, which is a well-established convolutional neural network architecture. By incorporating the VGG19 backbone into the Unet framework, the model could benefit from the rich representations learned from large-scale image classification tasks.
The second model employed the MobileNet v2 backbone, which is specifically designed for efficient mobile and embedded devices. By leveraging the lightweight and resource-efficient nature of MobileNet v2, the Unet-based model achieved a good balance between accuracy and efficiency, making it suitable for deployment on resource-constrained devices.
Both models were trained using Google Colab, which provided the necessary computational resources for training deep learning models. By utilizing pre-trained weights from ImageNet, the models could leverage the learned features and generalize well to new datasets, reducing the need for extensive training on the specific task at hand.

## U-Net with VGG 19 Results:
### Training and Validation graphs:
The graph for accuracy is as follows:

![Figure 4: Training and validation Accuracies with VGG 19 backbone](https://github.com/abdulrehman1215/Computer-Vision-Assignment-3/blob/images/vgg%20accuracy.png)

The graph for Loss is as follows:

![Figure 5: Training and Validation Loss for VGG 19 Architecture](https://github.com/abdulrehman1215/Computer-Vision-Assignment-3/blob/images/vgg%20Loss.png)

The graph for Mean Intersection Over Union is as follows:

![Figure 6: Mean intersention Over Union For traning and validation using VGG 19 backbone](https://github.com/abdulrehman1215/Computer-Vision-Assignment-3/blob/images/vgg%20Miou.png)

### Test Set MIoU:

The Mean Intersection over Union for test set was 0.45

### Semantic Segmentation Results:

Here are the results of semantic segmentation on some randomly picked images from test dataset:

![Figure 7: VGG backbone with 0.47 MIoU](https://github.com/abdulrehman1215/Computer-Vision-Assignment-3/blob/images/0.47%20VGG.png)

![Figure 8: VGG backbone eith 0.39 MIoU](https://github.com/abdulrehman1215/Computer-Vision-Assignment-3/blob/images/0.39%20VGG.png)

![Figure 9: VGG Backbone with 0.42 MIoU](https://github.com/abdulrehman1215/Computer-Vision-Assignment-3/blob/images/0.42%20VGG.png)

## U-Net with VGG 19 Results:

### Training and Validation graphs:

The graph for accuracy is as follows:

![Figure 10: Training and validation Accuracies with Mobile Net V2 backbone](https://github.com/abdulrehman1215/Computer-Vision-Assignment-3/blob/images/mob%20accuracy.png)

The graph for Loss is as follows:

![Figure 11:Training and validation Loss MobileNet V2 architecture](https://github.com/abdulrehman1215/Computer-Vision-Assignment-3/blob/images/mob%20Loss.png)

The graph for Mean Intersection Over Union is as follows:

![Figure 12: MIoU for Training and Validation](https://github.com/abdulrehman1215/Computer-Vision-Assignment-3/blob/images/mob%20Miou.png)

### Test Set MIoU:

The Mean Intersection over Union for test set was 0.46

### Semantic Segmentation Results:

Here are the results of semantic segmentation on some randomly picked images from test dataset:

![Figure 13: MobileNet V2 Backbone with 0.5 MIoU](https://github.com/abdulrehman1215/Computer-Vision-Assignment-3/blob/images/0.5%20mob.png)

![Figure 14: MobileNet V2 backbone with 0.48 MIoU](https://github.com/abdulrehman1215/Computer-Vision-Assignment-3/blob/images/0.48%20mob.png)

![Figure 15:MobileNet V2 backbone with 0.45 MIoU](https://github.com/abdulrehman1215/Computer-Vision-Assignment-3/blob/images/0.45%20mob.png)

## Conclusion:

In this learning task, I have successfully implemented 2 semantic segmentation architectures and through the quantitative and qualitative results we can conclude that the semantic segmentation model consisting U-Net baseline and MobileNet v2 backbone performed better than U-net baseline and VGG 19 backbone.
