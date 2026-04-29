# 🧠 Artificial Neural Networks (ANN) – Complete Notes

## 🔍 What is ANN?

Artificial Neural Network (ANN) is a **machine learning model inspired by the human brain**.

It consists of interconnected units called **neurons**, which process and pass information.

In simple terms:

> ANN learns patterns by adjusting weights between interconnected nodes (neurons).

---

# 🎯 Why Do We Need ANN?

Traditional models struggle with:

- Complex patterns
- Non-linear relationships
- High-dimensional data

ANN helps to:

- Capture complex relationships
- Handle large datasets
- Solve classification & regression problems

---

# 📌 Structure of ANN

ANN consists of **layers**:

## 1️⃣ Input Layer
- Takes input features  
- Each node represents a feature  

## 2️⃣ Hidden Layer(s)
- Performs computations  
- Extracts patterns  

## 3️⃣ Output Layer
- Produces final prediction  

---

# 📊 ANN Architecture
Input Layer → Hidden Layer(s) → Output Layer


Each connection has:
- Weight (importance)
- Bias (adjustment)

---

# ⚙️ How ANN Works

## Step-by-Step:

1️⃣ Input features are passed to neurons  
2️⃣ Multiply inputs with weights  
3️⃣ Add bias  
4️⃣ Apply activation function  
5️⃣ Pass output to next layer  
6️⃣ Repeat until final output  

---

# 📐 Mathematical Representation

\[
z = w \cdot x + b
\]

\[
a = f(z)
\]

Where:

- \(w\) → weights  
- \(x\) → input  
- \(b\) → bias  
- \(f(z)\) → activation function  
- \(a\) → output  

---

# 📌 Activation Functions

Activation functions introduce **non-linearity**.

## Common Functions:

### 1️⃣ Sigmoid
\[
\sigma(x) = \frac{1}{1 + e^{-x}}
\]

### 2️⃣ ReLU (Rectified Linear Unit)
\[
f(x) = \max(0, x)
\]

### 3️⃣ Tanh
\[
tanh(x)
\]

---

# 📉 Loss Function

Measures how wrong predictions are.

Examples:
- MSE (for regression)
- Cross-entropy (for classification)

---

# 🔁 Backpropagation

Backpropagation is used to:

- Calculate error
- Update weights

Steps:
1. Compute loss  
2. Calculate gradients  
3. Update weights using Gradient Descent  

---

# 📊 Forward Pass & Backward Pass

## Forward Pass
- Input → Output  
- Prediction is made  

## Backward Pass
- Error is propagated backward  
- Weights are updated  

---

# ⚙️ ANN in Python (Keras Example)

```python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense

model = Sequential()

model.add(Dense(10, activation='relu', input_shape=(X.shape[1],)))
model.add(Dense(1, activation='sigmoid'))

model.compile(optimizer='adam', loss='binary_crossentropy')

model.fit(X_train, y_train, epochs=10)