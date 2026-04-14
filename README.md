# Neural-Cryptanalysis: Learning Lightweight Ciphers

Can Neural Networks learn to encrypt? This project evaluates the security margins of lightweight block ciphers against Machine Learning attacks. We use **MLP**, **CNN**, and **Logistic Regression** to approximate encryption functions across multiple rounds.

## 🎯 Project Objective
The goal is to identify the "breaking point" where cryptographic diffusion becomes too complex for ML models. We treat encryption as a supervised learning task, using a "One-vs-Rest" framework to predict individual bits of the ciphertext.

## 🔐 Ciphers Analyzed
- **SIMON:** A Feistel-based cipher optimized for hardware.
- **SPECK:** An ARX-based cipher (Addition-Rotation-XOR) optimized for software.
- **PRESENT:** A Substitution-Permutation Network (SPN) using S-Boxes.



## 🧠 ML Architectures
- **Multi-Layer Perceptron (MLP):** Evaluates the model's ability to memorize non-linear mappings.
- **Convolutional Neural Network (CNN):** Uses a 4x4 bit-grid to detect spatial patterns in ciphertext.
- **Logistic Regression:** Serves as a linear baseline for simple round structures.

## 📊 Key Findings
- **Learnability vs. Rounds:** Most ciphers are highly learnable at Rounds 1–2 (Accuracy > 0.90) but drop to random-guess levels (Accuracy ≈ 0.50) by Round 5.
- **Structural Vulnerability:** **PRESENT** exhibited the highest vulnerability at low rounds, while **SPECK** showed stronger resistance to spatial extraction via CNN.
- **Diffusion:** The experiment validates that increased round counts effectively hide internal operations from neural pattern recognition.

## 🛠️ Requirements
- Python 3.x
- TensorFlow / Keras
- Scikit-learn
- NumPy & Matplotlib

## 🚀 Usage
Run the main experiment script to generate accuracy and Hamming distance plots:
```bash
python experiments.py

