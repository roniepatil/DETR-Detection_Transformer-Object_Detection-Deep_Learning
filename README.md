
# DETR (Detection Transformer)

## 1. Introduction to DETR
### Overview
DETR revolutionizes object detection by integrating a transformer model, traditionally used in natural language processing, into the realm of computer vision. It simplifies the object detection pipeline by eliminating the need for many hand-designed components.

### Motivation
DETR addresses the complexity and inefficiencies of prior object detection systems, offering a streamlined and theoretically elegant approach.

## 2. DETR Architecture

![alt text](https://github.com/roniepatil/DETR-Detection_Transformer-Object_Detection-Deep_Learning/blob/main/DETR.jpg)


### Overall Structure
DETR combines a Convolutional Neural Network (CNN) backbone with a transformer model. The CNN extracts features from input images, and the transformer processes these features to predict object classes and bounding boxes.

## 3. Key Components of DETR
### CNN Backbone
Extracts feature maps from the input image. Commonly, ResNet is used for this purpose.

### Transformer Encoder-Decoder
#### Encoder
Processes the feature map from the CNN. It consists of self-attention and feed-forward layers.

#### Decoder
Generates object queries. Each query predicts an object in the image, using cross-attention with the encoder's output.

### Feed-Forward Networks
These networks predict the final class and bounding box for each object query.

## 4. DETR Parameters and Configurations
### Model Parameters
Key parameters include the number of encoder and decoder layers, attention heads, and feed-forward network dimensions. DETR is trained with standard backpropagation using AdamW optimizer, learning rate scheduling, and a custom loss function. Techniques like dropout and layer normalization are used for stable training.

## 5. Working of DETR
### Object Detection Process
DETR treats object detection as a set prediction problem. Each decoder output corresponds to a prediction of an object.

### Sequence Modeling
The model processes the entire set of objects at once, in parallel, unlike traditional methods that process objects sequentially.

### Bipartite Matching and Loss Calculation
DETR uses the Hungarian algorithm for matching predicted and ground truth objects, calculating a combined loss of classification and bounding box regression.

## 6. Advantages and Limitations
### Advantages
Simplifies the object detection pipeline, handles occlusions and overlapping objects well, and is end-to-end trainable.

### Limitations
DETR can be slower to train due to the global nature of self-attention and might struggle with very small objects.


### References
(https://github.com/facebookresearch/detr)
