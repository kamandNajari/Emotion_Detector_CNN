# 😊 Emotion Detector CNN

A real-time facial emotion recognition app built with a custom Convolutional Neural Network (CNN), trained from scratch on the FER-2013 dataset. Point your webcam at your face and watch it detect your emotion live — complete with a real-time probability chart, emotion-based visual effects, and a fun challenge mode.

## ✨ Features

- Real-time emotion detection from your webcam feed
- Detects 7 emotions: angry, disgust, fear, happy, neutral, sad, surprise
- Live bar chart showing the probability of every emotion, updated continuously
- Unique visual effect for each detected emotion (confetti for happy, pulsing red border for angry, color tints for sad/fear/disgust, expanding ring for surprise)
- **Challenge Mode**: press a key to get a random emotion prompt, then try to make that expression within a time limit to score points

## 🧠 How This Model Was Built

The CNN behind this project was **trained from scratch** (not a pre-trained model) using TensorFlow/Keras on Google Colab with a free GPU. Here's the process:

1. The **FER-2013 dataset** (~35,000 labeled grayscale face images, 48x48 pixels) was downloaded from Kaggle
2. A custom CNN architecture was built using stacked Conv2D, BatchNormalization, ReLU, and MaxPooling layers, followed by Global Average Pooling and a Dense output layer
3. Data augmentation (rotation, shifting, flipping, zoom) was applied to help the model generalize better from a limited dataset
4. The model was trained with EarlyStopping to avoid overfitting
5. The trained model was exported as `emotion_model.keras` and used here for real-time inference

**Current validation accuracy: ~55%**

This is a reasonable result for FER-2013, which is a notoriously difficult dataset — even published research models typically score between 65-75% on it, due to low image resolution, ambiguous expressions, and class imbalance (some emotions like "disgust" have very few examples). Accuracy improvements are planned for a future version (see below).

## 🔮 Planned Improvements

- Train on a larger and more balanced dataset
- Experiment with deeper architectures and transfer learning
- Fine-tune data augmentation parameters
- Increase training epochs with a more patient early-stopping strategy

## 📦 Requirements

- Python 3.9 or newer
- A working webcam

## 📥 Clone the Repository

```bash
git clone https://github.com/kamandNajari/Emotion_Detector_CNN.git
cd Emotion_Detector_CNN
```

## 🚀 Installation

```bash
pip install -r requirements.txt
```

## 📓 Running the Notebook

Make sure Jupyter is installed:

```bash
pip install jupyter
```

Then launch it:

```bash
jupyter notebook
```

Open `emotion_detector_live.ipynb` from the Jupyter interface and run the cell (Shift + Enter).

The face detection model is downloaded automatically on first run — no manual setup needed.

## ▶️ How to Use

1. Run the notebook cell — your webcam will open alongside a live emotion probability chart
2. Your dominant emotion is displayed on screen with a colored box around your face
3. Each emotion triggers a unique visual effect
4. Press **c** to start Challenge Mode — you'll be given a random emotion to act out within a few seconds to earn points
5. Press **q** to quit

## 🛠️ Tech Stack

- [TensorFlow / Keras](https://www.tensorflow.org/) — CNN model architecture and training
- [MediaPipe](https://developers.google.com/mediapipe) — real-time face detection
- [OpenCV](https://opencv.org/) — webcam capture, rendering, and visual effects
- [NumPy](https://numpy.org/) — numerical processing

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

Thank you for checking out this project! ✨
