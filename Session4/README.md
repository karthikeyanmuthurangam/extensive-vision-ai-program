- [MNIST Convolution Neural Network Model - 1](#mnist-convolution-neural-network-model---1-session_4_firstipynb)
  * [Model Code](#model-code)
  * [Accuracy & Loss Plot](#accuracy--loss-plot)
  * [Concepts Used](#concepts-used)
  * [Observations](#observations)
- [MNIST Convolution Neural Network Model - 2](#mnist-convolution-neural-network-model---2-session_4_secondipynb)
  * [Model Code](#model-code-1)
  * [Accuracy & Loss Plot](#accuracy--loss-plot-1)
  * [Concepts Used](#concepts-used-1)
  * [Observations](#observations-1)
- [MNIST Convolution Neural Network Model - 3](#mnist-convolution-neural-network-model---3-session_4_thirdipynb)
  * [Model Code](#model-code-2)
  * [Accuracy & Loss Plot](#accuracy--loss-plot-2)
  * [Concepts Used](#concepts-used-2)
  * [Observations](#observations-2)
- [MNIST Convolution Neural Network Model - 4](#mnist-convolution-neural-network-model---4-session_4_fourthipynb)
  * [Model Code](#model-code-3)
  * [Accuracy & Loss Plot](#accuracy--loss-plot-3)
  * [Concepts Used](#concepts-used-3)
  * [Observations](#observations-3)
  
## MNIST Convolution Neural Network Model - 1 (Session_4_First.ipynb)

Achieved **99.1 Validation accuracy** with the following hyper parameters

|Hyperparameter Name| Hyperparameter Value|
|-------------------|---------------------|
|No. of Parameters| 21,956|
|No. of Epochs| 10 |
|Batch Size| 32|

#### Model Code

```
from keras.layers import Activation
model = Sequential()

 
model.add(Convolution2D(16, 3, 3, activation='relu', input_shape=(28,28,1)))
model.add(Convolution2D(16, 3, 3, activation='relu')) #26
model.add(MaxPooling2D(pool_size=(2,2))) #12
model.add(Convolution2D(16, 3, 3, activation='relu')) #10
model.add(Convolution2D(16, 3, 3, activation='relu')) #8
model.add(Convolution2D(16, 3, 3, activation='relu')) #6
model.add(Convolution2D(10, 6))
model.add(Flatten())
model.add(Activation('softmax'))
```

#### Accuracy & Loss Plot
![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session4/experiments/experiment%2312/accuracy-loss-plot.png "Accuracy & Loss Plot")

#### Concepts Used
1. 3x3 Convolutions 
2. 1x1 Convolutions
3. MaxPooling
4. SoftMax


#### Observations

- Building a simple Neural Network model using the basic building block of CNN (Convolution, Pooling, Activation) and incrementally adding the right convolution/transition block at the right layer helps in the understanding the model better
- Validation accuracy is always less than the training accuracy

##### Number of kernels
- Number of kernels depends on the input image size, accuracy required and the resources available (GPU)
- Small number of kernels (<=16) are good enough to train the MNIST dataset
- Large number of kernels overfits the model on the training data leading to very high training accuracy but does not really have high accuracy on the validation data

##### Validation Checks

- Adding Validation Check helped understand, how the model is performing very early

#### MaxPooling

- Maxpooling reduced the number of parameters for next layer and computation in the network
- Ideally Maxpooling should be positioned 2 convolution layer after the input and 2 convolution layer before the output (prediction) layer

##### Position of MaxPooling

- Maxpooling should be positioned after 2-3 convolution layers from the input layer to allow the model to extract a rich set of features before extracting the prominent features

##### Distance of MaxPooling from Prediction
- Maxpooling should not be positioned before the output layer because full image has been seen by the network, dropping any features at this point leads to missing some information on the input data

##### 3x3

3x3 helped in reducing the number of parameters and computation of the network (compared to large kernels like 5x5, 7x7, 9x9)

##### 1x1
- 1x1 or Feature Merger helps in getting the best of all the channels. It didn't help in improve the accuracy in case of the MNIST dataset  

## MNIST Convolution Neural Network Model - 2 (Session_4_Second.ipynb)

Achieved **99.42 Validation accuracy** with the following hyper parameters

|Hyperparameter Name| Hyperparameter Value|
|-------------------|---------------------|
|No. of Parameters| 10,676|
|No. of Epochs| 10 |
|Batch Size| 64|

### Model Code

```
from keras.layers import Activation
model = Sequential()

# Convolution Block 
model.add(Convolution2D(16, 3, 3, activation='relu', input_shape=(28,28,1)))
model.add(BatchNormalization())
model.add(Convolution2D(32, 3, 3, activation='relu')) #24
model.add(BatchNormalization())
model.add(Dropout(0.1))

# Transition Block
model.add(MaxPooling2D(pool_size=(2,2))) #12
model.add(Convolution2D(10, 1, 1, activation='relu')) #12
# Convolution Block

model.add(Convolution2D(16, 3, 3, activation='relu')) #10
model.add(BatchNormalization())
model.add(Dropout(0.2))

model.add(MaxPooling2D(pool_size=(2,2))) #5

model.add(Convolution2D(16, 3, 3, activation='relu')) #2
model.add(BatchNormalization())
model.add(Dropout(0.2))

model.add(Convolution2D(10, 3))
model.add(Flatten())
model.add(Activation('softmax'))
```

### Accuracy & Loss Plot
![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session4/experiments/experiment%2332/accuracy-loss-plot.png "Accuracy & Loss Plot")

#### Concepts Used
1. Batch Normalization
2. DropOut
3. Batch Size

#### Observations

##### Batch Normalization
- Batch Normalization helps in avoing exploding gradient or vanishing gradient problem
- Placing the Batch Normalization before or after the Convolution doesn't make any significant change in the accuracy
- Should not be placed before the prediction layer as it will alter the output predictions

##### Dropout

- Dropout helps in reducing overfitting and the gap between the training and validation accuracy
- Dropout of < 0.3 for this mdoel increases the accuracy and anything > 0.3 doesn't show any improvement in accuracy, actually reduces the accuracy

##### Batch Size
- Increasing the batch size from 32 to 64 has increased the validation accuracy and increasing it any further (>64) is not having any impact on the model accuracy

## MNIST Convolution Neural Network Model - 3 (Session_4_Third.ipynb)

Achieved **99.34 Validation accuracy** with the following hyper parameters

|Hyperparameter Name| Hyperparameter Value|
|-------------------|---------------------|
|No. of Parameters| 10,676|
|No. of Epochs| 10 |
|Batch Size| 64|

#### Model Code

```
from keras.layers import Activation
model = Sequential()

# Convolution Block 
model.add(Convolution2D(16, 3, 3, activation='relu', input_shape=(28,28,1)))
model.add(BatchNormalization())
model.add(Convolution2D(32, 3, 3, activation='relu')) #24
model.add(BatchNormalization())
model.add(Dropout(0.1))

# Transition Block
model.add(MaxPooling2D(pool_size=(2,2))) #12
model.add(Convolution2D(10, 1, 1, activation='relu')) #12
# Convolution Block

model.add(Convolution2D(16, 3, 3, activation='relu')) #10
model.add(BatchNormalization())
model.add(Dropout(0.2))

model.add(MaxPooling2D(pool_size=(2,2))) #5

model.add(Convolution2D(16, 3, 3, activation='relu')) #2
model.add(BatchNormalization())
model.add(Dropout(0.2))

model.add(Convolution2D(10, 3))
model.add(Flatten())
model.add(Activation('softmax'))
```

#### Accuracy & Loss Plot
![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session4/experiments/experiment%2335/accuracy-loss-plot.png "Accuracy & Loss Plot")

#### Concepts Used
1. Learning Rate

#### Observations

##### Learning Rate
- Learning Rate helps in faster network convergence. 
- Default learning Rate of the Adam optimizer is 0.001, increasing it to 0.003 and decreasing the learning rate with respect to the epoch has helped in improving the accuracy
- Higher learning rate (> 0.004) has been improving the accuracy significantly in this model.

## MNIST Convolution Neural Network Model - 4 (Session_4_Fourth.ipynb)

Achieved **99.42 Validation accuracy** with the following hyper parameters

|Hyperparameter Name| Hyperparameter Value|
|-------------------|---------------------|
|No. of Parameters| 9,822|
|No. of Epochs| 30 |
|Batch Size| 64|

#### Model Code

```from keras.layers import Activation
model = Sequential()

# Convolution Block 
model.add(Convolution2D(16, 3, 3, activation='relu', input_shape=(28,28,1)))
model.add(BatchNormalization())
model.add(Convolution2D(32, 3, 3, activation='relu')) #24
model.add(BatchNormalization())
model.add(Dropout(0.1))

# Transition Block
model.add(MaxPooling2D(pool_size=(2,2))) #12
model.add(Convolution2D(10, 1, 1, activation='relu')) #12
# Convolution Block

model.add(Convolution2D(16, 3, 3, activation='relu')) #10
model.add(BatchNormalization())
model.add(Dropout(0.2))

model.add(MaxPooling2D(pool_size=(2,2))) #5

model.add(Convolution2D(16, 3, 3, activation='relu')) #2
model.add(BatchNormalization())
model.add(Dropout(0.2))

model.add(Convolution2D(10, 3))
model.add(Flatten())
model.add(Activation('softmax'))
```

#### Accuracy & Loss Plot
![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session4/experiments/experiment%2334/accuracy-loss-plot.png "Accuracy & Loss Plot")

#### Concepts Used
1. No. of epochs

#### Observations

##### No. of epochs
- Increasing epochs from 10 to 30 has shown improvement in the training as well as validation accuracy. 
