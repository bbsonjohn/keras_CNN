# keras_CNN
An example of convolutional neural network using Keras as framework.
We acknowledge **deeplearning.ai** for inspiring the program and providing the data set.

We build a convolutional neural network with Keras to analyze where a person in a photo is smelling (y=1) or not (y=0). The model is summarized in the following figure. Roughly speaking, it consists of 2 convolutional layers, a max pooling and then a 1 by 1 filter to compress the depth. After the "vision layers", it is followed by two fully-connected layers. The final output is a sigmoid activation to output the binary classification (y = 0 or 1).

<img src="figures\CompGraph.png" width = 70%>

We setup the above model using a "cell" model. There are two types of cell, the convolutional cell and the fully-connected cell. We make the cells to be more general for possible future adaption. First, the convolutional cell contains the convolutional layer, pooling layer, dropout regularization, batch normalization and a possible "skip-net". Skip-net allows the activation to skip through layers should they produce identity action. The concrete ideal is shown in the full cell schematics 3 figures below.

<img src="figures\ConvCell.png" width = 40%>

The one below is a fully-connected cell. The main component is a fully connected layer with either a ReLU or sigmoid activation. Two optional features are, 1.) a "flatten layer" that flattens the 3D output from the convolutional cells should the FC cell connects to a convolutional cell; 2.) batch normalization.

<img src="figures\FCCell.png" width = 30%>

The following is the CNN shown in cell schematics. First, the images goes through layers of convolutional cells. Then, it goes through layers of fully-connected cells. Finally, it ouputs a binary classification activation. At the convolutional cell section, we cann see how skip-net in action. An intermediate activation is skewed from the output of a convolutional cell. Then it skips across one or a few cells, and connects directly to another convolutional cell downstream. The "shortcut activation" is summed to the main variable flow, in a way according to the definition of convolutional cell we defined above. 

<img src="figures\CellsSchematics.png" width = 50%>

This is the summary of our models. There are a total of 23,721 trainable parameters. The distribution of parameters and the structure of CNN are shown in the figure below.

<img src="figures\ModelSummary.png" width = 60%>

<img src="figures\Training.png" width = 100%>

<img src="figures\PredictResult.png" width = 25%>
