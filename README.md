# Fashion MNIST Classification using PyTorch (ANN - CPU)

## Project Overview
This project demonstrates an end-to-end deep learning pipeline using PyTorch to classify grayscale fashion images from the Fashion MNIST dataset. A fully connected Artificial Neural Network (ANN) is implemented and trained on a CPU.

The workflow includes data loading from CSV, visualization, preprocessing, custom dataset creation, model training, and evaluation.

---

## Objective
To classify 28×28 grayscale images into 10 fashion categories using a neural network model.

---

## Dataset Description
- **Dataset:** Fashion MNIST (CSV format)  
- **Total Samples:** 6000  
- **Features:** 784 (28×28 flattened pixels)  
- **Classes:** 10 (labels 0–9)  

### Data Format
- Column 0 → Label  
- Column 1–784 → Pixel intensity values  

---

## Data Visualization
- Visualized the first 16 samples using `matplotlib
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
- Training Loader: Shuffle = True  
- Testing Loader: Shuffle = False  

---

## Model Architecture (ANN)
A fully connected neural network:

- Input Layer: 784  
- Hidden Layer 1: 128 neurons + ReLU  
- Hidden Layer 2: 64 neurons + ReLU  
- Output Layer: 10 neurons (classes)  

---

## Training Setup
- Loss Function: CrossEntropyLoss  
- Optimizer: Stochastic Gradient Descent (SGD)  
- Learning Rate: 0.1  
- Epochs: 10  

---

## Training Process
- Forward propagation for predictions  
- Loss computation  
- Backpropagation  
- Weight updates using optimizer  
- Evaluation using `torch.max() 

---

## Performance
# Fashion MNIST Classification using PyTorch (ANN - CPU)

## Project Overview
This project demonstrates an end-to-end deep learning pipeline using PyTorch to classify grayscale fashion images from the Fashion MNIST dataset. A fully connected Artificial Neural Network (ANN) is implemented and trained on a CPU.

The workflow includes data loading from CSV, visualization, preprocessing, custom dataset creation, model training, and evaluation.

---

## Objective
To classify 28×28 grayscale images into 10 fashion categories using a neural network model.

---

## Dataset Description
- **Dataset:** Fashion MNIST (CSV format)  
- **Total Samples:** 6000  
- **Features:** 784 (28×28 flattened pixels)  
- **Classes:** 10 (labels 0–9)  

### Data Format
- Column 0 → Label  
- Column 1–784 → Pixel intensity values  

---

## Data Visualization
- Visualized the first 16 samples using `matplotlib`
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
- Training Loader: Shuffle = True  
- Testing Loader: Shuffle = False  

---

## Model Architecture (ANN)
A fully connected neural network:

- Input Layer: 784  
- Hidden Layer 1: 128 neurons + ReLU  
- Hidden Layer 2: 64 neurons + ReLU  
- Output Layer: 10 neurons (classes)  

---

## Training Setup
- Loss Function: CrossEntropyLoss  
- Optimizer: Stochastic Gradient Descent (SGD)  
- Learning Rate: 0.1  
- Epochs: 10  

---

## Training Process
- Forward propagation for predictions  
- Loss computation  
- Backpropagation  
- Weight updates using optimizer  
- Evaluation using `torch.max()`  

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
