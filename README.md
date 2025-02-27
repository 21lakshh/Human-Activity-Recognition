# **Human Activity Recognition Using Smartphones**

## 1. Introduction
Human Activity Recognition (HAR) is an essential application of machine learning, where sensor data is used to classify human actions such as walking, sitting, and standing. This project evaluates the performance of various machine learning models on the **Human Activity Recognition Using Smartphones Dataset** from the UCI Machine Learning Repository. Our primary objective is to compare the model performance based on different feature extraction techniques:
- **Raw Inertial Data**
- **TSFEL Extracted Features**
- **Features Provided by Dataset Authors**

## 2. Dataset Description
The dataset consists of recordings of 30 subjects performing daily activities while wearing a smartphone on their waist. The phone captured accelerometer and gyroscope data at a frequency of 50Hz. The dataset includes:
- **Raw inertial signals** from accelerometers and gyroscopes.
- **Feature-engineered dataset** created by the original authors, containing a set of handcrafted features.

The activities classified are:
1. Walking
2. Walking Upstairs
3. Walking Downstairs
4. Sitting
5. Standing
6. Laying

## 3. Methodology
### 3.1 Evaluating Raw Inertial Data Using an LSTM Model
Long Short-Term Memory (LSTM) networks are well-suited for sequential data like sensor readings. We applied an LSTM-based deep learning model to classify activities based on raw inertial data. The output variables were **one-hot encoded** to match the classification framework.

**Results:**
- **Training Accuracy:** 94.29%
- **Validation Accuracy:** 95.92%
- **Test Accuracy:** 93.04%

### 3.2 Feature Extraction Using TSFEL
To analyze the impact of feature engineering, we extracted features from the raw inertial data using the **TSFEL (Time Series Feature Extraction Library)**. This library computes a wide range of time-domain, frequency-domain, and statistical features, converting raw sensor data into meaningful inputs for machine learning models.

We trained multiple machine learning models using the TSFEL-generated features:
- **Logistic Regression**
- **Decision Tree Classifier**
- **Random Forest Classifier**
- **Gradient Boosting Classifier**
- **K-Nearest Neighbors (KNN)**
- **XGBoost Classifier**
- **Support Vector Classifier (SVC)**

**Best Performing Model:**
- **SVC (Support Vector Classifier) with an accuracy of 95.31%**

### 3.3 Evaluating Features Provided by Dataset Authors
The dataset authors provided a feature-engineered version of the dataset containing handcrafted statistical and frequency-based features. We trained the same machine learning models on this dataset to compare performance.

**Best Performing Model:**
- **Logistic Regression with an accuracy of 95.86%**

## 4. Comparison of Model Performances
| Feature Set                      | Best Model               | Accuracy (%) |
|----------------------------------|--------------------------|--------------|
| Raw Inertial Data                | LSTM                     | 93.04        |
| TSFEL Extracted Features         | SVC                      | 95.31        |
| Author-Provided Features         | Logistic Regression      | 95.86        |

## 5. Conclusion
1. **Raw inertial data** performed well with LSTM, showing the effectiveness of deep learning in capturing sequential dependencies.
2. **TSFEL-extracted features** enhanced the performance of traditional machine learning models, with SVC achieving a high accuracy of 95.31%.
3. Raw inertial data performed well with **LSTM**, showing an accuracy of 93.04 on test data

This study highlights the significance of feature engineering in HAR and the effectiveness of different modeling approaches in improving classification accuracy.

