## Assignment 6A

### The CIFAR-10 dataset

The CIFAR-10 dataset consists of 60000 32x32 colour images in 10 classes, with 6000 images per class. There are 50000 training images and 10000 test images. 

#### Base Network

After training the CIFAR-10 network for 100 epochs, achieved 83.51 Validation accuracy with the following hyper parameters


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

After training the CIFAR-10 network for 100 epochs using the modified network, achieved 86.19 Validation accuracy epoch with the following hyper parameters

|Hyperparameter Name| Hyperparameter Value|
|-------------------|---------------------|
|No. of Parameters| 664,330|
|No. of Epochs| 100 |
|Batch Size| 128|

#### Accuracy & Loss Plot

![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session6/Modified%20Network.png "Accuracy & Loss Plot")
