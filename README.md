# Melanoma Detection Using Computer Vision
> A computer vision project using CNN architecture to correctly classify 9 skin conditions inclusive of melanoma and basal cell carcinoma. This model is not meant for use in making medical decisions but simply serves as an example of how to build a CNN with parallel convolutions in hidden layers along with densely connected layers.  


## General Information
* Computer Vision Project
* Libraries used - Pandas, Numpy, Matplotlib.pyplot, Tensorflow, Keras, Augmentor


The final model has a single dense layer of 9 neurons to supply a softmax activation, with hidden layers of 3x3x2^(n+3) convolutions in each hidden layer followed by max pooling. 

** n is the layer number

> Structure of Model

| Layer (type)            | Output Shape     | Param #    |
|-------------------------|------------------|------------|
| sequential (input layer)| (None, 180, 180, 3) | 0          |
| sequential_1 (augmentation/Rescaling)| (None, 180, 180, 3) | 0          |
| conv2d_30               | (None, 178, 178, 32) | 896        |
| max_pooling2d_30        | (None, 89, 89, 32) | 0          |
| conv2d_31               | (None, 87, 87, 64) | 18496      |
| max_pooling2d_31        | (None, 43, 43, 64) | 0          |
| conv2d_32               | (None, 41, 41, 128) | 73856      |
| max_pooling2d_32        | (None, 20, 20, 128) | 0          |
| conv2d_33               | (None, 18, 18, 256) | 295168     |
| max_pooling2d_33        | (None, 9, 9, 256) | 0          |
| conv2d_34               | (None, 7, 7, 512) | 1180160    |
| max_pooling2d_34        | (None, 3, 3, 512) | 0          |
| dropout_5               | (None, 3, 3, 512) | 0          |
| flatten_6               | (None, 4608)     | 0          |
| dense_6                 | (None, 9)        | 41481      |
|-------------------------|------------------|------------|
| Total params            | 1,610,057        |            |
| Trainable params        | 1,610,057        |            |
| Non-trainable params    | 0                |            |
|_________________________|__________________|____________|

After 70 epochs, the model achieved a 76% accuracy and 0.6 cross entropy loss. While not best, it mainly shows that convolutional layers alone can be used to provide pretty good classification results.


> Note the original dataset can be found [here](https://www.kaggle.com/datasets/nodoubttome/skin-cancer9-classesisic), the dataset within this repo includes augmented images created using the original dataset. 

