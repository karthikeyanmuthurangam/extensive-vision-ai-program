### What are Channels and Kernels (according to EVA)?

In Image Processing, **kernel or filter** is used to *detect useful features* from an image. Applying multiple filters on an input image helps extract more features about an image.  

Smaller size kernels are more efficient and usually odd value such as 1x1, 3x3, 5x5 are used. 

More kernels can be used to extract more features from an input image. The size of the filter and the number of filters determine the quality of the features derived and the performance of a neural network. 

Bigger the size of the filter and the number of filters, bigger the number of parameters that needs to be derived by neural networks

##### Sample Kernels

###### Blur

![Blur Kernel](http://aishack.in/static/img/tut/conv-simple-blur.jpg "Blur Kernel")



###### Edge Detection

![Edge Detection](http://aishack.in/static/img/tut/conv-edge-detection.jpg "Edge Detection")

### Why should we only (well mostly) use 3x3 Kernels?

Typically smaller kernels are preferred over the larger kernels because

Applying 5*5 kernel once, uses 25 (5*5) weights but applying 3*3 kernel twice uses only 18 (3*3 + 3*3) to get to the same final output

* Needing lower number of weights to get to the same final output makes it computationally efficient. 
* Need for a multiple smaller layer makes it easy to learn complex, more features.

Few of the smaller kernels choices are

1. 1*1
2. 2*2
3. 3*3
4. 4*4

#### 1*1 Kernels


Features extracted by the kernel would be local and doesn't consider neighboring pixels, so 1*1 is not used 

#### 2*2 & 4*4 Kernels
Even sized filters are not prefered because the final output pixel that was obtained by convolving on the previous layer pixels will not be symmetrical leading to distortions across the layers

#### 3*3 Kernels

3*3 kernel is a smallest odd kernel which has lower number of weights making it computationally efficient and learns the complex features without any distortions

### How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations)
