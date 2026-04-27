# 🧠 Perceptron & Hinge Loss – Complete Notes

## 🔍 What is a Perceptron?

Perceptron is one of the **simplest binary classification algorithms**.

It is a **linear model** that separates data using a straight line (decision boundary).

In simple terms:

> Perceptron tries to find a line (or hyperplane) that separates two classes.

---

# 📊 Perceptron Model Equation

\[
y = sign(w \cdot x + b)
\]

Where:

- \(w\) → weights  
- \(x\) → input features  
- \(b\) → bias  
- \(sign()\) → returns +1 or -1  

---

# 🎯 Goal of Perceptron

- Correctly classify data points  
- Adjust weights when prediction is wrong  

---

# ⚙️ Perceptron Learning Rule

If a point is misclassified:

\[
w = w + yx
\]

\[
b = b + y
\]

Where:
- \(y\) = actual label (+1 or -1)

---

# ❗ Limitation of Perceptron

- Works only for **linearly separable data**
- No clear loss function
- Does not measure "how wrong" the prediction is

---

# 📌 What is Hinge Loss?

Hinge Loss is used in **Support Vector Machines (SVM)**.

It improves perceptron by:

> Not only checking if prediction is correct, but also how confident it is.

---

# 📐 Hinge Loss Formula

\[
Loss = \max(0, 1 - y(w \cdot x + b))
\]

Where:

- \(y\) → actual label (+1 or -1)  
- \(w \cdot x + b\) → predicted score  

---

# 📊 Understanding Hinge Loss

| Condition | Loss |
|----------|------|
| Correct & confident | 0 |
| Correct but weak | Small loss |
| Wrong prediction | Large loss |

---

# 📈 Interpretation

## Case 1: Correct and far from boundary

\[
y(wx + b) ≥ 1
\]

Loss = 0  
✔ Good prediction

---

## Case 2: Correct but near boundary

\[
0 < y(wx + b) < 1
\]

Loss > 0  
⚠ Needs improvement

---

## Case 3: Wrong prediction

\[
y(wx + b) ≤ 0
\]

Loss is high  
❌ Incorrect classification

---

# 🔄 Perceptron vs Hinge Loss

| Feature | Perceptron | Hinge Loss |
|--------|-----------|------------|
| Loss Function | No explicit | Yes |
| Margin concept | No | Yes |
| Confidence measurement | No | Yes |
| Used in | Perceptron | SVM |

---

# 📊 Margin Concept

Hinge loss introduces **margin**:

- Wants points not just correct
- But **far from decision boundary**

---

# ⚙️ Example

If:
