# Fashion MNIST Classification using PyTorch (ANN - CPU)

## Project Overview
This project demonstrates a complete deep learning workflow using PyTorch to classify grayscale fashion images. The model is implemented using a fully connected Artificial Neural Network (ANN) and trained entirely on a CPU.

The dataset is loaded from a CSV file and processed step-by-step, including visualization, preprocessing, custom dataset creation, model training, and evaluation.

---

## Objective
The goal of this project is to classify 28×28 grayscale images into one of 10 fashion categories using a neural network.

---

## Dataset Description
- Dataset: Fashion MNIST (CSV format)
- Total samples: 6000
- Features: 784 (28×28 pixels flattened)
- Labels: 10 classes (0–9)

Each row in the dataset:
- Column 0 → Label  
- Column 1–784 → Pixel values  

---

## Data Visualization
- Visualized first 16 images using matplotlib  
- Reshaped 784 values into 28×28 images  
- Displayed labels for verification  

---

## Data Preprocessing
- Separated features and labels  
- Train-test split:
  - Training: 80%  
  - Testing: 20%  
- Normalized pixel values:
  - Scaled from [0–255] to [0–1]  

---

## Custom Dataset (PyTorch)

python
class CustomDataset(Dataset):
    def __init__(self, features, labels):
        self.features = torch.tensor(features, dtype=torch.float32)
        self.labels = torch.tensor(labels, dtype=torch.long)

    def __len__(self):
        return len(self.features)

    def __getitem__(self, index):
        return self.features[index], self.labels[index]
        
Functionality:
__len__() → returns total samples
__getitem__() → returns (features, label)
DataLoader Configuration
Batch size: 32
Training loader: shuffle = True
Test loader: shuffle = False
Model Architecture (ANN)

Input Layer (784)
→ Linear (128 neurons) + ReLU
→ Linear (64 neurons) + ReLU
→ Output Layer (10 neurons)

Training Setup
Loss Function: CrossEntropyLoss
Optimizer: Stochastic Gradient Descent (SGD)
Learning Rate: 0.1
Epochs: 10
Training Process
Forward pass → predictions
Loss calculation
Backpropagation
Parameter update using optimizer
Evaluation
_, predicted = torch.max(outputs, 1)
Result:
Test Accuracy: ~83%
Tech Stack
Python
PyTorch
NumPy
Pandas
Matplotlib
Scikit-learn
Project Structure
fashion-mnist-ann-pytorch/
│── data/
│   └── fmnist_small.csv
│── notebook/
│   └── ann_fashion_mnist_pytorch_with_CPU.ipynb
│── README.md
│── requirements.txt

How to Run
Step 1: Clone Repository
git clone https://github.com/your-username/fashion-mnist-ann-pytorch.git
cd fashion-mnist-ann-pytorch

Step 2: Install Dependencies
pip install -r requirements.txt

Step 3: Run Notebook
Open Jupyter Notebook or Google Colab and run:

notebook/ann_fashion_mnist_pytorch_with_CPU.ipynb
Requirements
pandas
numpy
matplotlib
scikit-learn
torch
