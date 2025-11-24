# 🐾 ZooLinguistic  
### Real-Time Animal-Name Voice Command Classifier

## 🚀 Overview
ZooLinguistic is a **real-time audio classification system** that recognizes spoken animal names using machine learning and MFCC-based audio feature extraction. The system processes **540 labeled audio samples**, trains multiple classifiers (SVM, Random Forest, KNN, MLP, AdaBoost, etc.), and deploys a fully functional **cross-platform Streamlit interface** for live prediction.

The optimized pipeline uses **K-Nearest Neighbors (KNN)** with **feature selection**, achieving **93.52% accuracy** while reducing feature dimensionality from **5,186 MFCC features to 2,700**.

---

## 🎙️ Data Acquisition
Based on the acquisition experiments (see Data acquisition script):

- Recorded **540 audio samples** from six animal-name classes:  
  **Perro, Gato, Jirafa, Tortuga, Avestruz, Elefante**
- Each class includes **90 samples** from three speakers
- Sampling rate: **44.1 kHz**
- Real-time acquisition uses a **circular audio buffer** and multithreading
- Automatic fallback between mono and stereo channels for robust capture

---

## 🎚️ Audio Preprocessing
- Applied **Chebyshev II bandpass filtering** (10–15,000 Hz)
- Extracted **MFCC features** using 2048-point FFT
- Flattened MFCC matrices into final feature vectors
- Dataset shape:
  ```
  540 samples × 5186 features + 1 label column
  ```

---

## 🧠 Model Training & Evaluation
### Models Implemented
- Support Vector Machines (Linear, RBF, Polynomial)
- Random Forest
- KNN
- Logistic Regression
- Decision Tree
- LDA
- AdaBoost
- MLP Classifier

### Best Results
| Model | Accuracy |
|-------|----------|
| **KNN (k=3)** | **0.9352** |
| Random Forest (260 trees) | 0.9204 |
| Linear SVM | 0.91 |

### Feature Optimization
- Applied **filter-based feature selection**
- Reduced dimensionality: **5,186 → 2,700**
- Result: improved computational efficiency + higher accuracy

---

## ⚙️ Real-Time Streamlit App
The `app_online_prototype.py` provides:

- Real-time audio capture via multithreaded buffer
- MFCC extraction and immediate classification
- Clean, user-friendly interface for predictions
- Fully cross-platform (Windows/Linux; macOS supported with adjustments)

---

## 🏗️ Pipeline Architecture
1. **Data Acquisition** → Live microphone capture  
2. **Preprocessing** → Filtering + MFCC extraction  
3. **Model Training** → Training 10 ML models  
4. **Feature Selection** → Dimensionality reduction  
5. **Deployment** → Streamlit real-time classifier  
6. **Model Serving** → SVM & KNN trained models  

---

## 🐾 Classes Recognized
- 🐶 Perro  
- 🐱 Gato  
- 🦒 Jirafa  
- 🐢 Tortuga  
- 🐦 Avestruz  
- 🐘 Elefante  

---

## 🔍 Key Technical Contributions
- Implemented an end-to-end **real-time voice classification system**
- Engineered **threaded audio acquisition** with circular buffering
- Built a complete **signal processing pipeline** using MFCCs
- Trained and benchmarked 10 ML classifiers on 540 audio samples
- Achieved **93.52% accuracy** via optimized KNN model
- Deployed a **Streamlit interface** for real-time prediction
- Performed **hyperparameter tuning & feature selection**
- Designed a dataset of **540 labeled voice commands**

---

## 🧭 Technologies Used
Python · NumPy · SciPy · scikit-learn · python_speech_features · Streamlit · SoundDevice · Matplotlib

