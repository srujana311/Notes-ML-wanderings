# Convolutional Networks

Notes from [Introducing Convolutional Nets](http://neuralnetworksanddeeplearning.com/chap6.html#introducing_convolutional_networks):

In image classification, fully connected networks do not exploit the spatial structure of images. They treat pixels which are close/far apart on an equal footing. Conv Nets exploit the spatial structure in images. Further, their architecture makes them faster to train, paving the way for wide use of deep convolutional nets in image classification.

Convolutional neural networks use three basic ideas: local receptive fields, shared weights, and pooling.

- **Local receptive fields**: Instead of connecting each hidden neuron to all input neurons (as is the case in fully-connected architecture), each neuron in the first hidden layer is connected to a small region of (spatially adjacent) input neurons. 

![Image from neuralnetworksanddeeplearning.com](https%3A%2F%2Fgithub.com%2Fsrujana311%2FNotes-ML-wanderings%2Fblob%2Fmaster%2FImgs%2FLocal.png)

> For example, a small 5 x 5 region, corresponding to 25 pixels. That region in the input image is called the *local receptive field* for the hidden neuron. It's a little window on the input pixels. Each connection learns a weight. And the hidden neuron learns an overall bias as well. You can think of that particular hidden neuron as learning to analyze its particular local receptive field.

This particular window is slided across the whole image with a specified step size/stride length. Hence, each hidden neuron corresponds to a small local region of the input image, such that the hidden neurons together cover the entire image. 

- **Shared weights**: In a convolutional network, all the hidden neurons in a layer share the same weights. Intuitively, this corresponds to computing the same feature in all the local regions of the image. This architecture guarantees translational invariance, while also drastically reducing the number of parameters to be learned (in comparison to fully-connected networks).

Hence, on the whole, each neuron computes a kernel over a sub-region of the input image and transforms it through a non-linear activation function. %The shared weights and bias define the kernel (or filter).%

>The map from the input layer to the hidden layer a feature map. We call the weights defining the feature map the shared weights. And we call the bias defining the feature map in this way the shared bias. The shared weights and bias are often said to define a kernel or filter. 

Since each layer corresponds to one feature map of the image, multiple layers can be considered to obtain multiple feature maps. A complete convolutional layer consists of several different feature maps. 

%Insert image-feature maps%

>In the example shown, there are 3 feature maps. Each feature map is defined by a set of 5×5 shared weights, and a single shared bias. The result is that the network can detect 3 different kinds of features, with each feature being detectable across the entire image.

%Insert equation%

- **Pooling**:The neuron activations can be represented as an image i.e. of the form m x n. They represent fine-grained information over the image, which can be made compact by employing pooling. Here, we consider small windows (say 2 x 2) over the hidden layer activations, retaining only the maximum activation in each window. This is termed max pooling and provides robustness against overfitting. The max pooling is performed for each feature map separately.

%Insert image - pooling%

>We can think of max-pooling as a way for the network to ask whether a given feature is found anywhere in a region of the image. It then throws away the exact positional information. The intuition is that once a feature has been found, its exact location isn't as important as its rough location relative to other features. A big benefit is that there are many fewer pooled features, and so this helps reduce the number of parameters needed in later layers.

>Max-pooling isn't the only technique used for pooling. Another common approach is known as L2 pooling. Here, instead of taking the maximum activation of a 2×2 region of neurons, we take the square root of the sum of the squares of the activations in the 2×2 region. While the details are different, the intuition is similar to max-pooling: L2 pooling is a way of condensing information from the convolutional layer.






