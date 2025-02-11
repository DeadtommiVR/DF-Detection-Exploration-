Here's the **updated README** that reflects the changes in our approach, the challenges with the dataset, and what we would have done with more time and resources. It keeps the same structured format while making it clear that this project was adapted on the fly.

---

# **Deepfake Detection Using Optical Flow and CNN-LSTM with Bayesian Optimization**

## **Project Overview**
This project investigates **deepfake video detection** by leveraging **motion inconsistencies**, which are often present due to interpolation artifacts in synthetic videos. Instead of relying purely on spatial inconsistencies in individual frames, our approach focuses on **temporal coherence issues** by analyzing **optical flow features** extracted between consecutive frames.

We employ a **CNN-LSTM hybrid model** to capture both **spatial features (CNN)** and **temporal motion irregularities (LSTM)**. Bayesian Optimization is used to automate hyperparameter tuning, improving efficiency given our limited computational resources.

The project originally intended to use **PCA and statistical feature engineering**, but due to challenges with dataset handling and time constraints, we pivoted towards a **fully deep learning-based pipeline** that dynamically computes Optical Flow during training.

---

## **Project Objectives**
1. **Feature Extraction via Optical Flow**
   - Compute **Farneback Dense Optical Flow** dynamically between consecutive frames.
   - Convert Optical Flow vectors into **grayscale magnitude maps** to highlight motion distortions.
   - Stack Optical Flow maps as additional input channels for CNN processing.

2. **Deep Learning Model (CNN + LSTM)**
   - Use **EfficientNet-B0** as the CNN backbone for spatial feature extraction.
   - Feed CNN-extracted features into an **LSTM** to model temporal inconsistencies.
   - Apply **Bayesian Optimization for automatic hyperparameter tuning**, optimizing learning rate, batch size, and LSTM hidden units.

3. **Training and Evaluation**
   - Train the model on an **80/20 train-test split**, with a separate **holdout set for final evaluation**.
   - Evaluate performance using **Accuracy, Precision, Recall, and AUC-ROC**.
   - Compare results against a **baseline CNN-only classifier** to quantify the value of temporal modeling.

4. **Challenges & Lessons Learned**
   - Dataset handling was **more complex than expected**, requiring extensive preprocessing.
   - The decision to compute **Optical Flow on-the-fly** helped avoid storage issues but increased processing demands.
   - Given more time and better computational resources, **3D video mapping, Transformer-based models, and AutoML techniques** would have been explored.

---

## **Dataset**
- **Source**: [Deep Fake Detection (DFD) Dataset](https://www.kaggle.com/datasets/sanikatiwarekar/deep-fake-detection-dfd-entire-original-dataset)  
- **Preprocessing Steps:**
  - Extract frames from each video and store them in **video-named subdirectories**.
  - Standardize all sequences to the shortest video length.
  - Split data into **train (80%), test (20%), and holdout (1 sequence per class)**.
  - Compute **Optical Flow dynamically during training** instead of precomputing.

---

## **Project Structure**
```
Deepfake-Detection-Project/
│── data/                  # Datasets or links to datasets
│── src/                   # Source code scripts
│── notebooks/             # Jupyter notebooks (Colab exports go here)
│── results/               # Model checkpoints and evaluation metrics
│── README.md              # Project overview & instructions
│── requirements.txt       # Dependencies
│── model_card.md          # Model architecture and performance details
│── data_card.md           # Dataset details
│── LICENSE                # License information
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
3. **Run the Training Script**:
   - Open `notebooks/deepfake_detection.ipynb` in Jupyter or Google Colab.
   - Run all cells to preprocess data, train the CNN-LSTM model, and evaluate performance.

---

## **If We Had More Time & Resources**
Given **better computational power and more time**, the ideal approach would involve:
- **3D Spatiotemporal Feature Extraction**:  
  - Instead of relying only on Optical Flow, **3D CNNs or Transformers** could be used to analyze full spatiotemporal sequences.
- **Transformer-based Video Analysis**:  
  - Implementing **TimeSformer or Video Swin Transformer** for **attention-based motion tracking**.
- **Advanced Optical Flow Techniques**:  
  - Using **RAFT or PWC-Net** for more robust Optical Flow estimation.
- **Automated Model Optimization via AutoML**:  
  - Using **Neural Architecture Search (NAS) and differentiable hyperparameter tuning** to improve performance dynamically.
- **Multi-Scale Feature Fusion**:  
  - Combining **spatial, temporal, and frequency-domain features** to capture different types of deepfake artifacts.

---

## **Contributors**
- **Your Name** (Project Lead)
- Additional contributors (if applicable)

For any questions or suggestions, please open an issue in this repository.

---

## **License**
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

### **Key Updates from Original Plan**
✔ Switched from PCA-based statistical analysis to **CNN-LSTM deep learning**.  
✔ Abandoned precomputed Optical Flow in favor of **on-the-fly feature extraction**.  
✔ Adjusted dataset preprocessing to account for real-world data challenges.  
✔ Pivoted towards **Bayesian Optimization for backpropagation tuning** instead of manual hyperparameter selection.  

This README now fully reflects the **actual approach** we took while also documenting how the project could be expanded in the future. Let me know if anything needs tweaking!
