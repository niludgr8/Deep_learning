# 🧠 ANN Handwritten Digit Recognition (MNIST)

A deep learning project that uses an **Artificial Neural Network (ANN)** built with TensorFlow/Keras to recognize handwritten digits (0–9) from the MNIST dataset with ~98% accuracy.

---

## 📁 Project Structure

```
ann-mnist/
├── ann_mnist.py              # Main training & evaluation script
├── ann_mnist_model.keras     # Saved model (generated after training)
├── training_curves.png       # Accuracy & loss plots (generated after training)
├── sample_predictions.png    # Sample prediction grid (generated after training)
└── README.md
```

---

## 🚀 Quick Start

### 1. Clone / Download
```bash
git clone https://github.com/your-username/ann-mnist.git
cd ann-mnist
```

### 2. Install Dependencies
```bash
pip install tensorflow numpy matplotlib
```

### 3. Run
```bash
python ann_mnist.py
```

That's it — the MNIST dataset downloads automatically on first run.

---

## 🏗️ Model Architecture

```
Input Layer       →  784 neurons  (flattened 28×28 image)
Hidden Layer 1    →  512 neurons  (ReLU + BatchNorm + Dropout 0.3)
Hidden Layer 2    →  256 neurons  (ReLU + BatchNorm + Dropout 0.3)
Hidden Layer 3    →  128 neurons  (ReLU)
Output Layer      →   10 neurons  (Softmax — one per digit class)
```

| Component        | Choice                     |
|------------------|----------------------------|
| Optimizer        | Adam (lr = 0.001)          |
| Loss Function    | Categorical Cross-Entropy  |
| Regularization   | Dropout + BatchNormalization |
| Early Stopping   | Patience = 5 epochs        |
| LR Scheduler     | ReduceLROnPlateau          |

---

## 📊 Dataset

| Split    | Samples | Description                   |
|----------|---------|-------------------------------|
| Train    | 60,000  | Handwritten digits (0–9)      |
| Test     | 10,000  | Unseen evaluation samples     |

- Image size: **28 × 28 pixels**, grayscale
- Preprocessing: Flattened to 784 features, normalized to `[0, 1]`
- Labels: One-hot encoded (10 classes)

---

## 📈 Results

| Metric         | Value     |
|----------------|-----------|
| Test Accuracy  | ~97–98%   |
| Test Loss      | ~0.07     |
| Training Time  | ~2–5 min  |

> Results may vary slightly depending on hardware and random seed.

---

## 🔍 What the Script Does

1. **Loads** MNIST data via `keras.datasets`
2. **Preprocesses** — normalizes pixel values, one-hot encodes labels
3. **Builds** a 3-layer ANN with dropout and batch normalization
4. **Trains** with early stopping and learning rate scheduling
5. **Evaluates** on the held-out test set
6. **Plots** training accuracy & loss curves → `training_curves.png`
7. **Predicts** on 10 random test samples → `sample_predictions.png`
8. **Saves** the trained model → `ann_mnist_model.keras`
9. **Reloads** the saved model to demonstrate inference

---

## 🔧 Requirements

| Package      | Version  |
|--------------|----------|
| Python       | ≥ 3.8    |
| TensorFlow   | ≥ 2.10   |
| NumPy        | ≥ 1.21   |
| Matplotlib   | ≥ 3.5    |

Install all at once:
```bash
pip install tensorflow numpy matplotlib
```

---

## 💡 Key Concepts Demonstrated

- **ANN (Artificial Neural Network)** — fully connected feed-forward network
- **Batch Normalization** — stabilizes and speeds up training
- **Dropout** — prevents overfitting by randomly deactivating neurons
- **Softmax activation** — converts output to class probabilities
- **Early Stopping** — halts training when validation loss plateaus
- **Model Serialization** — saving and loading trained models

---

## 🔮 Possible Improvements

- Switch to a **CNN** (Convolutional Neural Network) for higher accuracy (~99.7%)
- Add **data augmentation** (rotation, shifts) for better generalization
- Experiment with different optimizers (SGD + momentum, RMSProp)
- Try **Hyperparameter Tuning** with Keras Tuner
- Deploy as a **web app** using Flask or FastAPI

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

## 🙌 Acknowledgements

- [MNIST Database](http://yann.lecun.com/exdb/mnist/) — Yann LeCun, Corinna Cortes, Christopher Burges
- [TensorFlow / Keras](https://www.tensorflow.org/) — Google Brain Team
