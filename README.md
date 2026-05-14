# CIFAR-10 Image Classification using CNN and Transfer Learning

## Project Overview

This project explores image classification on the CIFAR-10 dataset using both:

1. A custom Convolutional Neural Network (CNN)
2. Transfer Learning models:

   * MobileNetV2
   * DenseNet121
   * EfficientNetB0

The project was developed and trained using Google Colab with TensorFlow and Keras.

The goal of this project was to:

* Understand image classification workflows
* Compare traditional CNNs with modern pretrained architectures
* Evaluate transfer learning performance on CIFAR-10
* Analyze model accuracy, overfitting, validation stability, and computational efficiency

---

# Dataset

## CIFAR-10

CIFAR-10 is a widely used benchmark dataset for image classification.

### Dataset Details

* Total Images: 60,000
* Training Images: 50,000
* Testing Images: 10,000
* Image Size: 32 × 32 × 3
* Number of Classes: 10


---

# Technologies Used

## Development Environment

* Google Colab
* Python 3

## Libraries and Frameworks

* TensorFlow
* Keras
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Pandas

---

# Project Structure

```text
CIFAR10-Project/
│
├── cnn_model.ipynb
├── mobilenet_model.ipynb
├── densenet_model.ipynb
├── efficientnet_model.ipynb
├── comparison_notebook.ipynb
├── saved_models/
│   ├── cnn_model.keras
│   ├── mobilenet_model.keras
│   ├── densenet_model.keras
│   └── efficientnet_model.keras
└── README.md
```

---

## 1. Custom CNN Model

A custom CNN architecture was designed from scratch.

### Architecture Components

* Convolutional Layers
* Batch Normalization
* Max Pooling
* Dropout
* Global Average Pooling

---

# Training Strategy

For transfer learning models:

1. Base model layers were frozen
2. Only the custom classifier was trained
3. Adam optimizer was used
4. Validation accuracy was monitored

## Fine-Tuning

After initial convergence:

* Selected deeper layers were unfrozen
* Learning rate was reduced
* Additional training epochs were applied

### Fine-Tuning Benefits

* Improved validation accuracy
* Better feature adaptation to CIFAR-10
* Reduced train-validation performance gap

---

# Challenges Faced

## 1. RAM Usage

Initial preprocessing pipelines caused high RAM consumption due to resizing all images simultaneously.

### Solution

Implemented TensorFlow dataset pipelines for dynamic preprocessing.

---

## 2. Overfitting

Training accuracy increased while validation accuracy plateaued.

### Solutions

* Dropout layers
* Smaller classifier heads
* Fine-tuning selected layers only
* Early stopping

---

## 3. Runtime Disconnections in Colab

Google Colab occasionally disconnected during long training sessions.

### Solutions

* Saved models to Google Drive
* Reduced unnecessary epochs
* Used lightweight architectures

---

# Future Improvements

Potential future enhancements include:

* Data augmentation
* Hyperparameter optimization
* Ensemble learning
* Advanced fine-tuning strategies
* Learning rate schedulers
* Larger image resolutions
* Training on larger datasets

---

# Conclusion

This project demonstrated the effectiveness of transfer learning for image classification tasks on CIFAR-10.

Key conclusions:

* Transfer learning significantly outperformed the custom CNN baseline.
* MobileNetV2 provided excellent efficiency and fast training.
* DenseNet121 achieved stronger feature extraction.
* EfficientNetB0 delivered the best overall balance between accuracy and efficiency.
* Fine-tuning pretrained layers improved validation performance.
* TensorFlow dataset pipelines improved memory efficiency and training stability.

Overall, EfficientNetB0 achieved the strongest generalization performance among the tested architectures.

---

# Team Members

| Member | Model          |
| ------ | -------------- |
| Laxmi  | MobileNetV2    |
| Jan    | DenseNet121    |
| Bruno  | EfficientNetB0 |

---

# References

* TensorFlow Documentation
* Keras Applications Documentation
* CIFAR-10 Dataset
* ImageNet Pretrained Models
* Google Colab Documentation
