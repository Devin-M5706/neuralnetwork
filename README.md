Binary MNIST Classifier with Fixed-Point Forward Pass Simulation
This project trains a simple neural network on the MNIST dataset using Keras and then simulates a forward pass using fixed-point integer math. It’s built to mimic resource-constrained environments like FPGAs, microcontrollers, or embedded systems where floating-point operations and large memory aren't available.

Features
Binary Input: Grayscale MNIST images are binarized (0 or 1) for simplified input processing.

Simple Neural Network:

Input: 784 (28x28 pixels flattened)

Hidden Layer: 10 neurons with ReLU

Output Layer: 10 neurons with softmax

Fixed-Point Inference: Performs manual forward pass using only integer math with overflow checks.

Overflow Detection: Simulates hardware bit limitations (e.g., 8-bit, 16-bit overflow warnings).

Model Evaluation: Compares integer-based predictions with true labels and calculates accuracy.

File Overview

File/Function	Purpose
clean_data()	Preprocesses and binarizes MNIST data. One-hot encodes labels.
train_new_model()	Builds, trains, and saves a Keras model on MNIST.
forward()	Loads trained model, converts weights to fixed-point, simulates integer-only inference with overflow checks.
check_overflow(x, num_bits)	Warns if value exceeds range of specified bit-width.
main()	Runs either training or inference.
Usage
Requirements
Python 3.x

numpy

tensorflow / keras

Install dependencies:

bash
Copy
Edit
pip install numpy tensorflow
Train a New Model
Uncomment the train_new_model(model_name) line in main() to train the model:

python
Copy
Edit
def main():
    model_name = 'mnist_model.keras'
    train_new_model(model_name)
    # forward(model_name, 10000)
Then run:

bash
Copy
Edit
python your_script.py
Run Forward Pass Simulation
After training, comment the training line and run the forward simulation:

python
Copy
Edit
def main():
    model_name = 'mnist_model.keras'
    # train_new_model(model_name)
    forward(model_name, 10000)
This will evaluate the integer-only forward pass on 10,000 test samples with real-time overflow checks.

Example Output
bash
Copy
Edit
100
200
...
Test Loss: 0.1923
Test Accuracy: 0.9482
Accuracy: 9443 / 10000 = 94.43%
Why This Project?
This repo is a great sandbox for:

Exploring how neural networks behave with binary inputs

Simulating hardware inference without needing real hardware

Practicing low-level AI implementation under strict constraints

Possible Extensions
Replace ReLU with other activation functions

Support for different bit-widths (e.g., 4-bit or 16-bit)

Export weights in C-style arrays for embedded use

Let me know if you want me to auto-generate the actual README.md file or restructure it for a more professional tone!







You said:
Make it so I can copy all of it
ChatGPT said:
Absolutely — here’s the full copy-pasteable GitHub README.md content:

markdown
Copy
Edit
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
Train a New Model
Uncomment the train_new_model(model_name) line in main() to train the model:

python
Copy
Edit
def main():
    model_name = 'mnist_model.keras'
    train_new_model(model_name)
    # forward(model_name, 10000)
Then run:

bash
Copy
Edit
python your_script.py
Run Forward Pass Simulation
After training, comment the training line and run the forward simulation:

python
Copy
Edit
def main():
    model_name = 'mnist_model.keras'
    # train_new_model(model_name)
    forward(model_name, 10000)
This will evaluate the integer-only forward pass on 10,000 test samples with real-time overflow checks.

Example Output
yaml
Copy
Edit
100
200
...
Test Loss: 0.1923
Test Accuracy: 0.9482
Accuracy: 9443 / 10000 = 94.43%
Why This Project?
This repo is a great sandbox for:

Exploring how neural networks behave with binary inputs

Simulating hardware inference without needing real hardware

Practicing low-level AI implementation under strict constraints

Possible Extensions
Replace ReLU with other activation functions

Support for different bit-widths (e.g., 4-bit or 16-bit)

Export weights in C-style arrays for embedded use

yaml
Copy
Edit

---

Let me know if you want a downloadable `.md` file or a rendered preview!
