# 🌦️ Multi-Weather Classification System

This documentation provides a detailed explanation of a Weather Classification System implemented using deep learning in Python. The goal of this system is to accurately classify different weather conditions from images using transfer learning techniques.

---

## Overview

The project employs a dataset containing images of seven different weather conditions: Cloudy, Fog, Rain, Sand, Shine, Snow, and Sunrise. The model uses Transfer Learning with EfficientNetB3 as the base model to achieve high classification accuracy of 94%.

## Libraries Used

The following Python libraries were used to implement the model:

- **NumPy & Pandas:** For data manipulation and analysis
- **Matplotlib & Seaborn:** For data visualization
- **TensorFlow/Keras:** For building and training the deep learning model
- **PIL (Python Imaging Library):** For image processing
- **OpenCV (cv2):** For additional image processing capabilities
- **Scikit-learn:** For model evaluation and data splitting

## Project Structure

**1. Data Preparation:**
- Images are organized into folders representing each weather class
- File paths and corresponding labels are gathered into a DataFrame
- The dataset is split into training (80%), validation (10%), and test (10%) sets using stratified sampling

**2. Data Loading and Augmentation:**
- `ImageDataGenerator` is used to load images and create batches
- Images are resized to 224×224 pixels for compatibility with EfficientNetB3

**3. Model Architecture:**
- **Base Model:** Pre-trained EfficientNetB3 with weights from ImageNet
- **Additional Layers:**
  - Batch Normalization
  - Dense layer with 256 units and ReLU activation
  - Dropout (45%) for regularization
  - Output layer with softmax activation for 7-class classification
- **Regularization Techniques:** L1 and L2 regularization to prevent overfitting

**4. Model Training:**
- Trained for 25 epochs with Adamax optimizer
- Learning rate of 0.001
- Categorical cross-entropy loss function
- Multiple evaluation metrics: accuracy, precision, recall, and AUC

**5. Model Evaluation:**
- Training and validation loss/accuracy curves
- Confusion matrix
- Detailed classification report

## Evaluation Results

- **Test Accuracy:** 94%
- **Per-Class Performance:**
  - Cloudy: 93% F1-score
  - Fog: 83% F1-score (lowest performing class)
  - Rain: 100% F1-score
  - Sand: 88% F1-score
  - Shine: 100% F1-score
  - Snow: 100% F1-score
  - Sunrise: 97% F1-score

## Model Performance Highlights

The model demonstrates exceptional performance on most weather conditions, particularly Rain, Shine, and Snow with perfect F1-scores. Fog and Sand classifications show slightly lower performance, indicating these categories may have more visual similarities with other classes or more varied appearances within the class.

## Conclusion

The weather classification system implemented with transfer learning demonstrates high accuracy in identifying different weather conditions from images. This model can be useful for various applications including:
- Automated weather reporting from camera feeds
- Enhanced meteorological analysis
- Smart home systems that respond to weather conditions
- Transportation safety systems

Further improvements could focus on addressing the lower-performing weather classes through additional data collection or specialized augmentation techniques.
