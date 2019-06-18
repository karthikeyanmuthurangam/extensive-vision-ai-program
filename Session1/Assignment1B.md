### What are Channels and Kernels (according to EVA)?

#### Channels

Below is the list of convolutions and the data on which it is applied

1. 1D Convolutions to 1 dimensional data (temporal)
2. 2D Convolutions to 2 dimensional data (height and width)
3. 3D Convolutions to 3 dimensional data (height, width and depth)

Our input data usually defines multiple variables at each position (through time, or space), and not just a single value. This is called **channels**.

Channels are representation of a view of the image as a whole, emphasising some aspects, de-emphasising others.

<ins>RGB image with three channels<ins>
  
![RGB Image with 3 channels](https://cdn-images-1.medium.com/max/2400/1*k8P28Ayl-5hOqIMSv-qosw.jpeg "RGB images with three channels")


<ins>Input Channel<ins>
  
When the input data contains multiple channels, we need to construct a convolution kernel with the same number of input channels as the input data, so that it can perform cross-correlation with the input data. 

For example if the input data contains three channels (100x100x3) images, the kernel should also have 3 channels (3x3x3)

<ins>Output Channel<ins>
  
Each filter in a convolution layer produces one and only one output channel.

Sometimes we actually increase the channel dimension as we go higher up in the neural network for greater channel depth

#### Kernels

In Image Processing, **kernel or filter** is used to *detect useful features* from an image. Applying multiple filters on an input image helps extract more features about an image.  

Smaller size kernels are more efficient and usually odd value such as 1x1, 3x3, 5x5 are used. 

More kernels can be used to extract more features from an input image. The size of the filter and the number of filters determine the quality of the features derived and the performance of a neural network. 

Bigger the size of the filter and the number of filters, bigger the number of parameters that needs to be derived by neural networks

<ins>Sample Kernels<ins>

<ins>Blur<ins>

![Blur Kernel](http://aishack.in/static/img/tut/conv-simple-blur.jpg "Blur Kernel")

![](https://upload.wikimedia.org/wikipedia/commons/0/04/Vd-Blur2.png)

<ins>Edge Detection<ins>

![Edge Detection](http://aishack.in/static/img/tut/conv-edge-detection.jpg "Edge Detection")

![](https://upload.wikimedia.org/wikipedia/commons/6/6d/Vd-Edge3.png)

### Why should we only (well mostly) use 3x3 Kernels?

Typically smaller kernels are preferred over the larger kernels in the Convolution Neural Network (CNN)

Applying 5x5 kernel once, uses 25 (5x5) weights but applying 3x3 kernel twice uses only 18 (3x3 + 3x3) to get to the same final output

<ins>Adavantages of small kernels<ins>

* Need for lower number of weights to get to the same final output makes it computationally efficient. 
* Need for a multiple smaller layer makes it easy to learn more complex features.

Below are the available small kernels choices

1. 1x1
2. 2x2
3. 3x3
4. 4x4

<ins>1x1 Kernels<ins>


Features extracted by the kernel would be local and doesn't consider neighboring pixels, so 1x1 is not used 

<ins>2x2 & 4x4 Kernels<ins>
  
Even sized filters are not prefered because the final output pixel that was obtained by convolving on the previous layer pixels will not be symmetrical leading to distortions across the layers

<ins>3x3 Kernels<ins>

3x3 kernel is a smallest odd kernel after 1x1 which has lower number of weights making it computationally efficient and learns the complex features without any distortions

##### Any size of the kernel can be achieved by 3x3. 

For example 5x5 kernel can be achieved by 2 3x3 kernels. 7x7 kernel can be achieved by 3 3x3 kernels. **This makes the 3x3 kernel more popular among other kernels**

### How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations)

|Step #|Input |Kernel|Output|
|------|------|------|------
|1|199x199|3x3|197x197|
|2|197x197|3x3|195x195|
|3|195x195|3x3|193x193|
|4|193x193|3x3|191x191|
|5|191x191|3x3|189x189|
|6|189x189|3x3|187x187|
|7|187x187|3x3|185x185|
|8|185x185|3x3|183x183|
|9|183x183|3x3|181x181|
|10|181x181|3x3|179x179|
|11|179x179|3x3|177x177|
|12|177x177|3x3|175x175|
|13|175x175|3x3|173x173|
|14|173x173|3x3|171x171|
|15|171x171|3x3|169x169|
|16|169x169|3x3|167x167|
|17|167x167|3x3|165x165|
|18|165x165|3x3|163x163|
|19|163x163|3x3|161x161|
|20|161x161|3x3|159x159|
|21|159x159|3x3|157x157|
|22|157x157|3x3|155x155|
|23|155x155|3x3|153x153|
|24|153x153|3x3|151x151|
|25|151x151|3x3|149x149|
|26|149x149|3x3|147x147|
|27|147x147|3x3|145x145|
|28|145x145|3x3|143x143|
|29|143x143|3x3|141x141|
|30|141x141|3x3|139x139|
|31|139x139|3x3|137x137|
|32|137x137|3x3|135x135|
|33|135x135|3x3|133x133|
|34|133x133|3x3|131x131|
|35|131x131|3x3|129x129|
|36|129x129|3x3|127x127|
|37|127x127|3x3|125x125|
|38|125x125|3x3|123x123|
|39|123x123|3x3|121x121|
|40|121x121|3x3|119x119|
|41|119x119|3x3|117x117|
|42|117x117|3x3|115x115|
|43|115x115|3x3|113x113|
|44|113x113|3x3|111x111|
|45|111x111|3x3|109x109|
|46|109x109|3x3|107x107|
|47|107x107|3x3|105x105|
|48|105x105|3x3|103x103|
|49|103x103|3x3|101x101|
|50|101x101|3x3|99x99|
|51|99x99|3x3|97x97|
|52|97x97|3x3|95x95|
|53|95x95|3x3|93x93|
|54|93x93|3x3|91x91|
|55|91x91|3x3|89x89|
|56|89x89|3x3|87x87|
|57|87x87|3x3|85x85|
|58|85x85|3x3|83x83|
|59|83x83|3x3|81x81|
|60|81x81|3x3|79x79|
|61|79x79|3x3|77x77|
|62|77x77|3x3|75x75|
|63|75x75|3x3|73x73|
|64|73x73|3x3|71x71|
|65|71x71|3x3|69x69|
|66|69x69|3x3|67x67|
|67|67x67|3x3|65x65|
|68|65x65|3x3|63x63|
|69|63x63|3x3|61x61|
|70|61x61|3x3|59x59|
|71|59x59|3x3|57x57|
|72|57x57|3x3|55x55|
|73|55x55|3x3|53x53|
|74|53x53|3x3|51x51|
|75|51x51|3x3|49x49|
|76|49x49|3x3|47x47|
|77|47x47|3x3|45x45|
|78|45x45|3x3|43x43|
|79|43x43|3x3|41x41|
|80|41x41|3x3|39x39|
|81|39x39|3x3|37x37|
|82|37x37|3x3|35x35|
|83|35x35|3x3|33x33|
|84|33x33|3x3|31x31|
|85|31x31|3x3|29x29|
|86|29x29|3x3|27x27|
|87|27x27|3x3|25x25|
|88|25x25|3x3|23x23|
|89|23x23|3x3|21x21|
|90|21x21|3x3|19x19|
|91|19x19|3x3|17x17|
|92|17x17|3x3|15x15|
|93|15x15|3x3|13x13|
|94|13x13|3x3|11x11|
|95|11x11|3x3|9x9|
|96|9x9|3x3|7x7|
|97|7x7|3x3|5x5|
|98|5x5|3x3|3x3|
|99|3x3|3x3|1x1|

##### We need to perform 99 times 3x3 convolution operation on 199x199 to reach 1x1
