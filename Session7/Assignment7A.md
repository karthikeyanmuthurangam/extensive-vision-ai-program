## Assignment 7A

### Receptive Field Calculation for GoogLeNet

https://arxiv.org/pdf/1409.4842.pdf

![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session7/Receptive%20Field%20Calculation.png "Receptive Field Calculation Formula")

#### Observations

1. Padding for GoogLeNet is not provided in the "GoogLeNet incarnation of the Inception architecture Table". So padding is calculated using the below formula
![alt text](https://github.com/karthikeyanmuthurangam/extensive-vision-ai-program/blob/master/Session7/padding-calculation-formula.png "Padding Calculation Formula")

2. In Inception block, Receptive Field varies across each block but **Maximum Receptive Field is carried over to the next layer**
