# 🧠 Batch Normalization in Deep Learning – Complete Notes

## 🔍 What is Batch Normalization?

Batch Normalization (BatchNorm) is a technique used in Deep Learning to:

- Normalize activations of each layer
- Stabilize training
- Speed up convergence

In simple terms:

> Batch Normalization standardizes the inputs of a layer during training.

---

# 🎯 Why Do We Need Batch Normalization?

During training:

- Distribution of activations keeps changing
- This is called:

> Internal Covariate Shift

Problems caused:
- Slow training
- Vanishing/exploding gradients
- Unstable learning

Batch Normalization solves these issues.

---

# 📌 Core Idea

For each mini-batch:

1. Compute mean
2. Compute variance
3. Normalize data
4. Scale and shift values

This keeps activations stable.

---

# 📐 Batch Normalization Formula

## Step 1: Compute Mean

\[
\mu_B = \frac{1}{m}\sum x_i
\]

---

## Step 2: Compute Variance

\[
\sigma_B^2 = \frac{1}{m}\sum (x_i - \mu_B)^2
\]

---

## Step 3: Normalize

\[
\hat{x_i} = \frac{x_i - \mu_B}{\sqrt{\sigma_B^2 + \epsilon}}
\]

Where:
- \(\epsilon\) → Small constant to avoid division by zero

---

## Step 4: Scale and Shift

\[
y_i = \gamma \hat{x_i} + \beta
\]

Where:
- \(\gamma\) → Scale parameter
- \(\beta\) → Shift parameter

These are learnable parameters.

---

# ⚙️ How Batch Normalization Works

## During Training

For every mini-batch:

- Normalize activations
- Forward pass continues
- Gradients computed normally

---

# 📊 Position in Neural Network

Usually placed:

```text
Linear Layer
     ↓
Batch Normalization
     ↓
Activation Function