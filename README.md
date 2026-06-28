# Handwritten Digit Recognition using ANN and CNN

A deep learning project that recognizes handwritten digits using the MNIST dataset. This project compares the performance of a fully connected Artificial Neural Network (ANN) and a Convolutional Neural Network (CNN), and demonstrates how image preprocessing improves predictions on custom handwritten digit images.

---

## Features

- Train an Artificial Neural Network (ANN) for digit classification
- Train a Convolutional Neural Network (CNN) for improved accuracy
- Evaluate model performance on the MNIST test dataset
- Predict handwritten digits from custom image files
- MNIST-style preprocessing pipeline for custom images
- Visualize preprocessing steps before prediction

---

## Dataset

This project uses the **MNIST Handwritten Digits Dataset**, which contains:

- **60,000** training images
- **10,000** testing images
- Image size: **28 × 28** pixels
- **10 classes** (digits 0–9)

The dataset is automatically downloaded using TensorFlow:

```python
from tensorflow.keras.datasets import mnist
```

---

## Technologies Used

- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
- Pillow (PIL)

---

## Model Architectures

### Artificial Neural Network (ANN)

```
Input (28×28)
      │
Flatten
      │
Dense (128, ReLU)
      │
Dense (64, ReLU)
      │
Dense (10, Softmax)
```

---

### Convolutional Neural Network (CNN)

```
Input (28×28×1)
        │
Conv2D (32 filters)
        │
MaxPooling2D
        │
Conv2D (64 filters)
        │
MaxPooling2D
        │
Flatten
        │
Dense (128, ReLU)
        │
Dropout (0.5)
        │
Dense (10, Softmax)
```

---

## Image Preprocessing

To improve predictions on handwritten images outside the MNIST dataset, a preprocessing pipeline was implemented that:

- Converts images to grayscale
- Handles transparent backgrounds
- Automatically inverts colors when needed
- Applies Otsu thresholding
- Crops the digit to its bounding box
- Resizes while preserving aspect ratio
- Centers the digit using its center of mass
- Normalizes pixel values
- Reshapes the image into MNIST format (28×28×1)

This preprocessing significantly improves prediction accuracy on custom images.

---

## Results

### Model Performance

| Model | Test Accuracy | Test Loss |
|--------|--------------:|----------:|
| ANN | **97.71%** | **0.0957** |
| CNN | **99.21%** | **0.0245** |

### Training Summary

| Model | Training Accuracy | Validation Accuracy |
|--------|------------------:|--------------------:|
| ANN | 99.31% | 98.08% |
| CNN | 99.29% | 99.27% |

### Custom Image Prediction

| Model | Prediction |
|--------|-----------|
| ANN | 5 |
| CNN (without preprocessing) | 7 |
| CNN (after preprocessing) | **8** (98.7% confidence) |

---

## Project Structure

```
.
├── notebook.ipynb          # Training and prediction notebook
├── img1.png                # Sample handwritten digit
├── README.md
└── requirements.txt
```

---

## Installation

Clone the repository

```bash
git clone https://github.com/RominaFdo/mnist-handwritten-digit-recognition.git
cd mnist-handwritten-digit-recognition
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

## Requirements

```
tensorflow
numpy
matplotlib
pillow
```

```bash
pip install -r requirements.txt
``` 

or install manually

```bash
pip install tensorflow numpy matplotlib pillow
```

---

## Usage

Run the notebook:

```bash
jupyter notebook
```

or

```bash
python notebook.py
```

The notebook will:

1. Download the MNIST dataset
2. Train the ANN model
3. Train the CNN model
4. Evaluate both models
5. Predict digits from custom images

---

## Sample Workflow

```
Custom Image
      │
      ▼
Image Preprocessing
      │
      ▼
Resize to 28×28
      │
      ▼
Normalize Pixel Values
      │
      ▼
CNN Prediction
      │
      ▼
Predicted Digit
```

---

## Future Improvements

- Train on the EMNIST dataset
- Data augmentation for better generalization
- Build a web application using Streamlit or Flask
- Export the trained model as TensorFlow Lite
- Real-time digit recognition using a webcam
- Hyperparameter tuning and model optimization

---

## Learning Outcomes

This project demonstrates:

- Feedforward Neural Networks
- Convolutional Neural Networks
- Image preprocessing techniques
- Deep learning model evaluation
- Image classification using TensorFlow/Keras
- Prediction on unseen handwritten images

---

## Author

**Shiny Fernando**

Computer Science Undergraduate

Interested in Machine Learning, Deep Learning, Computer Vision, and AI Systems.

---