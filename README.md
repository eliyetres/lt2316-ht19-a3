# Movie poster classification

## Report

After training the model using 3 layers, the model starts to overfit; it's learning to recognize specific images in the training set rather than generalizing. Adding dropout to all the layers did not help to avoid overfitting. 

The  model with the lowest loss was trained using 3 layers, a dropout of 0.8 at the first layer and a dropout of 0.25 for the others. However, the model starts to overfit after 5 epochs; the validation keeps increasing while the training loss stays close to 0.

![pl1](/img/3l_lr0001.png "Plot 1")
3 layers, dropout 0.8 for input layer, 0.25 for the rest, learning rate: 0.0001

Using the same dropout, but adding a 4th layer produces similar results as only using 3 layers, but the model takes longer (10 epochs) before it starts to overfit. The model with 3 layers performed slightly better so I decided to keep it like this.
![pl2](/img/4l_lr0001.png "Plot 2")
4 layers, dropout 0.8 for input layer, 0.25 for the rest, learning rate: 0.0001

Training the model using 4 layers with a higher learning rate gives a higher loss than the 3 layers and after 20 epochs, both the training and validation loss increases. Training the model with a lower learning rate, even when including dropout for all layers, causes the model to overfit.

![pl3](/img/4l_lr001.png "Plot 3")
4 layers, dropout 0.8 for input layer, 0.25 for the rest, learning rate: 0.001

X = Batch size

Layer 1

* First convolutional layer: Size changes from `[X, 3, 300, 450]` to `[X, 16, 300, 450]`
* Dropout: 0.8
* First pooling layer: Size changes from `[X, 16, 300, 450]` to `[X, 16, 150, 225]`.

Layer 2

* Second convolutional layer: Size changes from `[X, 16, 150, 225]` to `[X, 32, 150, 225]`
* Dropout: 0.25
* Second pooling layer: `[X, 32, 75, 112]` to `[X, 32, 75, 112]`.

Layer 3

* Third convolutional layer: Size changes from `[X, 32, 75, 112]` to `[X, 64, 75, 112]`
* Dropout: 0.25
* Third pooling layer: Size changes from `[X, 64, 75, 112]` to `[X, 64, 37, 56]`.
