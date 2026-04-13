# Valorant Player Tracking with YOLO26s & ByteTrack

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![YOLO](https://img.shields.io/badge/Model-YOLO26s-orange.svg)
![Computer Vision](https://img.shields.io/badge/Field-Computer_Vision-green.svg)

## 📌 Introduction
This project implements object detection and tracking for characters in the Valorant game based on the **YOLO26s** architecture and the **ByteTrack** algorithm. This is part of a development roadmap to becoming an AI Engineer, focusing on high-speed video processing and optimal accuracy in complex gaming environments.

## 📺 Demo
*(Insert video link or result GIF here)*
> [Watch the high-quality demo video here](https://youtu.be/L_bL-CjXj04)

## 🚀 Key Features
* **Object Detection:** Accurately recognizes Players (Enemy/Ally) with high confidence scores.
* **Real-time Tracking:** Utilizes ByteTrack to maintain character IDs even when they are partially occluded.
* **YouTube Support:** Supports direct inference from YouTube streams without downloading the video.
* **MacOS Optimized:** Leverages GPU (MPS) on Apple Silicon chips to accelerate processing speed.

## 📊 Training Results (Metrics)
The model was trained on a specialized Valorant dataset with impressive metrics:
* **Precision:** 0.961 (96.1%)
* **Recall:** 0.941 (94.1%)
* **mAP@50:** *(Fill in your mAP metric here)*

## 🛠 Installation & Usage

### 1. System Requirements
* Python 3.9+
* macOS (optimized for M1/M2/M3 chips) or Windows/Linux.

### 2. Install Dependencies
```bash
pip install ultralytics torch torchvision opencv-python
from ultralytics import YOLO

# Load the trained model
model = YOLO('weights/best_valorant.pt')

# Run tracking on a YouTube stream or local video
results = model.track(
    source='your_youtube_link_or_video_path_here', 
    show=True, 
    stream=True,
    tracker='bytetrack.yaml',
    device='mps' # Remove or change to 'cpu'/'cuda' if not on Mac
)

for r in results:
    pass