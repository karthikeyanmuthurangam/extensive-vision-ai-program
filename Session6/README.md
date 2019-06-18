## Assignment 6A

The CIFAR-10 dataset

The CIFAR-10 dataset consists of 60000 32x32 colour images in 10 classes, with 6000 images per class. There are 50000 training images and 10000 test images. 

After training the CIFAR-10 network for 100 epochs, achieved 83.51 Validation accuracy with the following hyper parameters


|Hyperparameter Name| Hyperparameter Value|
|-------------------|---------------------|
|No. of Parameters| 1,172,410|
|No. of Epochs| 100 |
|Batch Size| 128|

#### Accuracy & Loss Plot


After applying the below changes
1. Remove dense
2. Add layers required to reach RF
3. Fix kernel scaleup and down (1x1)
4. Dropouts placements

After training the CIFAR-10 network for 100 epochs, achieved 83.99 Validation accuracy at 25th epoch with the following hyper parameters

|Hyperparameter Name| Hyperparameter Value|
|-------------------|---------------------|
|No. of Parameters| 664,330|
|No. of Epochs| 100 |
|Batch Size| 128|

#### Accuracy & Loss Plot

