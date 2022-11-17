# Apple Fruit Disease Detection

Requirements for project: Matlab

Developing an Artificial Neural Network (ANN) model which uses 
1.Kmeans clustering and image segmentation
LBP for Feature extraction
2.CCV and LBP feature extraction techniques
3. Feed forwarding Neural Network to train images


IMAGE PRE-PROCESSING
We have used L*a*b* color space because the color information in the L*a*b* color space is stored in only two channels (i.e. a* and b* components), 
It causes reduced processing time for the image segmentation
To convert an image in RGB format to L*a*b* format, one can combine the calling to the rgb2xyz and xyz2lab functions.
RGB2XYZ converts an image from RGB format to XYZ
XYZ = rgb2xyz(RGB)
Output RGB must be an image having 3 channels, i.e. a 3D array.
Each channel of RGB should be in the range 0 to 255.
Input XYZ would be an image of the same dimension.
Read image. 
Transform image from RGB to L*a*b* color space. 
RGB2LAB Convert an image from RGB to CIELAB
function [L, a, b] = RGB2Lab(R, G, B)
function [L, a, b] = RGB2Lab(I)
RGB2Lab takes red, green, and blue matrices, or a single M x N x 3 image, and returns an image in the CIELAB color space.  
RGB values can be either between 0 and 1 or between 0 and 255.  
Values for L are in the range [0,100] while a and b are roughly in the range [-110,110].  
The output is of type double.


IMAGE SEGMENTATION
The k-means clustering algorithms classify the objects into K number of four classes/clusters based on a set of features. 
The classification is carried out by minimizing the sum of squares of distances between the data objects and the corresponding cluster. 
In this experiment, squared Euclidean distance is used for the K-means clustering.
1. Classify colors using K-Means clustering in a*b* space. 
2. Label each pixel in the image from the results of K-Means. 
3. Generate images that segment the image by color. 
4. Select the segment containing disease.

PATTERN RECOGNITION
The feature vector of the Local Binary Pattern (LBP) is created in the following manner. 
1. The image window is divided into cells (16X16). 
2. For each pixel in a cell, compare the pixel to each of its 8 neighbors in a circular manner. 
3. If the center pixel’s value is greater than the neighbor’s value write ‘0’, otherwise write ‘1’ producing a 8 digit binary number. 
4. The histogram is computed for the cell as a 256 dimensional feature vector and normalized
5. The histograms of all the cells are normalized giving the feature vector for the entire window. 

The feature vector can now be processed using Feed Forward Back propagation Neural Network for disease recognition and classification of the fruit images.

DATASET TRAINING USING NEURAL NETWORK
In the proposed system the classification is done with Feed Forward Back propagation Neural Network. 
In this network, the information moves from the input nodes through the hidden nodes to the output nodes. 
Initialization Step 
1. Initialize all weights with a random number from a normal distribution. 
2. All Bias nodes are set 
Feed Forward 
1. The values of all input nodes are set. 
2. The hidden node values are calculated. 
3. An activation function for the hidden layer is selected. 
4. Hidden node activation values are calculated. 
5. The output node values are calculated. 
6. An activation function for output layer is selected. 
7. The output node activation values are calculated. 
8. The total error obtained is calculated.


Testing the model takes images as input, performs pre-processing, segmentation and LBP techniques.
the image is classified into the category of Apple fruit disease.
The model performs well and improves detection.
