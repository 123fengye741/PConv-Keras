# Keras-Inpainting
Keras implementation of "Image Inpainting for Irregular Holes Using Partial Convolutions", https://arxiv.org/abs/1804.07723. A huge shoutout the authors Guilin Liu, Fitsum A. Reda, Kevin J. Shih, Ting-Chun Wang, Andrew Tao and Bryan Catanzaro from NVIDIA corporation for releasing this awesome paper, it's been a great learning experience for me to implement the architecture, and it would not have been possible had it not been for their well communicated paper. 

# Dependencies
* Python 3.6
* Keras 2.2.0
* Tensorflow 1.8

# How to use this repository
The primary implementations of the new `PConv2D` keras layer as well as the `UNet`-like architecture using these partial convolutional layers can be found in `libs/pconv.py` - this is where the bulk of the implementation can be found. Beyond this I've set up four jupyter notebooks, which details the several steps I went through while implementing the network, namely:

Step 1: Creating random irregular masks
Step 2: Implementing and testing the implementation of the `PConv2D` layer
Step 3: Implementing and testing the UNet architecture with `PConv2D` layers
Step 4: Training & testing the final architecture on ImageNet

# Implementation details
The best summary of the implementation itself can be found in the [paper itself](https://arxiv.org/abs/1804.07723), however I'll try to summarize it here as well for clarity.

## Mask Creation
In the paper they use a technique based on occlusion/dis-occlusion between two consecutive frames in videos for creating random irregular masks - instead I've opted for simply creating a simple mask-generator function which uses OpenCV to draw some random irregular shapes which I then use for masks. Plugging in a new mask generation technique later should not be a problem though, and I think the end results are pretty decent using this method as well.

## Partial Convolution Layer
A key element in this implementation is the partial convolutional layer. Basically, given the convolutional filter **W** and the corresponding bias *b*, the following partial convolution is applied instead of a normal convolution:



NotImplementedError()

## UNet Architecture
NotImplementedError()

## Loss Function(s)
NotImplementedError()

## Training Procedure
NotImplementedError()
