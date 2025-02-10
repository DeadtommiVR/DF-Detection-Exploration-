# Explanation of the dataset
# Deepfake Detection Dataset - Datasheet

## Motivation

### For what purpose was the dataset created?
This dataset was created to develop and evaluate **deepfake video detection models**, specifically by analyzing **motion inconsistencies** using **optical flow features**. Deepfake videos often contain unnatural motion due to frame interpolation artifacts, which this dataset helps identify.

### Who created the dataset?
The dataset was assembled from the **Deep Fake Detection (DFD) dataset** and processed for this project. The preprocessing, extraction, and organization of data were done as part of an independent research effort.

### Any other comments?
- The dataset is **not an original dataset** but a **processed version** of an existing dataset.  
- The preprocessing steps focus on **temporal inconsistencies** rather than spatial frame-level artifacts.

---

## Composition

### What do the instances in the dataset represent?
Each instance represents a **video sequence** of **305 consecutive frames** extracted from **real and fake videos**. The dataset is divided into:
- **Real video sequences** (genuine human recordings)
- **Fake video sequences** (deepfake-generated content)

### How many instances are there?
- The dataset contains **a balanced set of real and fake sequences**.
- Each sequence consists of **305 frames**.

### Does the dataset contain all possible instances or is it a sample?
This dataset is a **subset of a larger dataset** (DFD) and was sampled based on availability and feasibility of processing. The sampling **prioritizes videos with noticeable motion artifacts**.

### What does each instance consist of?
Each instance consists of:
- **305 extracted frames** from a video.
- **Optical Flow feature maps** computed dynamically during training.

### Are there labels for the data?
Yes:
- `0` for real videos.
- `1` for fake videos.

### Is there missing information in the dataset?
No missing data after preprocessing.

### Are there recommended train/test splits?
Yes:
- **Train:** 80% of the dataset.
- **Test:** 20% of the dataset.
- **Holdout Set:** 1 real and 1 fake sequence for final validation.

### Does the dataset contain confidential or sensitive information?
No. The dataset consists of **publicly available deepfake detection data**.

### Any other comments?
- The dataset is **structured for deep learning models**, specifically **CNN-LSTM architectures**.
- Optical Flow is computed **on-the-fly** rather than being precomputed.

---

## Collection Process

### How was the data acquired?
The dataset was sourced from the **Deep Fake Detection (DFD) dataset** and processed by:
1. **Extracting frames** from each video.
2. **Standardizing frame sequence lengths** to 305 frames.
3. **Computing Optical Flow dynamically** for motion analysis.

### Over what time frame was the data collected?
The original dataset was collected as part of deepfake research between **2019-2022**.

### Were ethical review processes conducted?
No specific review process was required since this dataset is publicly available.

### Any other comments?
- The dataset was curated to focus on **temporal deepfake artifacts**, rather than static frame-level inconsistencies.

---

## Preprocessing

### What preprocessing was done?
- **Frame Extraction:** Videos were split into sequences of 305 frames.
- **Standardization:** All sequences were trimmed or padded to 305 frames.
- **Optical Flow Computation:** Implemented dynamically during training.
- **Dataset Splitting:** Train, test, and holdout sets were created.

### Was raw data saved?
No, only the processed sequences and structured dataset were retained.

### Any other comments?
- Optical Flow is **computed on-the-fly**, reducing storage requirements.

---

## Uses

### What other tasks could this dataset be used for?
- Deepfake detection using different architectures (e.g., Transformers, 3D CNNs).
- Motion pattern analysis in video forensics.
- Research into **optical flow-based anomaly detection**.

### Are there any risks in using this dataset?
Yes:
- The dataset is **not fully representative** of all deepfake types.
- **Static frame inconsistencies** are **not** the primary focus.
- Performance may degrade on **deepfakes that use advanced motion correction**.

### Any other comments?
- Future datasets should include **3D optical flow mapping** to capture richer temporal distortions.

---

## Distribution

### Will the dataset be shared publicly?
No, since it is a processed version of an existing dataset.

### How will the dataset be distributed?
Not publicly distributed. It is used **internally for research and model development**.

### Will the dataset be distributed under a license?
Not applicable, since it is derived from an external dataset.

### Any other comments?
- The dataset is not open-source but can be **reproduced using the preprocessing scripts**.

---

## Maintenance

### Who will maintain the dataset?
The dataset will be maintained by the project team for research purposes.

### Any other comments?
- Updates to the dataset may include **3D spatiotemporal deepfake features** in future versions.
- If extended, **new data sources will be integrated** for a broader evaluation.

---

## Summary
- This dataset is a **preprocessed deepfake detection dataset** designed for **motion analysis** using **Optical Flow and CNN-LSTM models**.
- It is **not publicly distributed** but can be **recreated from the preprocessing scripts**.
- Future iterations may include **multi-scale temporal analysis** and **advanced deepfake correction techniques**.

---

This datasheet provides full transparency on **what the dataset is, how it was created, and how it should be used**. It ensures responsible usage and documentation for researchers and developers working on deepfake detection.  

