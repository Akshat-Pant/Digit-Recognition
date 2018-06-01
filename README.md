# Digit-Recognition

Implementation of Convolutional Neural Network in python using Keras(Tensorflow backend) to recognize handwritten digits.

## The dataset
The dataset is downloaded from the MNIST website. Each image is a 28 by 28 pixel square (784 pixels total). A standard spit of the dataset is used to evaluate and compare models, where 60,000 images are used to train a model and a separate set of 10,000 images are used to test it. It is a subset of a larger set available from NIST. Images of digits were taken from a variety of scanned documents, normalized in size and centered. 
It is a digit recognition task. As such there are 10 digits (0 to 9) or 10 classes to predict. 

## Neural network
Neural networks are a set of algorithms, modeled loosely after the human brain, that are designed to recognize patterns. They interpret sensory data through a kind of machine perception, labeling or clustering raw input. The patterns they recognize are numerical, contained in vectors, into which all real-world data, be it images, sound, text or time series, must be translated.
I programmed the Neural Network part of the project in tensorflow using Keras.
The training dataset is structured as a 3-dimensional array of instance, image. width and image height. For a multi-layer perceptron model we must reduce the images down into a vector of pixels. In this case the 28×28 sized images will be 784 pixel input values. The pixel values are gray scale between 0 and 255. I normalized the pixel values to the range 0 and 1 by dividing each value by the maximum of 255.
Also, the output variable is an integer from 0 to 9. This is a multi-class classification problem. I one hot encoded the class values, transforming the vector of class integers into a binary matrix.

## Convolutional Neural Network
Convolutional Neural Networks differ from the Neural Nets in the sense that not all layers in a CNN are fully connected layers. I used Convolutional layers, Pooling layers and Dropout layers to build my CNN.
The network architecture is summarized below:
1.	The first hidden layer is a convolutional layer called a Convolution2D. The layer has 32 feature maps, which with the size of 5×5 and a rectifier activation function. This is the input layer.
2.	Next I define a pooling layer that takes the max called MaxPooling2D. It is configured with a pool size of 4×4.
3.	The next layer is a regularization layer using dropout called Dropout. It is configured to randomly exclude 25% of neurons in the layer in order to reduce overfitting.
4.	Next is a layer that converts the 2D matrix data to a vector called Flatten. It allows the output to be processed by standard fully connected layers.
5.	Next a fully connected layer with 128 neurons and rectifier activation function.
6.	Finally, the output layer has 10 neurons for the 10 classes and a softmax activation function to output probability-like predictions for each class.
