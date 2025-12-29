## ***Instant Sign Language Recognition using MediaPipe & MLP***
📌 **Project Overview**

This project focuses on building an AI-based sign language recognition system using MediaPipe Hands and a Multi-Layer Perceptron (MLP) model. The system captures hand gestures through a webcam, extracts hand landmark features, and classifies sign language characters in real time.

The long-term goal of this project is to integrate the recognition system into a web-based video communication tool with real-time multilingual text translation using Google Cloud Translation API to enable accessible video calls for deaf and hard-of-hearing users.


✅ **Current Project Status**

- `Real-time hand gesture capture using webcam`
- `Hand landmark extraction using MediaPipe Hands`
- `Dataset preparation using MediaPipe keypoints`
- `Training and evaluation of MLP-based sign recognition model`
- `Comparison with MobileNetV2 approach`



⏳ **Pending Work**

- `Integration of Google Cloud Translation API`
- `Deployment as a web-based video communication app`
- `Live caption overlay on video stream`
- `Multi-user video call support`
```
📂 Project Structure
📂 Sign Language Recognition System/
│── 📂 data/
│   │── asl_mediapipe_keypoints_dataset.csv   # Landmark-based dataset
│
│── 📂 models/
│   │── asl_mediapipe_mlp_model.h5             # Trained MLP model
│   │── sign_language_model_MobileNetV2.h5     # Experimental CNN model
│
│── 📂 notebooks/
│   │── Mediapipe_Training.ipynb               # MLP training & evaluation
│   │── MobileNetV2_Training.ipynb             # CNN training
│   │── Combined_Architecture.ipynb            # Model comparison
│
│── requirements.txt                           # Project dependencies
│── README.md
```


🏗️ **Dataset**

- The project uses an ASL Sign Language dataset sourced from Kaggle.
- Two approaches were explored:
- Image-based dataset for MobileNetV2
- Landmark-based dataset extracted using MediaPipe Hands for MLP
- Landmark-based data significantly improved real-time performance and accuracy.



🧠 **Model Approaches**

🔹 *MediaPipe Hands + MLP (Primary Approach)*

- MediaPipe Hands extracts 21 hand landmarks per frame
- Landmark coordinates are flattened into feature vectors
- A lightweight MLP model classifies sign language characters
- Best suited for real-time gesture recognition
- Why this approach?
- Low latency
- High accuracy for live input
- Works efficiently without GPU

🔹 *MobileNetV2 (Experimental)*

- Trained on raw gesture images
- Performed well on static images
- Struggled in real-time webcam conditions
- Retained only for comparison and experimentation



## 🚀 Running the Sign Language Recognition System

### **1️⃣ Install Dependencies**

```sh
pip install -r requirements.txt
```

### **2️⃣ Running Model Evaluations**

To test the output of individual models, run the **last cell** in:

- `Mediapipe_Training.ipynb` for MLP model evaluation.
- `MobileNetV2_Training.ipynb` for MobileNetV2 evaluation.

### **3️⃣ Running the Combined Architecture**

To see the working of **both MobileNetV2 and MediaPipe integrated**, run:

```sh
jupyter notebook Combined_Architecture.ipynb
```

### **4️⃣ Controls & Commands**

- **Normal Signs** → Letters are appended to the sentence.
- **SPACE Sign** → Adds a space.
- **DELETE Sign** → Removes the last character.
- **NOTHING** → No input detected.



⚠️ **Current Limitations**

- Recognizes a limited set of characters/signs
- No sentence-level language understanding yet
- Translation and video call features are not yet integrated
- Works only as a local prototype, not a deployed web app



🔜 **Planned Enhancements**

- Integrate Google Cloud Translation API for multilingual output
- Convert recognized text into live captions
- Deploy the system as a web-based video communication tool
- Add WebRTC for real-time video calls
- Improve gesture vocabulary and sentence formation
- UI enhancement with real-time caption overlay



🛠️ **Technologies Used**

- `MediaPipe Hands` – Real-time hand landmark detection
- `TensorFlow / Keras` – MLP model training
- `OpenCV` – Webcam video capture
- `Python` – Core development
- `Google Cloud Translation API` (Planned)
- `Web Technologies` (React, WebRTC) (Planned)



🎯 **Project Vision**

To build an accessible, AI-powered video communication platform that converts sign language into real-time multilingual text, enabling inclusive communication without the need for a human interpreter.



🤝 **Acknowledgments**

- MediaPipe by Google for hand tracking
- Kaggle ASL datasets
- Open-source research in sign language recognition
