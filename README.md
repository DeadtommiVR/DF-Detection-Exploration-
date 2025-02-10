# Deepfake Detection Using Optical Flow and CNN-LSTM with Bayesian Optimization

## Project Overview
This project investigates deepfake video detection by leveraging motion inconsistencies, which are often present due to interpolation artifacts in synthetic videos. Instead of relying purely on spatial inconsistencies in individual frames, our approach focuses on temporal coherence issues by analyzing optical flow features extracted between consecutive frames.

We employ a CNN-LSTM hybrid model to capture both spatial features (CNN) and temporal motion irregularities (LSTM). Bayesian Optimization is used to automate hyperparameter tuning, improving efficiency given our limited computational resources.

The project originally intended to use PCA and statistical feature engineering, but due to challenges with dataset handling and time constraints, we pivoted towards a fully deep learning-based pipeline that dynamically computes Optical Flow during training.

---

## Project Objectives

### 1. Feature Extraction via Optical Flow
- Compute Farneback Dense Optical Flow dynamically between consecutive frames.
- Convert Optical Flow vectors into grayscale magnitude maps to highlight motion distortions.
- Stack Optical Flow maps as additional input channels for CNN processing.

### 2. Deep Learning Model (CNN + LSTM)
- Use EfficientNet-B0 as the CNN backbone for spatial feature extraction.
- Feed CNN-extracted features into an LSTM to model temporal inconsistencies.
- Apply Bayesian Optimization for automatic hyperparameter tuning, optimizing learning rate, batch size, and LSTM hidden units.

### 3. Training and Evaluation
- Train the model on an 80/20 train-test split, with a separate holdout set for final evaluation.
- Evaluate performance using Accuracy, Precision, Recall, and AUC-ROC.
- Compare results against a baseline CNN-only classifier to quantify the value of temporal modeling.

### 4. Challenges and Lessons Learned
- Dataset handling was more complex than expected, requiring extensive preprocessing.
- The decision to compute Optical Flow on-the-fly helped avoid storage issues but increased processing demands.
- Given more time and better computational resources, 3D video mapping, Transformer-based models, and AutoML techniques would have been explored.

---

## Dataset

**Source**: [Deep Fake Detection (DFD) Dataset](https://www.kaggle.com/datasets/sanikatiwarekar/deep-fake-detection-dfd-entire-original-dataset)  

**Preprocessing Steps:**
- Extract frames from each video and store them in video-named subdirectories.
- Standardize all sequences to the shortest video length.
- Split data into train (80%), test (20%), and holdout (1 sequence per class).
- Compute Optical Flow dynamically during training instead of precomputing.

---

## Project Structure



