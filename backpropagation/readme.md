# 🧠 Backpropagation in Deep Learning – Complete Notes

## 🔍 What is Backpropagation?

Backpropagation is a training algorithm used in **Artificial Neural Networks (ANNs)** and Deep Learning.

It is used to:

> Calculate error gradients and update weights to minimize the loss function.

In simple terms:

- Forward pass → Make prediction
- Backward pass → Learn from mistakes

---

# 🎯 Why Do We Need Backpropagation?

Neural Networks learn by:
- Adjusting weights
- Reducing prediction error

Backpropagation helps the network:
- Understand how wrong the prediction is
- Update weights efficiently
- Improve predictions over time

---

# 📌 Main Idea

Backpropagation works using:

- Chain Rule of Calculus
- Gradient Descent Optimization

Goal:
- Minimize the loss function

---

# ⚙️ Steps in Backpropagation

## 1️⃣ Forward Propagation

Input passes through the network.

For each neuron:

\[
z = wx + b
\]

Apply activation function:

\[
a = f(z)
\]

Final output is generated.

---

## 2️⃣ Calculate Loss

Loss measures prediction error.

### For Regression

Usually uses:
- Mean Squared Error (MSE)

\[
Loss = \frac{1}{n}\sum(y - \hat{y})^2
\]

---

### For Classification

Usually uses:
- Cross Entropy Loss

Binary Classification:

\[
Loss = -[y\log(\hat{y}) + (1-y)\log(1-\hat{y})]
\]

---

## 3️⃣ Backward Propagation

Error is propagated backward through the network.

Goal:
- Find how much each weight contributed to the error.

Uses:
- Partial derivatives
- Chain rule

---

## 4️⃣ Compute Gradients

Gradient:

\[
\frac{\partial Loss}{\partial Weight}
\]

Represents:
- Direction of error increase
- How weights should change

---

## 5️⃣ Update Weights

Weights are updated using Gradient Descent:

\[
W_{new} = W_{old} - \eta \frac{\partial Loss}{\partial W}
\]

Where:

- \(\eta\) → Learning rate
- Gradient → Error slope

---

# 📊 Backpropagation in Regression

## Output Layer

Usually:
- Linear activation

Loss:
- Mean Squared Error (MSE)

Goal:
- Minimize numerical prediction error

Example:
- House price prediction
- Stock prediction

---

# 📊 Backpropagation in Classification

## Output Layer

Depends on problem:

### Binary Classification
- Sigmoid activation

### Multi-class Classification
- Softmax activation

Loss:
- Cross Entropy Loss

Goal:
- Maximize class prediction accuracy

Example:
- Spam detection
- Disease classification

---

# 🔄 Difference Between Classification & Regression

| Feature | Regression | Classification |
|--------|------------|---------------|
| Output | Continuous value | Class probability |
| Activation | Linear | Sigmoid / Softmax |
| Loss Function | MSE | Cross Entropy |
| Goal | Minimize numeric error | Predict correct class |

---

# 📌 Activation Functions Used

## Regression

Usually:
- Linear activation

---

## Classification

### Sigmoid

\[
\sigma(x)=\frac{1}{1+e^{-x}}
\]

Used for:
- Binary classification

---

### Softmax

\[
P(y=i)=\frac{e^{z_i}}{\sum e^{z_j}}
\]

Used for:
- Multi-class classification

---

# 📉 Why Backpropagation is Important

Without backpropagation:
- Network cannot learn
- Weights remain random
- Predictions do not improve

Backpropagation enables:
- Efficient learning
- Deep learning training
- Error minimization

---

# ⚙️ Simple Workflow

```text
Input
  ↓
Forward Pass
  ↓
Prediction
  ↓
Calculate Loss
  ↓
Backward Pass
  ↓
Compute Gradients
  ↓
Update Weights
  ↓
Repeat