# Convolutional Networks

Notes from [Introducing Convolutional Nets](http://neuralnetworksanddeeplearning.com/chap6.html#introducing_convolutional_networks):

In image classification, fully connected networks do not exploit the spatial structure of images. They treat pixels which are close/far apart on an equal footing. Conv Nets exploit the spatial structure in images. Further, their architecture makes them faster to train, paving the way for wide use of deep convolutional nets in image classification.

Convolutional neural networks use three basic ideas: local receptive fields, shared weights, and pooling.

- **Local receptive fields**: Instead of connecting each hidden neuron to all input neurons (as is the case in fully-connected architecture), each neuron in the first hidden layer is connected to a small region of (spatially adjacent) input neurons. 

> For example, a small 5 x 5 region, corresponding to 25 pixels. That region in the input image is called the *local receptive field* for the hidden neuron. It's a little window on the input pixels. Each connection learns a weight. And the hidden neuron learns an overall bias as well. You can think of that particular hidden neuron as learning to analyze its particular local receptive field.

- **Shared weights**:
- **Pooling**:


