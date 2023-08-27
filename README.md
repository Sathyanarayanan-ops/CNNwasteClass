# CNNwasteClass

This project was performed as part of a bigger funded project in SASTRA University, a **smart waste management system**

The objective of this project was to not just build a CNN classifier, but use this as a platform to analyse the effectiveness of building CNN models from scratch rather than using transfer learning methods 

This particular project use InceptionV3 model and compares it with a manually written CNN architecture 

**Methodology**

1. The first process of the project was to process all the given data, which is in the form of images. This project had contained 25,000 images for training and validation, followed by 100 for testing the built model
2.  The processing involved extracting all the images and sorting them so that the classifier can iterate through it, and then all the images were resized inorder to facilitate easy processing. Images were grouped into batches of 20.
3. The CNN has three convolutional layers, each followed by a max pooling layer. The convolutional layers extract features from the input image, and the max pooling layers downsample the feature maps to reduce the number of parameters in the network. The final layer is a fully connected layer that outputs a probability for each class.

The CNN architecture is as follows:

Input layer: The input layer is a 3-dimensional tensor of shape (150, 150, 3). This represents an image with 150 x 150 pixels and 3 color channels (RGB).
Convolutional layers: The first convolutional layer has 16 filters of size 3 x 3. The second convolutional layer has 32 filters of size 3 x 3. The third convolutional layer has 64 filters of size 3 x 3. Each convolutional layer uses a ReLU activation function.
Max pooling layers: The first max pooling layer has a pool size of 2 x 2. The second max pooling layer has a pool size of 2 x 2. The max pooling layers downsample the feature maps by a factor of 2 in each dimension.
Fully connected layer: The final layer is a fully connected layer with 512 hidden units. The fully connected layer uses a ReLU activation function and outputs a probability for each class.

The CNN was decided to be made 3 layered because of the complexity of the task and the size of the image 
It is usually norm to use 3 layer for simple binary classification, and since the size of the image was decided to be made into 150x150, the 3 layer proved to be adept as well as reduced computation complexity 

4. Loading the inceptionV3 Architecture
5. We load the Inception v3 model and freeze all of its layers. The last layer of the model is the mixed7 layer, which has an output shape of (None, 7, 7, 1024).

The mixed7 layer outputs a 1024-dimensional feature vector for each input image. This feature vector can be used as input to a classifier for fine-tuning the model on a specific task.

This is the trained on a new classification layer 

6. The model is the fine tuned and used to process the image classifier 
