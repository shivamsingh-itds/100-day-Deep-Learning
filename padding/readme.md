# 🧠 Padding in Keras (Deep Learning) – Complete Notes

## 🔍 What is Padding?

Padding is a technique used in Convolutional Neural Networks (CNNs) where:

> Extra pixels (usually zeros) are added around the border of an input image.

Padding helps preserve spatial dimensions during convolution.

---

# 🎯 Why Do We Need Padding?

Without padding:

- Image size decreases after every convolution
- Important edge information may be lost
- Deep networks shrink feature maps very quickly

Padding helps to:

- Preserve image size
- Retain edge information
- Allow deeper networks

---

# 📌 Example Without Padding

Input Image:

```text
5 × 5
```

Kernel:

```text
3 × 3
```

Output Size:

\[
Output = (5 - 3 + 1) = 3
\]

Result:

```text
3 × 3
```

Image becomes smaller.

---

# 📌 Example With Padding

Input Image:

```text
5 × 5
```

Padding:

```text
1 pixel border
```

New Size:

```text
7 × 7
```

After convolution:

```text
5 × 5
```

Original size preserved.

---

# 📊 Types of Padding

## 1️⃣ Valid Padding

No padding is applied.

```text
Padding = 0
```

Output size decreases after convolution.

Formula:

\[
Output = \frac{(N - F)}{S} + 1
\]

Where:

- N = Input size
- F = Filter size
- S = Stride

---

## Example

Input:

```text
5 × 5
```

Kernel:

```text
3 × 3
```

Output:

```text
3 × 3
```

---

# 2️⃣ Same Padding

Adds padding so that:

> Output size remains the same as input size.

Example:

Input:

```text
5 × 5
```

Output:

```text
5 × 5
```

---

# 📌 Formula for Padding

For stride = 1:

\[
P = \frac{F-1}{2}
\]

Where:

- P = Padding
- F = Filter size

Example:

Kernel:

```text
3 × 3
```

Padding:

\[
P = \frac{3-1}{2}=1
\]

---

# 📊 Visual Representation

Without Padding:

```text
Input
5 × 5
  ↓
Convolution
  ↓
3 × 3
```

---

With Padding:

```text
Input
5 × 5
  ↓
Padding
7 × 7
  ↓
Convolution
  ↓
5 × 5
```

---

# ⚙️ Padding in Keras

## Valid Padding

```python
from tensorflow.keras.layers import Conv2D

model.add(
    Conv2D(
        filters=32,
        kernel_size=(3,3),
        padding='valid'
    )
)
```

---

## Same Padding

```python
from tensorflow.keras.layers import Conv2D

model.add(
    Conv2D(
        filters=32,
        kernel_size=(3,3),
        padding='same'
    )
)
```

---

# 📊 Output Size Formula

General Formula:

\[
Output = \frac{(N - F + 2P)}{S} + 1
\]

Where:

- N = Input size
- F = Filter size
- P = Padding
- S = Stride

---

# 📌 Why Same Padding is Popular?

Benefits:

- Preserves image dimensions
- Retains border information
- Easier network design
- Common in modern CNN architectures

---

# 📈 Advantages of Padding

- Prevents feature map shrinkage
- Preserves edge information
- Allows deeper CNNs
- Improves feature extraction

---

# ⚠️ Disadvantages of Padding

- Slightly increases computation
- Adds artificial values around image borders

---

# 🔄 Valid vs Same Padding

| Feature | Valid Padding | Same Padding |
|----------|--------------|--------------|
| Padding Added | No | Yes |
| Output Size | Smaller | Same as input |
| Edge Information | May lose | Preserved |
| Most Common | Less | More |

---

# 📌 When to Use Padding?

Use padding when:

- Building CNNs
- Need to preserve image dimensions
- Creating deep convolutional networks
- Important edge features exist

---

# 🔥 Key Takeaway

> Padding is a technique in CNNs that adds extra pixels around an image before convolution, helping preserve spatial dimensions and retain important edge information. In Keras, the most commonly used options are `padding='valid'` and `padding='same'`.