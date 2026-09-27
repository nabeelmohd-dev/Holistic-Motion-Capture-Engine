# 🕺 Holistic Motion Capture & Keypoint Engine
> **1st Prize Winner @ SRM 48-Hour Hackathon**
> A high-performance PyQt5 application for real-time skeletal, facial, and hand landmark extraction using MediaPipe.

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![MediaPipe](https://img.shields.io/badge/AI-MediaPipe_Holistic-00C853.svg)](https://mediapipe.dev/)
[![PyQt5](https://img.shields.io/badge/GUI-PyQt5-90caf9.svg)](https://www.riverbankcomputing.com/software/pyqt/)
[![Award](https://img.shields.io/badge/Award-1st_Place_Hackathon-gold.svg)]()

## 📌 Project Overview

This system was developed to solve the challenge of high-latency motion capture. By integrating **Google MediaPipe's Holistic model** with a custom **PyQt5** dashboard, the application provides a seamless way to track, visualize, and record 540+ individual keypoints across the human body, face, and hands in real-time.

## ✨ Key Features

* **Real-time Holistic Tracking:** Unified processing of pose, face mesh, and hand landmarks.
* **Selective Part View:** Toggle between "Whole Body", "Face", "Hands", or "Legs" to control which landmarks are drawn and recorded.
* **Data Serialization:** Record motion sequences and export them as structured **JSON** for use in 3D animation pipelines or ML model training.
* **Simple GUI:** Built with PyQt5, featuring a live camera feed, part-selection dropdown, and start/stop/save recording controls.

## 🛠️ Tech Stack

* **Core Logic:** Python, OpenCV, MediaPipe
* **Desktop Framework:** PyQt5
* **Data Handling:** JSON
* **Logging:** Python's built-in `logging` module for error reporting

## 🚀 Getting Started

### Prerequisites

* Python 3.9 or higher
* A webcam

### Installation

1. **Clone the repo:**

   ```bash
   git clone https://github.com/nabeelmohd-dev/Holistic-Motion-Capture-Engine.git
   cd Skeletal-Tracking
   ```

2. **Install dependencies:**

   It is recommended to use a virtual environment.

   ```bash
   python -m venv venv
   source venv/bin/activate      # On Windows: venv\Scripts\activate
   pip install opencv-python mediapipe PyQt5 numpy
   ```

### Running the App

```bash
python main.py
```

This opens the application window and connects to your default webcam (device index 0). From there:

1. Choose a tracking mode from the dropdown: **Whole Body**, **Face**, **Hands**, or **Legs**.
2. Click **Start Recording** to begin capturing keypoints for the selected mode.
3. Click **Stop Recording** when finished.
4. Click **Save Key Points** to export the recorded sequence as a JSON file.

## 📁 Output Format

Saved JSON files contain a list of frames, each with normalized `(x, y, z)` coordinates for the landmark groups relevant to the selected tracking mode (`pose_landmarks`, `face_landmarks`, `left_hand_landmarks`, `right_hand_landmarks`).
