# Cartoon Emotion Recognition: An Integrated DNN Approach

## ✨ Overview

This repository implements a two-stage Deep Neural Network (DNN) pipeline for recognizing emotions in cartoon characters. The system targets **Tom & Jerry** and achieves **96.87% accuracy** on a custom-collected dataset.

## 🧠 Architecture

The pipeline combines a detection model with a classification model so the classifier only ever sees the relevant facial region, avoiding background noise and improving accuracy.

| Stage | Model | Goal |
|---|---|---|
| 1. Face Detection | YOLOv3 | Localize and crop the face of the target character (Tom or Jerry) in any frame or image |
| 2. Emotion Classification | MobileNetV2 (fine-tuned) | Classify the emotion of the cropped face |

## 🚨 Running Outside Google Colab

This project was developed primarily in Google Colab. If running locally (Windows/Linux/local Jupyter), adjust the following:

1. **File paths** — Colab mounts Google Drive at paths like `/content/drive/MyDrive/`. Update all dataset load/save paths in the notebook/scripts to match your local directory structure.
2. **Folder structure** — Ensure your local copy of the downloaded dataset matches the folder structure the code expects.
3. **GPU setup** — Colab provisions CUDA automatically; locally you'll need to install CUDA drivers yourself if using a GPU.

## 💾 Dataset

The raw image dataset used for training and replication is available here:

- **Image Dataset Folder:** https://drive.google.com/drive/folders/1gAEZwl46yl7pTAdGuSOR07hXaI1bxZiz?usp=sharing

## ⚙️ Prerequisites

- Python 3.8+
- pip

## 💻 Installation

```bash
git clone <this-repository-url>
cd <repository-folder>
pip install -r requirements.txt
```

`requirements.txt` includes `torch`, `torchvision`, `ultralytics`, `opencv-python`, and other supporting libraries.

## 🚀 Usage

**1. Model setup**
Trained weights are already included in this repository — no manual download needed. Just make sure your prediction script points to the correct model file paths within the repo.

**2. Run prediction**

```bash
python predict.py --input <path-to-video-or-image>
```

The script runs the full two-stage pipeline:

1. Load the input frame.
2. Detect faces using YOLOv3.
3. Crop the detected face using the bounding box.
4. Classify the emotion using MobileNetV2 (`Happy`, `Sad`, `Angry`, `Surprised`, `Unknown`).
5. Draw the bounding box and predicted emotion label on the output frame.

## 🎯 Results

The integrated DNN approach achieved **96.87% accuracy** on the validation set.

## 👥 Contributors

- **Muhammad Souman** — [GitHub](https://github.com/muhammadsouman7)
- **Shaaf Khan** — [GitHub](https://github.com/shaafkhan10k)

## 📄 Reference

This work builds on the architecture and methodology described in:

> Jain, N., Gupta, V., Shubham, S. et al. *Understanding cartoon emotion using integrated deep neural network on large dataset.* Neural Comput & Applic 34, 21481–21501 (2022).
