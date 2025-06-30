# neural-network-from-scratch

Coding a neural network from scratch is valuable for building a deep, practical understanding of how core concepts like forward propagation, backpropagation, and gradient descent actually work. It removes reliance on high-level libraries, forces you to think critically about each component, and improves debugging and problem-solving skills. While it's not efficient for real-world deployment, doing it is essential for solidifying foundational knowledge in machine learning.


1. What is a Neural Network?

A neural network is a set of interconnected layers of nodes (neurons) that learn to approximate complex functions by transforming input data step-by-step into predictions. It’s like stacking multiple linear regressions with non-linear activations in between.

2. Parameters:
   
These are the trainable values:

Weights (W) – control the strength of connections between neurons.

Biases (b) – added to each layer to shift the output.

Every layer has its own weights and biases, and these are updated during training.

3. Layers:

Input layer: Takes raw features (e.g., pixel values, measurements).

Hidden layers: Do the actual processing via linear operations + activation functions.

Output layer: Produces final prediction (class, value, etc.).

4. Forward Propagation:

This is how the input moves through the network:


z1 = X @ W1 + b1        # linear

a1 = ReLU(z1)           # activation

z2 = a1 @ W2 + b2       # next layer
..

output = softmax(zN)    # for classification

Each z is a weighted sum, and each a is the activation.

5. Activation Functions:

Add non-linearity so the network can learn complex patterns.

ReLU: max(0, x) — fast, commonly used in hidden layers.

Sigmoid/Tanh: older, used less now.

Softmax: for multi-class classification output.

6. Loss Function:
   
Measures how far predictions are from actual targets.

Cross Entropy Loss (classification)

MSE (regression)

7. Backpropagation:
   
This is how the model learns. It computes gradients of the loss w.r.t each weight/bias and updates them using:


W = W - learning_rate * dL/dW

b = b - learning_rate * dL/db

This is done using the chain rule through all layers.

8. Learning Rate (LR):
   
Controls how much weights are adjusted during each update. Same concept as in linear regression:

Too high = unstable.

Too low = slow training.

9. Training Loop:
    
Forward pass (compute prediction)

Compute loss

Backward pass (compute gradients)

Update weights and biases

Repeat for multiple epochs

