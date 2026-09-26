**Cartoon Emotion Recognition: An Integrated DNN Approach**

**✨ Project Overview:**

This repository contains the implementation of a novel Integrated Deep Neural Network (DNN) approach for recognizing emotions in cartoon characters. This project successfully addresses the challenge of recognizing emotions in animated characters, specifically 'Tom' & 'Jerry', achieving a high accuracy of 96.87% on a custom-collected dataset.

**🧠 Integrated DNN Architecture (Two-Stage Pipeline):**

The project utilizes a two-stage deep learning pipeline, combining a detection model with a classification model for robust and focused analysis:

**Stage 1: Face Detection (YOLOv3):**

**Goal:** To accurately localize and crop the face of the target character (Tom or Jerry) within any video frame or image.

**Stage 2: Emotion Classification (MobileNetV2):**

**Goal:** The cropped facial region is fed into a fine-tuned MobileNetV2 model to classify the emotion.

This integrated approach ensures the emotion classifier focuses only on the most relevant features (the face), avoiding noise and improving recognition performance.

**🚨 Note for Non-Colab Users:**

This project was developed primarily in a Google Colab environment. If you are running this project locally (e.g., on Windows/Linux or a local Jupyter environment), you might need to make minor adjustments, particularly regarding:

1. **File Paths:** Colab mounts Google Drive (e.g., /content/drive/MyDrive/). You must update all dataset loading and saving paths in the notebook/scripts to your local directory structure.
2. **Folder Structure:** Ensure your local folder structure for the downloaded dataset matches the paths referenced in the code.
3. **Initial Setup:** You may need to manually install CUDA drivers if you plan to use a GPU, as Colab handles this automatically.

**💾 Dataset & Model Files:**

**Image Dataset Download (Google Drive)**
To access the raw image dataset required for training and replication visit the drive link provided below.

**Image Dataset Folder:** https://drive.google.com/drive/folders/1gAEZwl46yl7pTAdGuSOR07hXaI1bxZiz?usp=sharing

**⚙️ Prerequisites:**

1. Python 3.8+
2. pip (Python package installer)

**💻 Installation:**

1. Clone the repository
2. Install the required libraries

The requirements.txt file lists libraries like torch, torchvision, ultralytics, opencv-python, and others.

**🚀 Usage:**
1. **Model Setup:** Since the trained weights are already on GitHub, you can skip manual model setup. Ensure your prediction script correctly loads the model files from their location within this repository.
2. **Run Prediction on Video/Image:** Use the main prediction script (e.g., predict.py) to run the two-stage pipeline on your test files

The script will process the input by performing the following steps sequentially:
1. Load the input frame.
2. Use the YOLOv3 model to detect faces.
3. Crop the detected face based on the bounding box.
4. Use the MobileNetV2 model to classify the emotion (Happy, Sad, Angry, Surprised, Unknown).
5. Draw bounding boxes and the predicted emotion label on the output frame.

**🎯 Results:**

The integrated DNN approach demonstrated high efficiency in recognizing emotions in cartoons, achieving a benchmark accuracy of 96.87% on the validation set.

**👥 Contributors:**
1. Muhammad Souman - GitHub Profile:  https://github.com/muhammadsouman7
2. Alishba Nadeem - GitHub Profile:  https://github.com/Alishba-Nadeem1
3. Shaaf Khan - GitHub Profile:  https://github.com/shaafkhan10k
4. Ilsa Javed
5. Anas Waqas
6. Raja Amman Shakir

**📄 Reference:**

The system architecture and dataset were developed based on the research presented in the paper:
1. Jain, N., Gupta, V., Shubham, S. et al. Understanding cartoon emotion using integrated deep neural network on large dataset. Neural Comput & Applic 34, 21481–21501 (2022).
