# Fashion MNIST Classification using PyTorch (ANN - CPU)

## Project Overview

This project demonstrates an end-to-end deep learning pipeline using PyTorch to classify grayscale fashion images from the Fashion MNIST dataset. A fully connected Artificial Neural Network (ANN) is implemented and trained on a CPU.

The workflow includes data loading from CSV, visualization, preprocessing, custom dataset creation, model training, and evaluation.

---

## Objective

To classify 28×28 grayscale images into 10 fashion categories using a neural network model.

---

## Dataset Description

- Dataset: Fashion MNIST (CSV format)
- Total Samples: 6000
- Features: 784 (28×28 flattened pixels)
- Classes: 10 (labels 0–9)

### Data Format

- Column 0 → Label
- Column 1–784 → Pixel intensity values

---

## Data Visualization

- Visualized the first 16 samples using matplotlib
- Reshaped flattened vectors (784 → 28×28)
- Verified labels with corresponding images

---

## Data Preprocessing

- Separated features and labels

- Train-test split:
  - Training: 80%
  - Testing: 20%

- Normalized pixel values to range [0, 1]

---

## Custom Dataset (PyTorch)

Implemented a custom dataset class using torch.utils.data.Dataset:

- Converts NumPy arrays into PyTorch tensors

- Implements:
  - __len__() → returns dataset size
  - __getitem__() → returns (feature, label) pair

---

## DataLoader Configuration

- Batch Size: 32
- Training Loader: Shuffle = True
- Testing Loader: Shuffle = False

---

## Model Architecture (ANN)

- Input Layer: 784
- Hidden Layer 1: 128 neurons + ReLU
- Hidden Layer 2: 64 neurons + ReLU
- Output Layer: 10 neurons

---

## Training Setup

- Loss Function: CrossEntropyLoss
- Optimizer: SGD
- Learning Rate: 0.1
- Epochs: 10

---

## Training Process

- Forward propagation for predictions
- Loss computation
- Backpropagation
- Weight updates using optimizer
- Evaluation using torch.max()

---

## Performance

- Test Accuracy: ~83%

---

## Tech Stack

- Python
- PyTorch
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

---

## Requirements

- pandas
- numpy
- matplotlib
- scikit-learn
- torch

---

# Fashion MNIST Classification using PyTorch (ANN - GPU Accelerated)

## Project Overview

This project demonstrates an end-to-end deep learning pipeline using PyTorch to classify grayscale fashion images from the Fashion MNIST dataset. A fully connected Artificial Neural Network (ANN) is implemented and trained on a **GPU (CUDA)** for significantly faster training.

The workflow includes data loading from CSV, visualization, preprocessing, custom dataset creation, GPU-accelerated training, and evaluation.

---

## Objective

To classify 28×28 grayscale images into 10 fashion categories using a neural network model, leveraging a GPU for faster computation.

---

## Dataset Description

- Dataset: Fashion MNIST (CSV format)
- Total Samples: **10,000** (full test set)
- Features: 784 (28×28 flattened pixels)
- Classes: 10 (labels 0–9)

### Data Format

- Column 0 → Label
- Column 1–784 → Pixel intensity values

---

## Data Visualization

- Visualized the first 16 samples using matplotlib
- Reshaped flattened vectors (784 → 28×28)
- Verified labels with corresponding images

---

## Data Preprocessing

- Separated features and labels

- Train-test split:
  - Training: 80%
  - Testing: 20%

- Normalized pixel values to range [0, 1]

---

## Custom Dataset (PyTorch)

Implemented a custom dataset class using `torch.utils.data.Dataset`:

- Converts NumPy arrays into PyTorch tensors

- Implements:
  - `__len__()` → returns dataset size
  - `__getitem__()` → returns (feature, label) pair

---

## DataLoader Configuration

- Batch Size: 32
- Training Loader: `shuffle = True`, `pin_memory = True` (for faster GPU transfer)
- Testing Loader: `shuffle = False`, `pin_memory = True`

---

## Model Architecture (ANN)

- Input Layer: 784
- Hidden Layer 1: 128 neurons + ReLU
- Hidden Layer 2: 64 neurons + ReLU
- Output Layer: 10 neurons

---

## Training Setup

- Device: **CUDA (NVIDIA T4 GPU)**
- Loss Function: CrossEntropyLoss
- Optimizer: SGD
- Learning Rate: 0.1
- Epochs: **100**

---

## Training Process

- Move data to GPU before forward pass
- Forward propagation for predictions
- Loss computation
- Backpropagation
- Weight updates using optimizer
- Evaluation using `torch.max()`
- Loss printed per epoch

---

## Performance

- **Training Accuracy: ~99.71%**
- **Test Accuracy: ~85.45%**
- Training completed in minutes (GPU acceleration)

---

## Tech Stack

- Python
- PyTorch (CUDA enabled)
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

---

## Requirements

- pandas
- numpy
- matplotlib
- scikit-learn
- torch (with CUDA support)

---

## How to Run

1. Clone the repository
2. Install dependencies: `pip install -r requirements.txt`
3. Run the Jupyter notebook: `ann_gpu_fashion_mnist.ipynb`
4. Make sure your runtime has GPU enabled (Colab → Runtime → Change runtime type → GPU)

---

## Key Improvements over CPU Version

| Aspect | CPU Version | GPU Version |
|--------|-------------|--------------|
| Dataset size | 6,000 samples | 10,000 samples |
| Epochs | 10 | 100 |
| Test accuracy | ~83% | **85.45%** |
| Training time | ~45 minutes | **~5 minutes** |

---

