# Smart Parking Detection with YOLOv8

**Course:** Computer Vision

Welcome to the **Smart Parking Detection** project powered by **YOLOv8s**! This repository provides an efficient, real-time solution for identifying available parking spaces.

---

## 📌 Project Overview

With rapid urbanization and growing vehicle numbers, finding an empty parking spot has become a daily challenge, leading to wasted time, fuel consumption, and increased traffic congestion.

Our solution leverages computer vision and deep learning to detect free parking slots in real time using a standard camera—eliminating the need for costly sensor installations.

---

## ✨ Key Features

- **High Accuracy**: Achieves 97.7% mAP@0.5 for precise parking slot detection.
- **Fast Inference**: Processes live video streams at 35–38 FPS for seamless real-time performance.
- **Cost-Effective**: Utilizes only a standard camera and lightweight YOLOv8s model.
- **Scalable**: Easily deployable on edge devices like NVIDIA Jetson Nano or Google Coral TPU.

---

## 🛠️ Requirements

- Python ≥ 3.8
- Ultralytics YOLOv8 library
- OpenCV
- NVIDIA GPU (e.g., Tesla T4) for training and inference
- Labeled parking lot dataset (e.g., Roboflow-curated)

---

## 🚀 Installation & Usage

1. **Clone the repository**
   ```bash
   git clone https://github.com/username/smart-parking-yolov8.git
   cd smart-parking-yolov8
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate    # Linux/macOS
   venv\Scripts\activate     # Windows
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the detector**
   ```bash
   python detect.py --weights yolov8s.pt --source data/parking_lot_video.mp4
   ```

---

## 🧠 Methodology

1. **Data Collection**: Over 1,200 images of parking lots under various lighting (day, dusk, night) and weather (rain, fog) conditions.
2. **Preprocessing**: Resize to 640×640, adjust brightness/contrast, apply rotations, flips, and synthetic noise.
3. **Training**: Transfer learning from COCO-pretrained weights; 10 epochs using SGD with learning rate 0.01 and step decay every 5 epochs.
4. **Evaluation**: Metrics include mAP@0.5, mAP@0.5:0.95, Precision, Recall, F1 Score, and inference speed (FPS).

---

## 📊 Results

| Metric              | Value    |
|---------------------|----------|
| mAP@0.5             | 97.7%    |
| mAP@0.5:0.95        | 85.3%    |
| Precision           | 94.7%    |
| Recall              | 94.3%    |
| F1 Score            | 90.6%    |
| Inference Speed     | 35–38 FPS |

---

## 🔭 Future Work

- **Edge Deployment**: Optimize and deploy on devices like Jetson Nano and Coral TPU.
- **Multi-Camera Integration**: Fuse feeds to improve occlusion robustness.
- **Temporal Tracking**: Add object tracking to stabilize detections and reduce flicker.
- **Dashboard & Analytics**: Build a web interface for live occupancy stats, heatmaps, and pricing management.

---

## 📚 References

1. Li et al., “Vision-based Parking Slot Detection: A Survey,” *IEEE Access*, 2020.
2. Redmon & Farhadi, “YOLOv3: An Incremental Improvement,” arXiv, 2018.
3. Ultralytics, “YOLOv8: State-of-the-Art Real-Time Object Detection,” 2023.

---

> Developed under the supervision of Dr. Mohammed Imran.

---

Thank you for using **Smart Parking Detection!** 🚗🔍
