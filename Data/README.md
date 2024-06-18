# Lung Cancer 14K Dataset

## Overview

This dataset consists of 14,819 images of lung tissue, categorized into three classes: Benign, Malignant, and Normal. The dataset is designed to facilitate the training and evaluation of machine learning models for lung cancer detection and classification.

## Dataset Details

- **Total Images**: 14,819
- **Classes**:
  - Benign
  - Malignant
  - Normal
- **Image Format**: JPEG/PNG
- **Image Size**: Varies

## Download

The dataset can be downloaded from Kaggle using the following link:

[Download Lung Cancer 14K Dataset](https://www.kaggle.com/datasets/sangemjayaprakash/lung-cancer-14k/data)

## File Structure

The dataset is organized into the following structure:

lung-cancer-14k/  
├── benign/  
│ ├── image1.jpg  
│ ├── image2.jpg  
│ └── ...  
├── malignant/  
│ ├── image1.jpg  
│ ├── image2.jpg  
│ └── ...  
└── normal/  
├── image1.jpg  
├── image2.jpg  
└── ...  


## Usage

1. **Download the dataset** from the provided Kaggle link.
2. **Extract the contents** into your project directory.
3. **Load the dataset** using your preferred method (e.g., TensorFlow, PyTorch).

### Example (TensorFlow)

```python
import tensorflow as tf
from tensorflow.keras.preprocessing.image import ImageDataGenerator

# Define the data directory
data_dir = "path/to/lung-cancer-14k/"

# Create an ImageDataGenerator
datagen = ImageDataGenerator(rescale=1./255, validation_split=0.2)

# Load the training data
train_data = datagen.flow_from_directory(
    data_dir,
    target_size=(224, 224),
    batch_size=32,
    class_mode='categorical',
    subset='training'
)

# Load the validation data
val_data = datagen.flow_from_directory(
    data_dir,
    target_size=(224, 224),
    batch_size=32,
    class_mode='categorical',
    subset='validation'
)
```