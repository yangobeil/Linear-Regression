# Linear-Regression
We implement the learning algorithm linear regression from scratch with python. The only library that is necessary is numpy ad the details about the algorithm and the implementation can be found in the notebook.

The algorithm is implemented as a python class with functions as its methods, similarly to how it is done in scikit-learn. The first step is always to initialize the model in the following way:  
=> model = lin_reg(...)

There are two options that can be used when initializing the model
- normalize (default False): decide if the model normalizes the data before training it
- degree (default None): give the degree of a polynomial that the model uses to generate new features from the basic ones

The next step in using this model is to train it on some data. These must be numpy arrays where each row is a training example. X contains the features and Y the targets. This done with

=> model.fit(X, Y, ...)

The input is the rough data and there is a print at each 10000 steps of training. The modifications, like normalization and adding the bias, will be done by the algorithm. The numerous options are
- alpha (default 0.001): learning rate for gradient descent
- limit (default 100000): maximum number of steps of gradient descent to do
- rgularization (default None): putting this to 'L1' or 'L2' will add the appropriate regularization to gradient descent
- lambd (default 0): regularization parameter to use, its value won't matter if there is no regularization set
- normal (default False): if it is True the training will be done using the normal equation instead of gradient descent

After training it will be possible to access the trained weights using

=> model.weights

Also if the training was done using gradient descent the cost at each step of the training can be obtained using

model.cost

After the training is done the model can be used to predict the target for new data using

=> model.predict(X)

If normalization and/or polynomial are used it will be automatically applied in order to predict. The output of this function is a vector containing the predictions.

