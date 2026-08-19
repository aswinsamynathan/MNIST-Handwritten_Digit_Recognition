
### MNIST Handwritten Digit Recognition

## 📌 Project Overview

This project focuses on recognizing handwritten digits using a Neural Network trained on the MNIST dataset.

The project experiments with different neural network architectures, batch sizes, activation functions, and numbers of epochs to understand their effect on model performance.

## 📊 Dataset

# The MNIST dataset contains:

70,000 grayscale handwritten digit images
Digits from 0 to 9
Image size: 28 × 28 pixels
Pixel values range from 0 to 255
Each image is converted into 784 input features for the neural network.

## The dataset is loaded using TensorFlow/Keras:
(x_train, y_train), (x_test, y_test) = keras.datasets.mnist.load_data()
🛠️ Technologies Used
Python
TensorFlow
Keras
NumPy
Pandas
Matplotlib
Seaborn
Scikit-learn
Libraries
tensorflow==2.18.0
scikit-learn==1.3.2
matplotlib==3.8.3
seaborn==0.13.2
numpy==1.26.4
pandas==2.2.2

## 🔄 Data Preprocessing

# The handwritten digit images are processed before training.

# Main preprocessing steps:

Load the MNIST dataset.
Reshape the 28 × 28 images into 784 features.
Normalize the pixel values.
Convert the target labels into one-hot encoded vectors with 10 classes.

## 🧠 Model Building
Model 0 – Baseline Model

The baseline model contains:

MNIST Image
     ↓
28 × 28 Pixels
     ↓
784 Input Features
     ↓
No Hidden Layer
     ↓
10 Output Neurons
     ↓
Digit Prediction (0–9)

The output layer uses Softmax activation. The model contains 7,850 trainable parameters.
The baseline model uses:

Loss: categorical_crossentropy
Optimizer: SGD
Epochs: 10

The baseline achieved approximately:

Training Accuracy: 17.79%
Validation Accuracy: 18.37%

# 🧪 Experiments

# Different configurations were tested by changing:

Number of hidden layers
Number of neurons
Activation functions
Number of epochs
Batch size
Optimizer

# Activation functions tested include:

Sigmoid
Tanh
ReLU

# The results were stored using the following metrics:

Training Loss
Validation Loss
Training Accuracy
Validation Accuracy
Training Time

## 📈 Model Results
Model	Hidden Layers	Activation	Epochs	Batch Size	Train Accuracy	Validation Accuracy
Baseline	0	-	10	50000	15.27%	16.28%
Model 1	0	-	50	50000	43.06%	43.32%
Model 2	0	-	10	32	90.83%	90.71%
Model 3	0	-	50	32	92.39%	91.86%
Model 4	0	-	50	64	91.86%	91.44%
Model 5	1	Sigmoid	50	50000	14.81%	15.41%
Model 6	1	Sigmoid	50	32	94.56%	94.13%
Model 7	1	Sigmoid	50	32	94.26%	93.91%
Model 8	1	Tanh	50	32	98.07%	96.70%
Model 9	1	ReLU	50	32	98.62%	97.18%
Model 10	2	ReLU + Tanh	50	32	99.74%	97.54%
Model 11	2	Tanh + ReLU	50	32	99.43%	97.48%
Model 12	3	ReLU + ReLU + ReLU	50	32	99.98%	97.44%
Model 13	3	ReLU + ReLU + ReLU	100	32	100.00%	97.45%

Results are taken from the experiment results recorded in the notebook.

## 🏆 Best Model

# The best validation accuracy was achieved by the model with:

2 Hidden Layers
128 and 64 neurons
ReLU + Tanh activation
50 epochs
Batch size: 32
Training Accuracy: 99.74%
Validation Accuracy: 97.54%

# This model performed better on validation data than the deeper 3-layer models.

## 📌 Key Findings
Increasing the number of epochs generally improved training accuracy.
Smaller batch sizes significantly improved model performance.
Adding hidden layers improved the model compared with the baseline.
ReLU and Tanh performed better than Sigmoid in the experiments.
Increasing model depth and epochs can increase training accuracy but may also lead to overfitting.
The deeper models achieved very high training accuracy, while validation accuracy remained around 97%.

## ✅ Conclusion
The experiment shows that SGD, smaller batch sizes, hidden layers, and suitable activation functions can significantly improve MNIST digit classification. ReLU and Tanh performed better than Sigmoid, and increasing epochs improved training accuracy but could cause overfitting. Overall, the deeper neural network models performed much better than the baseline model.

