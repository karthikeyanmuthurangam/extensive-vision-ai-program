## MNIST Convolution Neural Network Model - 1 (Session_4_First.ipynb)

Achieved **99.1 Validation accuracy** with the following hyper parameters

|Hyperparameter Name| Hyperparameter Value|
|-------------------|---------------------|
|No. of Parameters| 21,956|
|No. of Epochs| 10 |
|Batch Size| 32|

![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session4/experiments/experiment%2312/model-code.png "Model Code")

#### Accuracy & Loss Plot
![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session4/experiments/experiment%2312/accuracy-loss-plot.png "Accuracy & Loss Plot")

#### Concepts Used
1. 3x3 Convolutions 
2. 1x1 Convolutions
3. MaxPooling
4. SoftMax


### Observations

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

##### 1x1
- 1x1 or Feature Merger helps in getting the best of all the channels. It didn't help in improve the accuracy in case of the MNIST dataset  

## MNIST Convolution Neural Network Model - 2 (Session_4_Second.ipynb)

Achieved **99.42 Validation accuracy** with the following hyper parameters

|Hyperparameter Name| Hyperparameter Value|
|-------------------|---------------------|
|No. of Parameters| 10,676|
|No. of Epochs| 10 |
|Batch Size| 64|

![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session4/experiments/experiment%2332/model-code.png "Model Code")

### Accuracy & Loss Plot
![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session4/experiments/experiment%2332/accuracy-loss-plot.png "Accuracy & Loss Plot")

#### Concepts Used
1. Batch Normalization
2. DropOut

#### Observations
- 

## MNIST Convolution Neural Network Model - 3 (Session_4_Third.ipynb)

Achieved **99.34 Validation accuracy** with the following hyper parameters

|Hyperparameter Name| Hyperparameter Value|
|-------------------|---------------------|
|No. of Parameters| 10,676|
|No. of Epochs| 10 |
|Batch Size| 64|

![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session4/experiments/experiment%2335/model-code.png "Model Code")

#### Accuracy & Loss Plot
![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session4/experiments/experiment%2335/accuracy-loss-plot.png "Accuracy & Loss Plot")

#### Concepts Used
1. Learning Rate

#### Observations

## MNIST Convolution Neural Network Model - 4 (Session_4_Fourth.ipynb)

Achieved **99.42 Validation accuracy** with the following hyper parameters

|Hyperparameter Name| Hyperparameter Value|
|-------------------|---------------------|
|No. of Parameters| 9,822|
|No. of Epochs| 30 |
|Batch Size| 64|

#### Model Code
![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session4/experiments/experiment%2334/model-code.png "Model Code")

#### Accuracy & Loss Plot
![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session4/experiments/experiment%2334/accuracy-loss-plot.png "Accuracy & Loss Plot")

#### Concepts Used
1. Batch Size
2. No. of epochs

#### Observations
