# 😊 Real-Time Emotion Detection System

A real-time facial emotion detection application built with **OpenCV** and **Keras**, capable of identifying 7 human emotions directly from a live webcam feed — no cloud APIs, no DeepFace dependency.

---

## 🎯 Features

- 🎥 **Real-time webcam inference** — processes live video frame-by-frame
- 🧠 **Custom CNN model** — lightweight `.hdf5` model trained for emotion classification
- 👤 **Haar Cascade face detection** — fast, reliable face localization
- 🏷️ **7 emotion classes** — Angry, Disgust, Fear, Happy, Sad, Surprise, Neutral
- 🖥️ **macOS compatible** — uses `cv2.CAP_AVFOUNDATION` for native webcam support
- ⚡ **No internet required** — fully offline inference

---

## 🗂️ Project Structure

```
emotion-detection/
│
├── emotion_detection.py              # Main application script
├── emotion_model.hdf5                # Pre-trained Keras CNN model
├── haarcascade_frontalface_default.xml  # OpenCV face detector
└── README.md
```

---

## 🧠 How It Works

```
Webcam Frame
     │
     ▼
Convert to Grayscale
     │
     ▼
Haar Cascade Face Detection
     │
     ▼
Crop & Resize ROI → (64×64, grayscale)
     │
     ▼
Normalize Pixel Values (÷ 255)
     │
     ▼
CNN Model Inference
     │
     ▼
Argmax → Emotion Label
     │
     ▼
Overlay Bounding Box + Label on Frame
```

The model accepts a `(1, 64, 64, 1)` input tensor and outputs a probability distribution over the 7 emotion classes. The predicted class is the one with the highest softmax score.

---

## 📋 Requirements

- Python 3.7+
- OpenCV
- NumPy
- TensorFlow / Keras

Install dependencies:

```bash
pip install opencv-python numpy tensorflow
```

> **macOS users:** The script uses `cv2.CAP_AVFOUNDATION` for webcam access. No extra setup needed.

> **Linux/Windows users:** Change the capture line in `emotion_detection.py`:
> ```python
> # Linux / Windows
> cap = cv2.VideoCapture(0)
> ```

---

## 🚀 Getting Started

1. **Clone the repository**

```bash
git clone https://github.com/your-username/emotion-detection.git
cd emotion-detection
```

2. **Install dependencies**

```bash
pip install opencv-python numpy tensorflow
```

3. **Run the application**

```bash
python emotion_detection.py
```

4. **Quit** — press `q` in the webcam window to exit.

---

## 🏷️ Emotion Labels

| Index | Emotion   |
|-------|-----------|
| 0     | Angry     |
| 1     | Disgust   |
| 2     | Fear      |
| 3     | Happy     |
| 4     | Sad       |
| 5     | Surprise  |
| 6     | Neutral   |

---

## ⚙️ Configuration

You can tweak the following parameters inside `emotion_detection.py`:

| Parameter | Default | Description |
|-----------|---------|-------------|
| `scaleFactor` | `1.3` | How much the image is scaled per detection pass |
| `minNeighbors` | `5` | Minimum neighbor rectangles for a valid face |
| Input size | `64×64` | Expected model input resolution |

---

## 🔧 Troubleshooting

**Webcam not opening**
- Ensure no other app is using the camera
- On macOS, grant Terminal/IDE camera permissions in System Preferences → Privacy & Security

**Low detection accuracy**
- Ensure good lighting conditions
- Face the camera directly
- Try lowering `scaleFactor` to `1.1` for more sensitive detection

**TensorFlow warnings on load**
- Pass `compile=False` to `load_model()` (already set) to suppress optimizer warnings

---

## 🤝 Contributing

Contributions are welcome! Feel free to open issues or submit pull requests for:
- Model improvements or retraining on larger datasets
- Adding emotion confidence score display
- Multi-face tracking support
- GPU acceleration support

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙏 Acknowledgements

- [OpenCV](https://opencv.org/) — computer vision library
- [Keras / TensorFlow](https://keras.io/) — deep learning framework
- Haar Cascade classifier from OpenCV's pre-trained model library
