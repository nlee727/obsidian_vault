### Multiclass Classification
$C$ is the number of classes, can be any number.
- Goal is to generalize the linear model (separating hyperplane) for multiple classes.
To do this, create a new vector $w = w_{1}-w_{2}$ and choose the maximum

9/31
W is a matrix of norms to create many separating areas

10/31
numerator $y_{n}$ represents each class
denominator, sum over all possible classes
result will give the softmax function which will assign a probability to each class.

11/31
After creating the loss function by MLE, the cross-entropy/multiclass logistic loss is created. When C=2, this is binary logistic loss.

### Gradient Descent
20/31
Nesterov - momentum accelerated gradient
- You update velocity, then the weight

21/31
Adam - adaptive
- Intuition - understand momentum/rolling down a hill. Say you are approaching the minimum, your steps should start relatively large and get smaller as you get closer to the minimum.

### Neural Networks
28/31
Whatever comes in - dot product
what ever comes out - activation function

