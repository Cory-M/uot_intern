## Neural Network Exercise - MultiDigit MNIST

*MScAC - UofT internship - Vanguard*

*Keyu Long*  - keyu@cs.toronto.edu

### Intro

1. **Since I currently don't have access to any GPU resources, I only tried several relatively simple conv models. The codes/logs are pushed to the forked repository on Github.** (the log was a copy-paste from the terminal - I forgot to log it during training.)
2. Codes can be found at **/mnist/part2-twodigit/***


### My Answer:

- for MLP: (Single hidden layer with 64 units)
  - ACC1: 0.925907
  - ACC2: 0.916079
- for Conv:
  - **ACC1: 0.983619**
  - **ACC2: 0.980595**

### Preparing steps

> Look at the **main** method in each file. Identify the training and test data and labels. How many images are inside the train and test data? What is the size of each image?

- There are 40,000 training data and 4,000 test data.
- the size of each image is $42\times28$.

> Look at the definition of the MLP class in **mlp.py**. Try to make sense of what those lines are trying to achieve. What is y_train[0] and y_train[1]?

- y_train[0]  and y_train[1] are the labels for the two digits correspondingly.

### Hyperparameter tuning

- Batchnormalization helps. It helps with the ill-conditioned optimization case, where gradients along different directions varies a lot.
- Extra training might lead to decrease of accuracy on test set. Decrease the learning rate might help with the loss plateau. Overparameterization and too large epoch number might make the test accuracy get worse after some point.

