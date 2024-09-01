# Real Time Video Surveillance and Triggering System

There is a critical need for an automated surveillance solution that can continuously and accurately monitor environments for signs of emergencies, providing real-time alerts to facilitate rapid intervention. Traditional systems relying on human operators are often slow and prone to errors, which can result in severe consequences, including loss of life and extensive property damage. Our project aims to develop a real-time emergency surveillance system that leverages computer vision to detect and respond to critical situations such as fires, violence, and medical emergencies.

<p align="center">
  <img src="artifacts/Violence.png" alt="Violence Detection" width="400"/>
  <img src="artifacts/Telegram_bot.jpg" alt="Telegram Bot" width="200"/>
</p>

## Project Demonstration

[Watch the Demo](https://drive.google.com/file/d/1YtPSY-Q1Xp_LdIYvHNcUdkq8IL7Nck73/view?usp=drive_link)

## Dataset

[Kaggle: Real Life Violence Situations Dataset](https://www.kaggle.com/datasets/mohamedmustafa/real-life-violence-situations-dataset)

# Technical Aspects

## Human Fall Detection

### Methodology

<p align="center">
  <img src="artifacts/mediapipe_opencv.png" alt="Human Fall Detection" width="500"/>
</p>

- Check the distance between foot C.G. and body C.G.
- If the distance exceeds 90 pixels (tall * 0.75), it indicates a fall.
- The system counts how many times a fall has occurred and detects when the person gets back up.

## Violence Detection

### Methodology

<p align="center">
  <img src="artifacts/violence_detection.png" alt="Violence Detection" width="500"/>
</p>

- The dataset contains 1000 videos each of violent and non-violent categories.
- A model was trained using MobileNetV2 architecture.
- Real-time video footage is processed, and the output is obtained as image frames.
- The model provides real-time classification capabilities on devices with computing constraints, such as smartphones.

## Fire Detection

### Methodology

<p align="center">
  <img src="artifacts/fire.jpg" alt="Fire Detection" width="500"/>
</p>

- The `cv2.CascadeClassifier` is used to load a pre-trained fire detection model.
- The model processes video frames, extracting features like edges and textures, comparing them against the pre-trained model.
- Real-time detection triggers an alarm if fire patterns are detected.

### Telegram Bot and Alert System

At the end, we integrated a real-time alert system using a Telegram bot and an alarm. The Telegram bot, built with the telebot library, sends instant alerts with captured images to a specified chat when the models detect instances of fire outbreak, violence and fall (e.g. a person falling due to medical emergency). 

---

## Steps to Run the Project

1. **Clone the repository:**

   ```bash
   git clone https://github.com/Hirak010/Real-time-surveillance-detection.git
   ```

2. **Create an environment & activate:**

   ```bash
   conda create -n env python=3.11 -y
   conda activate ./env
   ```

3. **Install the requirements:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Run the webcam app:**

   ```bash
   python alert.py
   ```

---
## Authors

```bash
Authors: Ashutosh Kumar, Hirakjyoti Medhi, Roshan Jha and Biswajit Bera
Email: kumarashutosh9694@gmail.com
```

*This project was developed as part of a group effort while participating in a Computer Vision Hackathon organized by SarasAI Institute. We won the Hackathon, securing the **First Position!*** 🎉
