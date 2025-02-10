# Explanation of the trained model
# Model Card: Deepfake Detection Using Optical Flow and CNN-LSTM with Bayesian Optimization

## Model Overview
This model is designed for deepfake video detection by analyzing motion inconsistencies using optical flow features. Instead of focusing solely on spatial inconsistencies in individual frames, it captures temporal coherence issues by leveraging a CNN-LSTM hybrid architecture. Bayesian Optimization is used for hyperparameter tuning to enhance model performance given limited computational resources.

## Model Details
- **Model Type**: CNN-LSTM hybrid
- **Primary Goal**: Detect deepfake videos by analyzing motion inconsistencies through optical flow
- **Key Components**:
  - EfficientNet-B0 for spatial feature extraction
  - LSTM for temporal pattern recognition
  - Bayesian Optimization for hyperparameter tuning
- **Inputs**: Consecutive video frames converted into optical flow maps
- **Outputs**: Binary classification (real vs. fake)

## Intended Use
### Primary Use Case
Detecting deepfake videos based on motion distortions.

### Users
- Researchers
- AI practitioners
- Cybersecurity experts

### Deployment Scenarios
- Video authentication systems
- Forensic analysis
- Media integrity verification

## Training Data
- **Dataset Used**: [Deep Fake Detection (DFD) Dataset](https://www.kaggle.com/datasets/sanikatiwarekar/deep-fake-detection-dfd-entire-original-dataset)
- **Preprocessing**:
  - Extract frames from each video
  - Standardize sequence lengths
  - Split data (80% train, 20% test, holdout set per class)
  - Compute Optical Flow dynamically during training

## Performance Metrics
- **Evaluation Metrics**:
  - Accuracy
  - Precision
  - Recall
  - AUC-ROC

### Baseline Comparison
A CNN-only classifier serves as a baseline to quantify LSTM’s contribution.

## Ethical Considerations
### Bias & Fairness
Dataset-dependent biases could impact performance across different demographics.

### Misuse Risks
Potential adversarial attacks or bypass techniques may emerge; requires continuous evaluation.

### Privacy
Ensuring datasets do not contain personally identifiable information (PII).

## Limitations
### Computational Constraints
Optical Flow computation increases processing demands.

### Dataset Limitations
May not generalize well to unseen deepfake generation techniques.

### Future Work
- Exploring Transformer-based models
- Investigating 3D video mapping techniques
- Implementing AutoML for model optimization

## Citation
If using this model, please cite the repository and dataset accordingly.

