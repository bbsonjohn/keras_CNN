# keras_CNN
An example of convolutional neural network using Keras as framework.
We acknowledge **deeplearning.ai** for inspiring the program and providing the data set.

We build a convolutional neural network with Keras to analyze where a person in a photo is smelling (y=1) or not (y=0). The model is summarized in the following figure. Roughly speaking, it consists of 2 convolutional layers, a max pooling and then a 1 by 1 filter to compress the depth. After the "vision layers", it is followed by two fully-connected layers. The final output is a sigmoid activation to output the binary classification (y = 0 or 1).

<img src="figures\CompGraph.png" width = 70%>

We setup the above model using a "cell" model. There are two types of cell, the convolutional cell and the fully-connected cell. We make the cells to be more general for possible future adaption. First, the convolutional cell contains the convolutional layer, pooling layer, dropout regularization, batch normalization and a possible "skip-net".

<img src="figures\ConvCell.png" width = 40%>

<img src="figures\FCCell.png" width = 30%>

<img src="figures\CellsSchematics.png" width = 50%>

<img src="figures\ModelSummary.png" width = 60%>

<img src="figures\Training.png" width = 100%>

<img src="figures\PredictResult.png" width = 25%>
