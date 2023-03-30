# Fruit Image Recognition

## 1. Introduction
&nbsp;&nbsp;&nbsp;&nbsp; In this dataset, I have 100 images of 36 fruits and vegetables in a training set and 10 images of fruits and vegetables in a testing and validation set. The goal of this project was to create a neural network that would be able to correctly identify and label each image with the utmost accuracy.

## 2. Data Analysis
&nbsp;&nbsp;&nbsp;&nbsp; Initially, I had to choose how to import the data. I used the image_dataset_from_directory from tensorflow's keras package to to import the images into a single dataset. I had the images sized 256x256 with batches of 32 images in each. I wanted to go with images sized 256x256 since it's a nice number to work with for squares, and the batch sizes were just there as default.

&nbsp;&nbsp;&nbsp;&nbsp; I also wanted to try to display a small sample of the images I would be using, displayed a 4x4 panel of 16 images labeled. With this example, I was able to see a couple cartoon images of the fruits and vegetables, other images of some of them cooked, and even some where the fruit or vegetable is right on the plant of which it grows.

## 3. Modeling
&nbsp;&nbsp;&nbsp;&nbsp; Once modeling, there was a small period where I was doing research on best possible parameters for my case, as well as some trial and error. It was suggested many times for a problem like this that I create a convolutional neural network. In this neural network, I began by adding 2 pixels of zero padding around the image and rescaling the values to range from 0 to 1. I then did 4 cycles if putting a 2d convolution over the image, followed by applying batch normalization, and finally applying the ReLU activation function. With each cycles of applying the 2d convolution layer, I lessened by 1/2 each time, from 64 down to 8. I always used a kernel size of (3,3) and a stride of (1,1). After the first 3 iterations of the cycle, I applied max pooling 2d with a pool size of (2,2) to downsample the input in order to prevent overfitting. At the end of the fourth and final cycle, instead of max pooling, I flattened the output of the fourth ReLU layer and applied a dense layer with the number of units being equal to the number of image labels that I have in my dataset. 

## 4. Model Analysis
 &nbsp;&nbsp;&nbsp;&nbsp; After a few iterations, my model was consistently between 89% and 92% accurate when predicting the labels of the testing data. I was very pleased with the consistency of my model and would be more than pleased to test the same out with other types of images. I am not so much disappointed by the inaccuracies when detecting corn and sweetcorn since the test images did look very similar to each other. I would like to further research different activation functions to better understand which work the best in certain situations, as well as deepen my understanding of the parameters in the convolution layers of my model.
