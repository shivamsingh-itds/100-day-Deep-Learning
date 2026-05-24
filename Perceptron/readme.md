# 🧠 Perceptron – Complete Notes

## 🔍 What is a Perceptron?

Perceptron is the **simplest Artificial Neural Network (ANN)** and one of the earliest machine learning algorithms.

It is a **binary classification algorithm** used to classify data into two classes.

In simple terms:

> Perceptron learns a decision boundary that separates two classes.

---

# 🎯 Why Do We Need Perceptron?

Perceptron helps to:

- Learn from data
- Perform binary classification
- Build the foundation of neural networks

Example:
- Spam vs Not Spam
- Yes vs No
- Positive vs Negative

---

# 📌 Structure of Perceptron

A perceptron contains:

- Input features
- Weights
- Bias
- Activation function
- Output

---

# 📊 Perceptron Architecture

```text
Input Features → Weighted Sum → Activation Function → Output
```

---

# ⚙️ Mathematical Representation

## Weighted Sum

\[
z = w_1x_1 + w_2x_2 + ... + w_nx_n + b
\]

Where:

- \(x\) → Input features  
- \(w\) → Weights  
- \(b\) → Bias  

---

## Activation Function

Perceptron uses a **step activation function**:

\[
f(z)=
\begin{cases}
1 & z \geq 0 \\
0 & z < 0
\end{cases}
\]

Output:
- 1 → Positive class
- 0 → Negative class

---

# 📌 How Perceptron Works

## Step-by-Step

1️⃣ Take input features  
2️⃣ Multiply inputs with weights  
3️⃣ Add bias  
4️⃣ Compute weighted sum  
5️⃣ Apply activation function  
6️⃣ Generate output  

---

# 📉 Perceptron Learning Rule

If prediction is wrong:

Update weights using:

\[
w = w + \eta(y - \hat{y})x
\]

Where:

- \(w\) → Weight  
- \(\eta\) → Learning rate  
- \(y\) → Actual output  
- \(\hat{y}\) → Predicted output  
- \(x\) → Input feature  

---

# 🔁 Training Process

1. Initialize weights randomly  
2. Predict output  
3. Calculate error  
4. Update weights  
5. Repeat until convergence  

---

# 📊 Decision Boundary

Perceptron creates a:

- Line (2D)
- Plane (3D)
- Hyperplane (higher dimensions)

to separate classes.

---

# ⚙️ Perceptron in Python

```python
from sklearn.linear_model import Perceptron
from sklearn.model_selection import train_test_split

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Create model
model = Perceptron()

# Train model
model.fit(X_train, y_train)

# Predict
y_pred = model.predict(X_test)
```

---

# 📌 Assumptions of Perceptron

- Data should be linearly separable
- Binary classification problem
- Features should be numerical

---

# 📈 When to Use Perceptron?

Use when:
- Problem is linearly separable
- Binary classification needed
- Simple and fast model required

---

# ❌ When NOT to Use?

Avoid when:
- Data is non-linear
- Complex patterns exist
- Multi-class classification required

---

# ⭐ Advantages

- Simple and easy to understand
- Fast training
- Foundation of neural networks
- Works well for simple linear problems

---

# ⚠️ Disadvantages

- Works only for linearly separable data
- Cannot solve XOR problem
- No probability output
- Sensitive to noisy data

---

# 🔄 Perceptron vs Logistic Regression

| Feature | Perceptron | Logistic Regression |
|--------|-------------|-------------------|
| Output | 0 or 1 | Probability |
| Activation | Step function | Sigmoid |
| Loss Function | Perceptron loss | Log loss |
| Probability output | No | Yes |

---

# 🔥 Key Takeaway

> Perceptron is the simplest neural network model that performs binary classification by learning a linear decision boundary using weighted inputs and a step activation function.