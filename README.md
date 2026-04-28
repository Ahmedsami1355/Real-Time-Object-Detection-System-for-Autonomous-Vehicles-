# Real-Time-Object-Detection-System-for-Autonomous-Vehicles-
# 🚗 Autonomous Vehicle Perception System (YOLOv8)

![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![YOLOv8](https://img.shields.io/badge/YOLO-v8-yellow)
![PyTorch](https://img.shields.io/badge/PyTorch-ee4c2c?logo=pytorch&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green)

## 📌 Project Overview
A comprehensive real-time perception system for autonomous vehicles powered by **YOLOv8**. This model is trained to detect and classify **57 unique classes** crucial for self-driving cars, including vehicles, pedestrians, traffic signs, and traffic lights states.

### 🎯 Key Capabilities:
- **8 Vehicle Types** (Cars, Trucks, Vans, Pedestrians, Cyclists, etc.)
- **43 Traffic Signs** (Speed limits, Stop, Yield, Warnings, etc.)
- **6 Traffic Light States** (Red, Yellow, Green + Left Arrows)
- **Real-Time Inference** optimized for video streams and webcam feeds.

---

## 🎬 Demo & Results
*(Showcase your model's performance here!)*

| Video Inference | Image Detection |
| :---: | :---: |
| ![Video Demo](link_to_your_gif_or_video.gif) | ![Image Demo](link_to_your_screenshot.jpg) |
> **Note:** Replace the placeholders above with actual GIFs or screenshots of your model running on the German driving test video or sample images.

---

## 📊 Dataset Architecture
To achieve robust detection, we merged three distinct and highly-regarded datasets. **Due to the large size of the combined dataset (~30GB), the data is not hosted in this repository.**

1. **KITTI Vision Benchmark Suite:** Used for detecting vehicles and pedestrians.
2. **GTSRB (German Traffic Sign Recognition Benchmark):** Used for learning 43 classes of European traffic signs.
3. **LISA Traffic Light Dataset:** Used for identifying the states of traffic lights.

*Scripts are provided in this repository to automatically clean, convert, and merge these datasets into a unified YOLO format.*

---

## 📁 Repository Structure
The project is modularized into clear, sequential scripts to ensure **100% reproducibility**:

```text
├── 01_lisa_to_yolo.py       # Converts LISA annotations (CSV) to YOLO format
├── 02_merge_datasets.py     # Unifies KITTI, GTSRB, and LISA with correct Class IDs
├── 03_train_model.py        # YOLOv8s training configuration and execution
├── 04_test_images.py        # Samples images and runs batched predictions
├── 05_test_video.py         # Runs real-time inference on video files/webcam
├── weights/
│   └── best.pt              # The final trained model weights (Included)
├── requirements.txt         # Project dependencies
└── README.md
🚀 Getting Started (Reproducibility)
1. Clone the Repository
Bash
git clone [https://github.com/YourUsername/comercio.git](https://github.com/YourUsername/comercio.git)
cd comercio
2. Install Dependencies
Bash
pip install -r requirements.txt
(Dependencies include: ultralytics, torch, opencv-python, pandas, scikit-learn)

3. Data Preparation (Optional)
If you wish to train the model yourself:

Download the KITTI, GTSRB, and LISA datasets.

Place them in the root directory.

Run the data preparation scripts:

Bash
python 01_lisa_to_yolo.py
python 02_merge_datasets.py
4. Run Inference (Testing)
You can immediately test the system using our pre-trained best.pt model.

For testing on images:

Bash
python 04_test_images.py
For testing on a video file:

Bash
python 05_test_video.py
📈 Model Performance
Base Model: YOLOv8s (Small)

Epochs: 50

Batch Size: 32

Training Hardware: RTX 4060 (8GB VRAM)

mAP50: [Insert your mAP score here, e.g., 0.85]

Inference Speed: [Insert speed, e.g., 60 FPS on GPU]