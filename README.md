# Binary MNIST Classifier with Fixed-Point Forward Pass Simulation

This project trains a simple neural network on the MNIST dataset using Keras and then simulates a forward pass using fixed-point integer math. It’s built to mimic resource-constrained environments like FPGAs, microcontrollers, or embedded systems where floating-point operations and large memory aren't available.

---

## Features
- **Binary Input**: Grayscale MNIST images are binarized (0 or 1) for simplified input processing.
- **Simple Neural Network**:
  - Input: 784 (28x28 pixels flattened)  
  - Hidden Layer: 10 neurons with ReLU  
  - Output Layer: 10 neurons with softmax
- **Fixed-Point Inference**: Performs manual forward pass using only integer math with overflow checks.
- **Overflow Detection**: Simulates hardware bit limitations (e.g., 8-bit, 16-bit overflow warnings).
- **Model Evaluation**: Compares integer-based predictions with true labels and calculates accuracy.

---

## File Overview

| File/Function | Purpose |
|---------------|---------|
| `clean_data()` | Preprocesses and binarizes MNIST data. One-hot encodes labels. |
| `train_new_model()` | Builds, trains, and saves a Keras model on MNIST. |
| `forward()` | Loads trained model, converts weights to fixed-point, simulates integer-only inference with overflow checks. |
| `check_overflow(x, num_bits)` | Warns if value exceeds range of specified bit-width. |
| `main()` | Runs either training or inference. |

---

## Usage

### Requirements
- Python 3.x
- `numpy`
- `tensorflow` / `keras`

Install dependencies:

```bash
pip install numpy tensorflow
