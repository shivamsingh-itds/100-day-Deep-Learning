# 🧠 Gradient Descent in Neural Networks – Complete Notes

## 🔍 What is Gradient Descent?

Gradient Descent is an **optimization algorithm** used to train Neural Networks.

It helps the network:

> Minimize the loss function by updating weights and biases.

In simple terms:

- Neural network makes predictions
- Calculates error
- Adjusts weights to reduce error

---

# 🎯 Why Do We Need Gradient Descent?

Neural Networks start with:
- Random weights
- Random predictions

Gradient Descent helps to:
- Learn from errors
- Improve predictions
- Find optimal weights

---

# 📌 Main Goal

The goal is to minimize the:

\[
Loss\ Function
\]

Lower loss means:
- Better predictions
- Better learning

---

# 📊 Basic Idea

Imagine standing on a mountain and trying to reach the lowest point.

Gradient Descent:
- Calculates slope
- Moves downhill step-by-step
- Reaches minimum loss

---

# ⚙️ Working of Gradient Descent in Neural Networks

## Step-by-Step Process

### 1️⃣ Initialize Weights Randomly

Neural network starts with:
- Random weights
- Random bias values

---

### 2️⃣ Forward Propagation

Input passes through the network.

For each neuron:

\[
z = wx + b
\]

Apply activation function:

\[
a = f(z)
\]

Prediction is generated.

---

### 3️⃣ Calculate Loss

Loss measures prediction error.

Example:
- MSE for regression
- Cross-entropy for classification

---

### 4️⃣ Backpropagation

Error is propagated backward.

Goal:
- Calculate gradients

Gradient:

\[
\frac{\partial Loss}{\partial Weight}
\]

Represents:
- How much each weight contributes to error

---

### 5️⃣ Update Weights

Weights updated using:

\[
W_{new} = W_{old} - \eta \frac{\partial Loss}{\partial W}
\]

Where:

- \(\eta\) → Learning rate
- Gradient → Slope of error

---

### 6️⃣ Repeat

Repeat process for:
- Multiple epochs
- Until loss becomes minimum

---

# 📉 Loss Function

Loss function measures:
- Difference between actual and predicted output

---

## Regression Loss

### Mean Squared Error (MSE)

\[
MSE = \frac{1}{n}\sum(y - \hat{y})^2
\]

---

## Classification Loss

### Cross Entropy Loss

\[
Loss = -[y\log(\hat{y}) + (1-y)\log(1-\hat{y})]
\]

---

# 📌 Learning Rate (η)

Learning rate controls:
- Step size during optimization

---

## Small Learning Rate

- Slow learning
- More stable

---

## Large Learning Rate

- Faster learning
- May overshoot minimum

---

# 📊 Types of Gradient Descent

## 1️⃣ Batch Gradient Descent

- Uses entire dataset
- Stable but slow

---

## 2️⃣ Stochastic Gradient Descent (SGD)

- Uses one sample at a time
- Faster but noisy

---

## 3️⃣ Mini-Batch Gradient Descent

- Uses small batches
- Most commonly used

---

# 📊 Gradient Descent Workflow

```text
Input Data
      ↓
Forward Propagation
      ↓
Prediction
      ↓
Calculate Loss
      ↓
Backpropagation
      ↓
Compute Gradients
      ↓
Update Weights
      ↓
Repeat
```

---

# ⚙️ Gradient Descent in TensorFlow/Keras

```python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense

model = Sequential()

model.add(Dense(64, activation='relu'))
model.add(Dense(1))

model.compile(
    optimizer='sgd',
    loss='mse'
)
```

---

# 📌 Common Optimizers Based on Gradient Descent

| Optimizer | Description |
|----------|-------------|
| SGD | Basic Gradient Descent |
| Momentum | Faster convergence |
| RMSprop | Adaptive learning rate |
| Adam | Most popular optimizer |

---

# 📈 Why Gradient Descent is Important?

Without Gradient Descent:
- Neural networks cannot learn
- Weights remain random
- Predictions never improve

---

# ⭐ Advantages

- Efficient optimization
- Works for deep learning
- Handles large datasets
- Simple mathematical concept

---

# ⚠️ Disadvantages

- Sensitive to learning rate
- Can get stuck in local minima
- Slow convergence sometimes
- Requires tuning

---

# 🔄 Batch vs SGD vs Mini-Batch

| Feature | Batch GD | SGD | Mini-Batch |
|--------|-----------|-----|------------|
| Speed | Slow | Fast | Balanced |
| Stability | High | Low | Medium |
| Memory Usage | High | Low | Medium |

---

# 🔥 Key Takeaway

> Gradient Descent is the core optimization algorithm in neural networks that minimizes loss by updating weights using gradients calculated through backpropagation.