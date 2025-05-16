# Smart Parking Detection with YOLOv8

**Course:** Computer Vision

Welcome to the **Smart Parking Detection** project powered by **YOLOv8s**! This repository provides an efficient, real-time solution for identifying available parking spaces.

---

## 📌 Project Overview

With rapid urbanization and growing vehicle numbers, finding an empty parking spot has become a daily challenge, leading to wasted time, fuel consumption, and increased traffic congestion.

Our solution leverages computer vision and deep learning to detect free parking slots in real time using a standard camera,
NO need for costly sensor installations.

---
## 🧠 YOLOv8 Architecture

YOLOv8 is the latest one-stage detector from Ultralytics, designed for real-time object detection with modular scalability (variants from nano to extra-large). We selected YOLOv8s (small) to balance accuracy and inference speed:
![yolov8 architecture](https://github.com/user-attachments/assets/70da1e49-f917-467c-887d-36266f3cd813)

Backbone: Modified CSPDarknet53 structure with C2f modules, which concatenate feature maps to improve gradient flow and extract rich hierarchical features.

Neck: PANet-style path aggregation network combining multi-scale features for robust detection of objects at varying sizes.

Head: Anchor-free detection head with direct class and bounding-box predictions, removing the need for preset anchors and improving convergence. 

---

##  🎨 Data Augmentation

To ensure robustness under diverse conditions, we applied extensive augmentations via Roboflow’s pipeline on our 1,200+ image dataset:

Resizing & Normalization: Standardized to 640×640 pixels and applied pixel-value normalization.

Photometric Jitter: Random brightness and contrast adjustments to mimic varied lighting (day, dusk, night).

Geometric Transforms: Horizontal flips and random rotations to improve viewpoint invariance.

Noise Injection: Gaussian noise simulating sensor artifacts and low-light grain.

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

![train_batch1 (1)](https://github.com/user-attachments/assets/04e35af1-fb42-4d6f-8a71-9dfb633e6db6)

![Screenshot 2025-05-16 030050](https://github.com/user-attachments/assets/521873f3-602c-476e-a2df-c84a9a62432e)

![Screenshot 2025-05-16 025940](https://github.com/user-attachments/assets/1d8d1001-87de-491b-85b9-bdd1c88946ef)

---

##  📝 Conclusion

This project demonstrates the effectiveness of a vision-based approach to parking detection using YOLOv8. The system achieved high accuracy with minimal hardware requirements, making it a cost-effective alternative to traditional sensor-based solutions. Our methodology, emphasizing data augmentation and model optimization, ensures robust performance across diverse conditions. As urban areas continue to grow, scalable and intelligent parking solutions like ours will become essential. Future improvements will focus on deployment on edge devices, multi-camera setups, and enhanced analytics.
