# Image-Classification-in-MATLAB

# Architecture of ConvNet

ConvNet is not just a deep neural network that has many hidden layers. It is a deep network that imitates how the visual cortex of the brain processes and
recognizes images. Therefore, even the experts of neural networks often have a hard time understanding this concept on their first encounter. That is how much ConvNet differs in concept and operation from the previous neural networks. This section briefly introduces the fundamental architecture of ConvNet.

Basically, image recognition is the classification. For example, recognizing whether the image of a picture is a cat or a dog is the same as classifying the image into a cat or dog class. The same thing applies to the letter recognition; recognizing the letter from an image is the same as classifying the image into one of the letter classes. Therefore, the output layer of the ConvNet generally employs the multiclass classification neural network.

However, directly using the original images for image recognition leads to poor results, regardless of the recognition method; the images should be processed to contrast the features. The examples used the original images and they worked well because they were simple black-and-white images. Otherwise, the recognition process would have ended up with very poor results. For this reason, various techniques for image feature extraction have been developed.

Before ConvNet, the feature extractor has been designed by experts of specific areas. Therefore, it required a significant amount of cost and time while it yielded an inconsistent level of performance. These feature extractors were independent of Machine Learning.

![image](https://user-images.githubusercontent.com/86974424/171833548-bdca6679-7dae-493b-be6b-5420c633affe.png)

ConvNet yields better image recognition when its feature extraction neural network is deeper (contains more layers), at the cost of difficulties in the training
process, which had driven ConvNet to be impractical and forgotten for a while. Let’s go a bit deeper. ConvNet consists of a neural network that extracts features of the input image and another neural network that classifies the feature image.

![image](https://user-images.githubusercontent.com/86974424/171833765-35ff8f2b-3a79-426a-bd69-911e477caea9.png)

# Convolution Layer

The convolution layer generates new images called feature maps. The feature map accentuates the unique features of the original image. The convolution layer operates in a very different way compared to the other neural network layers. This layer does not employ connection weights and a weighted sum.4 Instead, it contains filters5 that convert images. We will call these filters convolution filters. The process of the inputting the image through the convolution filters yields the feature map.

The filters of the convolution layer are two-dimensional matrices. They usually come in 5´5 or 3´3 matrices, and even 1´1 convolution filters have been used in recent applications. As addressed in the previous section, the values of the filter matrix are determined through the training process. Therefore, these values are continuously trained throughout the training process. This aspect is similar to the updating process of the connection weights of the ordinary neural network.

Similarly to the first convolution operation, the values in the elements of this feature map depend on whether the image matrix matches the convolution filter or not. In summary, the convolution layer operates the convolution filters on the input image and produces the feature maps. The features that are extracted in the convolution layer determined by the trained convolution filters. Therefore, the features that the convolution layer extracts vary depending on which convolution filter is used.

# Pooling Layer

The pooling layer reduces the size of the image, as it combines neighboring pixels of a certain area of the image into a single representative value. Pooling is a typical technique that many other image processing schemes have already been employing.

In order to conduct the operations in the pooling layer, we should determine how to select the pooling pixels from the image and how to set the representative value. The neighboring pixels are usually selected from the square matrix, and the number of pixels that are combined differs from problem to problem. The representative value is usually set as the mean or maximum of the selected pixels.

Actually, in a mathematical sense, the pooling process is a type of convolution operation. The difference from the convolution layer is that the convolution filter is stationary, and the convolution areas do not overlap. The example provided in the next section will elaborate on this. The pooling layer compensates for eccentric and tilted objects to some extent. 

For example, the pooling layer can improve the recognition of a cat, which may be off-center in the input image. In addition, as the pooling process reduces the image size, it is highly beneficial for relieving the computational load and preventing overfitting.

# MNIST Database

We implement a neural network that takes the input image and recognizes the digit that it represents. The training data is the MNIST database, which contains 70,000 images of handwritten numbers. In general, 60,000 images are used for training, and the remaining 10,000 images are used for the validation test. Each digit image is a 28-by-28 pixel black-and-white image, as shown in Figure
![image](https://user-images.githubusercontent.com/86974424/171839085-da32589c-0ea7-4484-9727-90e5edef5ede.png)

Considering the training time, this example employs only 10,000 images with the training data and verification data in an 8:2 ratio. Therefore, we have 8,000 MNIST images for training and 2,000 images for validation of the performance of the neural network. As you may know well by now, the MNIST problem is caused by the multiclass classification of the 28´28 pixel image into one of the ten digit classes of 0-9.

Figure shows the architecture of this neural network. Although it has many layers, only three of them contain the weight matrices that require training; they are W1, W5, and Wo in the square blocks. W5 and Wo contain the connection weights of the classification neural network, while W1 is the convolution layer’s weight, which is used by the convolution filters for image processing.
![image](https://user-images.githubusercontent.com/86974424/171839252-5b897ef6-93ce-4aeb-8853-401a8cc24e42.png)

# Image Processing

It passes through the convolution layer and pooling layer. The original dimension of the MNIST image is 28´28. Once the image is processed with the 9´9 convolution filter, it becomes a 20´20 feature map.11 As we have 20 convolution filters, the layer produces 20 feature maps. Through the 2´2 mean pooling process, the pooling layer shrinks each feature map to a 10´10 map.
![image](https://user-images.githubusercontent.com/86974424/171839897-12fa7755-8799-4eec-9578-d36d201ae1b7.png)

# MATLAB Output Of different output layers:
![image](https://user-images.githubusercontent.com/86974424/171840428-ecbf9927-db19-48a2-bcdc-e25c33fdd2fe.png)
![image](https://user-images.githubusercontent.com/86974424/171840441-133d42b5-7709-4f57-8efa-ebef5a5ab7e6.png)
![image](https://user-images.githubusercontent.com/86974424/171840454-a3e947a1-ec1a-44d8-a8df-18dc21803301.png)
![image](https://user-images.githubusercontent.com/86974424/171840468-b8cb6ed3-451d-4dff-be03-2c0e94ece03c.png)
![image](https://user-images.githubusercontent.com/86974424/171840481-23d262ae-7931-433f-b1c2-6b4612512e78.png)



### References
Deep Learning ~ Phil kim
