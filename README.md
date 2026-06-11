# Traffic Sign Recognition for Autonomous Vehicles

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.0+-orange.svg)
![Keras](https://img.shields.io/badge/Keras-2.0+-red.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-4.0+-green.svg)
![Accuracy](https://img.shields.io/badge/Test%20Accuracy-98.56%25-brightgreen.svg)

## 📌 Project Overview
[cite_start]This repository contains a deep learning project dedicated to **Traffic Sign Recognition (TSR)**, a fundamental subfield of perception engineering in Advanced Driver-Assistance Systems (ADAS) and Autonomous Driving Systems[cite: 1, 4]. 

[cite_start]By developing a customized **Convolutional Neural Network (CNN)** and employing complex image processing pipelines, this system classifies **43 unique types of traffic signs** from the **German Traffic Sign Recognition Benchmark (GTSRB)** dataset[cite: 1, 15]. [cite_start]The final model surpasses typical real-world baselines, achieving an outstanding validation/test accuracy of **98.56%**[cite: 1, 37].

[cite_start]To bridge the gap between model training and deployment, a functional **Desktop Graphical User Interface (GUI)** prototype has been built to test the classifier in real-time[cite: 1, 39].

---

## 🛠️ Key Objectives & Challenges Addressed
* [cite_start]**Target Classification:** Detect and isolate distinct semantic visual classes across 43 different standard categories[cite: 15, 28].
* [cite_start]**Environmental Variance Mitigation:** Address challenges such as extreme illumination fluctuations (shadows, low daylight), scaling, motion blur, and structural distortion[cite: 11, 13].
* [cite_start]**Class Imbalance Resolution:** Utilize systematic data augmentation techniques to ensure minority classes are not systematically ignored by the gradient optimization process[cite: 14, 31].

---

## 🧬 Pipeline Architecture

### 1. Preprocessing Pipeline
[cite_start]To maximize feature identification, raw images pass through a three-stage preprocessing layer before inference[cite: 17, 29]:
* [cite_start]**Region of Interest (ROI) Cropping:** Eliminates noisy peripheral pixel information, centering the array focus strictly on bounding-box vectors containing the traffic sign[cite: 1, 29].
* [cite_start]**Contrast Limited Adaptive Histogram Equalization (CLAHE):** Overcomes harsh atmospheric illumination and heavy shading variations by locally enhancing regional contrast boundaries without over-amplifying local background noise[cite: 1, 17].
* [cite_start]**Data Augmentation:** Artificially inflates dataset scale through targeted random spatial operations (rotation ranges, vertical/horizontal shifts, zoom variations) to enforce generalization properties[cite: 1, 31].

### 2. Deep Learning Model Design
[cite_start]The classification engine features a deep Convolutional Network built with standard modular layers[cite: 1, 33]:
* [cite_start]**Convolutional Blocks & Batch Normalization:** Multiple blocks of `Conv2D` feature extractors integrated directly with `BatchNormalization` to maintain internal covariate shift control and ensure swift validation convergence[cite: 34].
* [cite_start]**Regularization Overfit Defenses:** Strategically embedded `Dropout` nodes to interrupt co-dependency traps among neuron parameters[cite: 35].
* [cite_start]**Dense Classification Head:** A sequence of dense linear multi-layers culminating in a 43-unit vector configured with a `Softmax` operational layer for probability distribution estimation[cite: 15, 32].

---

## 📈 Performance & Results
* [cite_start]**Test Accuracy:** **98.56%** on completely unseen dataset arrays[cite: 1, 37].
* [cite_start]**Learning Convergence:** Training analytics curves confirm a highly stable learning trajectory, characterized by minimum divergence between training data and validation loss limits[cite: 36].

---

## 💻 GUI Application Prototype
[cite_start]The directory contains a responsive desktop application built with `Tkinter` to facilitate testing[cite: 1, 39]:
1. [cite_start]**Image Upload Window:** Drag or browse custom local file paths to parse immediate context evaluation matrices[cite: 40].
2. [cite_start]**Instant Classification Engine:** Feeds preprocessed imagery matrix elements directly into the deep graph context[cite: 41].
3. [cite_start]**Confidence Feedback Monitor:** Explicitly returns absolute category matching identifiers alongside numerical prediction parameters to measure network classification confidence[cite: 38].

---

## 📁 Repository Structure
```text
├── Data/
[cite_start]│   ├── Train.csv               # Dataset training metadata annotations 
[cite_start]│   └── Test.csv                # Dataset test metadata annotations 
├── Notebook/
│   └── Researched TSR .ipynb   # Complete model design, preprocessing, & evaluation pipeline
├── App/
[cite_start]│   └── gui_app.py              # Tkinter application code for the system presentation [cite: 1, 39]
├── Models/
│   └── tsr_cnn_model.h5        # Serialized weights file for the trained network architecture
├── Requirements.txt            # System dependencies to reproduce environments
└── README.md
