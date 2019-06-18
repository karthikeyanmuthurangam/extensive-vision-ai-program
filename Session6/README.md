# The CIFAR-10 dataset

The CIFAR-10 dataset consists of 60000 32x32 colour images in 10 classes, with 6000 images per class. There are 50000 training images and 10000 test images. 

## Assignment 6A

#### Base Network

After training the CIFAR-10 network for 100 epochs, achieved **83.51 Validation accuracy** with the following hyper parameters


|Hyperparameter Name| Hyperparameter Value|
|-------------------|---------------------|
|No. of Parameters| 1,172,410|
|No. of Epochs| 100 |
|Batch Size| 128|

#### Accuracy & Loss Plot

![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session6/Base%20Network.png "Accuracy & Loss Plot")

#### Modified Network

CIFAR-10 Modified network contains the below changes

1. Dense layer removed
2. Added layers required to reach RF
3. Fixed kernel scaleup and down (1x1)
4. Optimal Dropouts placements

After training the CIFAR-10 network for 100 epochs using the modified network, achieved **86.19 Validation accuracy** with the following hyper parameters

|Hyperparameter Name| Hyperparameter Value|
|-------------------|---------------------|
|No. of Parameters| 664,330|
|No. of Epochs| 100 |
|Batch Size| 128|

#### Accuracy & Loss Plot

![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session6/Modified%20Network.png "Accuracy & Loss Plot")

## Assignment 6B

#### Functional API Network

CIFAR-10 Functional API Network contains the below changes

1. Normal Convolution
2. Spatially Separable Convolution  (Conv2d(x, (3,1)) followed by Conv2D(x,(3,1))
3. Depthwise Separable Convolution
4. Grouped Convolution (use 3x3, 5x5 only)
5. Grouped Convolution (use 3x3 only, one with dilation = 1, and another with dilation = 2) 

After training the CIFAR-10 Functional API network for 50 epochs, achieved **80.71 Validation accuracy** with the following hyper parameters

|Hyperparameter Name| Hyperparameter Value|
|-------------------|---------------------|
|No. of Parameters| 684,330|
|No. of Epochs| 50 |
|Batch Size| 128|

#### Model Summary

![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session6/functional-api-model.png "Model Summary")

#### Accuracy & Loss Plot

![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session6/Functional%20API%20Network.png "Accuracy & Loss Plot")
