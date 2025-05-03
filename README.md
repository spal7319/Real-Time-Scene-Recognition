# Real-Time Scene Recognition and Description Generation for Visually Impaired

---

## 📑 Abstract

This project develops a real-time system to assist visually impaired individuals by interpreting visual scenes and generating contextual audio descriptions. It integrates **ResNet-50** for feature extraction, **LSTM** for caption generation, **YOLOv5** for object detection, and **OpenCV** for video processing. The system achieves a BLEU-1 score of **0.2069**, scene classification accuracy of **78–82%**

---

## 🧩 Introduction

### Problem Statement

Visually impaired individuals struggle to interpret visual environments. This system provides real-time audio descriptions of scenes using AI, enabling independent navigation.

### Key Features

- **Scene Recognition**: Classifies indoor environments (e.g., kitchen, corridor).
- **Object Detection**: Identifies objects using YOLOv5.
- **Caption Generation**: Converts visual data to natural language.
- **Real-Time Audio Feedback**: Integrates TTS for accessibility.

### Hardware Setup

- **OAK-D S2 Camera**: Depth-aware vision.
- **Raspberry Pi 5**: On-device processing.
- **Power Bank & Earphones**: Portable audio output.

---

## 🛠 Methodology

### Architecture

1. **Scene Recognition**: ResNet-18 trained on MIT Indoor-67.
2. **Object Detection**: YOLOv5 for real-time localization.
3. **Caption Generation**: ResNet-50 + LSTM with attention.
4. **Integration**: OpenCV for frame processing and TTS for audio.

### Algorithms

- **ResNet-50**: Extracts 2048-D image features.
- **LSTM**: Generates captions sequentially.
- **YOLOv5**: Detects objects with 80-class COCO labels.

---

## ⚙️ Implementation

### Data Preprocessing

- **Datasets**:
  - **Flickr30k**: 31k images + 5 captions each.
  - **MIT Indoor-67**: 15k indoor scene images.
- **Steps**:
  - Remove punctuation and lowercase text.
  - Tokenize captions into numerical sequences.

### Training

- **Image Captioning**: 20 epochs on Flickr30k (80:20 train-val split).
  - Training Loss: 1.23 → 0.45
  - Validation Loss: Plateaued at 1.85
- **Scene Recognition**: ResNet-18 fine-tuned for 25 epochs.
  - Accuracy: 78–82% on MIT Indoor-67.

---

## 📊 Results

### Metrics

| Metric          | Value  |
| --------------- | ------ |
| BLEU-1          | 0.2069 |
| Scene Accuracy  | 78–82% |
| Inference Speed | 18 FPS |
