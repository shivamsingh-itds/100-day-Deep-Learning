# 🧠 Keras Functional API in Deep Learning – Complete Notes

## 🔍 What is Keras Functional API?

Keras Functional API is an advanced way to build Deep Learning models in TensorFlow/Keras.

Unlike Sequential API, Functional API allows:

> Building complex neural network architectures with multiple inputs, outputs, shared layers, and non-linear connections.

---

# 🎯 Why Do We Need Functional API?

Sequential API works only for:

- Simple linear stack of layers

But real-world deep learning models may require:

- Multiple inputs
- Multiple outputs
- Skip connections
- Shared layers
- Complex architectures

Functional API solves these limitations.

---

# 📌 Sequential API vs Functional API

| Feature | Sequential API | Functional API |
|--------|----------------|----------------|
| Linear architecture | Yes | Yes |
| Multiple inputs | No | Yes |
| Multiple outputs | No | Yes |
| Complex architectures | No | Yes |
| Shared layers | No | Yes |

---

# 📊 Core Idea of Functional API

Functional API treats:
- Layers as functions

Each layer:
- Takes tensor as input
- Returns tensor as output

---

# ⚙️ Basic Workflow

## Step-by-Step

1️⃣ Define input layer  
2️⃣ Add hidden layers  
3️⃣ Define output layer  
4️⃣ Create model object  

---

# 📐 Functional API Syntax

```python
from tensorflow.keras.models import Model
from tensorflow.keras.layers import Input, Dense

# Input layer
inputs = Input(shape=(10,))

# Hidden layer
x = Dense(64, activation='relu')(inputs)

# Output layer
outputs = Dense(1, activation='sigmoid')(x)

# Create model
model = Model(inputs=inputs, outputs=outputs)
```

---

# 📊 Understanding the Flow

```text
Input Layer
      ↓
Hidden Layer
      ↓
Output Layer
```

Each layer acts like a function.

---

# 📌 Input Layer

Defines:
- Shape of input data

Example:

```python
inputs = Input(shape=(20,))
```

Means:
- 20 input features

---

# 📌 Hidden Layers

Hidden layers perform:
- Feature extraction
- Learning patterns

Example:

```python
x = Dense(128, activation='relu')(inputs)
```

---

# 📌 Output Layer

Depends on problem type.

---

## Regression

```python
outputs = Dense(1)(x)
```

---

## Binary Classification

```python
outputs = Dense(1, activation='sigmoid')(x)
```

---

## Multi-class Classification

```python
outputs = Dense(10, activation='softmax')(x)
```

---

# ⚙️ Compile the Model

```python
model.compile(
    optimizer='adam',
    loss='binary_crossentropy',
    metrics=['accuracy']
)
```

---

# ⚙️ Train the Model

```python
model.fit(X_train, y_train, epochs=10)
```

---

# 📊 Functional API for Multiple Inputs

Example:

```python
input1 = Input(shape=(10,))
input2 = Input(shape=(5,))
```

Useful for:
- Multi-modal data
- Combining text + image inputs

---

# 📊 Functional API for Multiple Outputs

Example:

```python
output1 = Dense(1)(x)
output2 = Dense(5, activation='softmax')(x)
```

Useful for:
- Multi-task learning

---

# 📊 Shared Layers

One layer can be reused for multiple inputs.

Useful in:
- Siamese Networks
- NLP models

---

# 📌 Why Functional API is Powerful?

It allows:
- Flexible architectures
- DAG (Directed Acyclic Graph) models
- Modern deep learning designs

---

# 📈 Advantages

- Flexible
- Supports complex models
- Multiple inputs/outputs
- Layer sharing possible
- Better visualization

---

# ⚠️ Disadvantages

- Slightly more complex
- Harder for beginners
- More code than Sequential API

---

# 📌 When to Use Functional API?

Use when:
- Building complex architectures
- Multiple inputs/outputs needed
- Using shared layers
- Creating advanced deep learning models

---

# ❌ When NOT to Use?

Avoid for:
- Very simple linear models

In those cases:
- Sequential API is easier

---

# 🔄 Sequential vs Functional Example

## Sequential

```python
model = Sequential([
    Dense(64, activation='relu'),
    Dense(1)
])
```

---

## Functional

```python
inputs = Input(shape=(10,))
x = Dense(64, activation='relu')(inputs)
outputs = Dense(1)(x)

model = Model(inputs, outputs)
```

---

# 🔥 Key Takeaway

> Keras Functional API is a flexible way to build deep learning models that supports complex architectures with multiple inputs, outputs, shared layers, and non-linear connections.