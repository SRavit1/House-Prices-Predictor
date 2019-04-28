# ML-House-Prices-Predictor

Predicting house prices, using sample data from Google Colab.

The goal is to predict the price of a house based on 8 parameters, including: 

* longitude
* latitude
* housing median age
* total rooms
* total bedrooms
* population
* households
* median income

# Model Architecture

The model is very simple, just a series of three dense layers.

* Layer 1: Input Layer (Dense Layer) - input shape of (*, 8), output shape of (*, 8)
* Layer 2: Hidden Layer (Dense Layer) - output shape of (*, 4)
* Layer 3: Output Layer (Dense Layer) - output shape of (*, 1)

The first (input) layer is where the inputs are passed in, such as longitude, latitude, housing median age, etc. (see above).
The second (hidden) layer receives the output of the first layer in the shape (*, 8), and returns output in the shape (*, 4).
The third (output) layer receives the output of the second layer in the shape (*, 4), and returns output in the shpae (*, 1).
The output of the third layer is the predicted value of the house.

Before being passed in, all parameters were normalized to be somewhere between 0 and 1 (since working with smaller numbers improves performance).
The house prices (output) was reduced by 6 orders of magnitude.

# Performance
After 10 epochs, the loss, measured in mean square error (of the normalized outputs) is 0.0058.
