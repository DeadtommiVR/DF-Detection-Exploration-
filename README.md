# **Deepfake Detection Using Optical Flow, PCA, and Bayesian Optimization**

## **Project Overview**
This project explores deepfake video detection using **optical flow residuals**, **Principal Component Analysis (PCA)**, and **Bayesian Optimization** to efficiently classify real vs. fake videos. Rather than relying purely on deep learning-based frame-level inconsistencies, our approach focuses on **motion anomalies**—a domain where deepfake video synthesis struggles due to interpolation artifacts.

By leveraging **dimensionality reduction via PCA** and **hyperparameter tuning with Bayesian Optimization**, we aim to create a lightweight but robust classification pipeline that can effectively detect deepfake-induced motion distortions with limited computational resources.

---

## **Project Objectives**
1. **Feature Engineering for Motion-Based Detection**
   - Extract **optical flow residuals** to analyze motion inconsistencies.
   - Use **Principal Component Analysis (PCA)** to reduce feature dimensionality and highlight key variations.
   - Identify the **relationships between interpolated frames** to detect synthetic frame transitions.
   - Compute **optical flow difference maps** to highlight anomalies.
   - Perform **statistical analysis on motion vectors** (e.g., entropy, variance, smoothness) to quantify deepfake artifacts.
   - Apply **K-Means clustering on PCA-transformed optical flow features** to discover deepfake-specific patterns.

2. **Machine Learning Model Development**
   - Train a baseline **SVM or Random Forest** model on PCA-reduced features.
   - Integrate **Bayesian Optimization** to fine-tune hyperparameters for optimal performance.
   - Compare against a simple **MLP classifier with Bayesian-tuned backpropagation**.

3. **Evaluation and Performance Metrics**
   - Measure performance using **Accuracy, Precision, Recall, AUC-ROC, and RMSE**.
   - Visualize feature separability using **PCA scatter plots and optical flow heatmaps**.

4. **Practical Implementation & Reproducibility**
   - Ensure computational feasibility by limiting dataset size and optimizing data preprocessing.
   - Structure the project for **easy replication and deployment**, adhering to best practices for dataset management, model evaluation, and GitHub documentation.
   
---

## **Dataset**
- **Primary Choice**: [Deep Fake Detection DFD Dataset](https://www.kaggle.com/datasets/sanikatiwarekar/deep-fake-detection-dfd-entire-original-dataset)
- **Alternative**: [Multi-Fidelity Deepfake Video Dataset](https://www.kaggle.com/competitions/multi-ffdv/data) *(if a smaller subset is viable)*

Data preprocessing steps:
- Extract frames from videos.
- Compute **optical flow** using Farneback or RAFT.
- Apply **PCA for feature selection and dimensionality reduction**.
- Split dataset into **train (70%), validation (15%), and test (15%)**.

---

## **Project Structure**
```
Deepfake-Detection-Project/
│── data/                  # Datasets or links to datasets
│── src/                   # Source code scripts
│── notebooks/             # Jupyter notebooks (Colab exports go here)
│── results/               # Saved models, logs, or generated visualizations
│── README.md              # Project overview & instructions
│── requirements.txt       # List of dependencies
│── model_card.md          # Explanation of the trained model
│── data_card.md           # Explanation of the dataset
│── LICENSE                # License information (if open-source)
│── .gitignore             # Files to exclude from Git tracking
```

---

## **Installation & Usage**
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/YOUR-USERNAME/Deepfake-Detection-Project.git
   cd Deepfake-Detection-Project
   ```
2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
3. **Run the Notebook**:
   - Open `notebooks/deepfake_detection.ipynb` in Jupyter or Google Colab.
   - Follow the step-by-step instructions in the notebook.

---

## **Future Work**
- Integrating **K-Means clustering** to explore unsupervised feature separation.
- Experimenting with **Neural Architecture Search (NAS)** for model selection.
- Exploring **Differentiable Hyperparameter Optimization** techniques.

---

## **Contributors**
- **Your Name** (Project Lead)
- Additional contributors (if applicable)

For any questions or suggestions, please open an issue in this repository.

---

## **License**
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---



