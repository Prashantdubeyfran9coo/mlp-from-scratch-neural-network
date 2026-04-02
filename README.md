# Multilayer Perceptron From Scratch

This project implements a **Multilayer Perceptron (MLP)** neural network from scratch using Python and NumPy without relying on deep learning frameworks.

The project demonstrates how neural networks perform forward propagation, backpropagation, optimization, and classification on different datasets.

---

## Project Objectives

The goal of this project is to understand the internal working of neural networks by implementing:

- Forward propagation
- Backpropagation
- Gradient descent optimization
- Hyperparameter tuning
- Performance evaluation

---

# Task A – MLP on Real Dataset (Binary Classification)

Dataset used:
Breast Cancer Wisconsin (Diagnostic)

Source:
sklearn.datasets.load_breast_cancer()

Dataset properties:

- 569 samples
- 30 numerical features
- Binary classification (Malignant / Benign)

### Architecture

```
Input Layer : 30 neurons
Hidden Layer : 8 / 16 / 32 neurons
Output Layer : 1 neuron
Activation : Sigmoid
```

### Training Setup

- Train/Test Split: 70/30
- Validation Split: 20% of training data
- Batch Size: 32
- Optimizer: Stochastic Gradient Descent
- Learning Rate: 0.001
- Epochs: 200
- Early stopping used

### Loss Functions Compared

1. Mean Squared Error (MSE)
2. Binary Cross Entropy (BCE)

### Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix

### Results

Binary Cross Entropy showed faster convergence and better classification stability compared to Mean Squared Error.

---

# Task B – 7 Segment Digit Recognition

In this task, digits 0–9 are represented using **7 segment binary encoding**.

Each digit is represented by a vector:

```
[a, b, c, d, e, f, g]
```

Example:

```
Digit 0 : [1 1 1 1 1 1 0]
Digit 1 : [0 1 1 0 0 0 0]
Digit 8 : [1 1 1 1 1 1 1]
```

### Architecture

```
Input Layer : 7
Hidden Layer 1 : H1
Hidden Layer 2 : H2
Output Layer : 10
```

Activation functions:

- ReLU (Hidden Layers)
- Softmax (Output)

### Data Augmentation

For robustness, noisy samples were generated:

- 50 noisy variants per digit
- Bit flip probability = 0.05

### Training

- Loss: Cross Entropy
- Optimizer: SGD / Adam
- Epochs: 200

### Hyperparameter Study

Learning rates tested:

```
5e-4
1e-3
5e-3
```

Hidden layer sizes tested:

```
8
16
32
```

### Evaluation

- 5 Fold Cross Validation
- Accuracy
- Precision
- Recall
- F1 Score

---

# Task C – Handwritten Letters (5x5 Binary Grid)

This task classifies uppercase letters using a **5×5 binary grid representation**.

Each letter is represented as a 25 dimensional vector.

Example representation:

```
1 1 1 1 1
1 0 0 0 1
1 1 1 1 1
1 0 0 0 1
1 0 0 0 1
```

### Dataset

- 26 letters
- At least 3 patterns per letter
- Total samples ≥ 78

### Data Augmentation

- Random bit flips (p = 0.02)
- Random pixel shifts

### Model Architecture

```
Input Layer : 25
Hidden Layer 1 : 64
Hidden Layer 2 : 32
Output Layer : 26
```

Activation:

- ReLU
- Softmax

Regularization:

- Dropout = 0.2
- L2 weight decay

Training:

- Epochs: 300
- Early stopping used

### Evaluation

- Confusion matrix
- Per-class F1 score
- Error analysis

---

# Technologies Used

- Python
- NumPy
- Matplotlib
- Scikit-Learn
- Jupyter Notebook

---

# Key Concepts Demonstrated

- Neural Network Fundamentals
- Forward Propagation
- Backpropagation
- Gradient Descent
- Classification Metrics
- Hyperparameter Optimization
- Data Augmentation

---

# Future Improvements

Possible improvements include:

- Implementing the model using PyTorch or TensorFlow
- Adding more datasets
- Improving robustness to noisy inputs

---

# Author

Prashant Dubey


# images

Image1 - accuracy Vs epoch and loss vs epoch for H=32

<img width="1189" height="490" alt="image" src="https://github.com/user-attachments/assets/12172c3b-008c-4a2e-a75c-87be42e17f7b" />


Image2 - H=16

<img width="1189" height="490" alt="image" src="https://github.com/user-attachments/assets/a6fa7e35-8aab-44bb-9b3d-03c00fa374c9" />

Image3 - H=8

<img width="1189" height="490" alt="image" src="https://github.com/user-attachments/assets/938c85b7-fee0-4caf-b7ff-395f218378f3" />


