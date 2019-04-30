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

### How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations)
