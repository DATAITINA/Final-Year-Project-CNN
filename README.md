# Sign Language Recognition with CNNs

**Final Year Project — Applied Mathematics in Sign Language Recognition using Convolutional Neural Networks**

Real-time sign language gesture classification system developed as part of a B.Sc. Industrial Mathematics degree. The project applies deep learning and computer vision to classify hand gestures and produce speech output, with the goal of improving accessibility.

---

### Problem & Why It Matters

Communication barriers between deaf/hard-of-hearing individuals and the hearing population remain significant. Automated, real-time sign language recognition can reduce friction in everyday interactions. This project explores a practical CNN-based pipeline constrained by real-time performance and limited gesture classes.

---

### Architecture / Pipeline

```text
Webcam Feed
     │
     ▼
┌────────────────────┐
│ MediaPipe          │  ← hand tracking & landmarks
│ Hand Detection     │
└─────────┬──────────┘
          │
          ▼
┌────────────────────┐
│ Image Preprocessing│
└─────────┬──────────┘
          │
          ▼
┌────────────────────┐
│ CNN Classifier     │  ← MobileNetV2 / custom CNN
│ (7 gesture classes)│
└─────────┬──────────┘
          │
          ▼
┌────────────────────┐
│ Speech Output      │  ← gTTS
└────────────────────┘
```

---

### Key Components

- CNN-based image classification
- MobileNetV2 architecture (efficiency for real-time use)
- MediaPipe hand tracking
- Real-time webcam pipeline (OpenCV)
- Speech synthesis (gTTS)
- 7 gesture classes

---

### Tech Stack

| Area              | Technologies                          |
|-------------------|---------------------------------------|
| Deep Learning     | PyTorch / TensorFlow, CNNs, MobileNetV2 |
| Computer Vision   | OpenCV, MediaPipe                     |
| Output            | gTTS                                  |
| Math Foundation   | Applied mathematics coursework        |

---

### Implementation Location

Core experimental notebooks and related work are maintained in the main journey repository:

→ **[Sign_Lang_using_gTTS.ipynb](https://github.com/DATAITINA/my-ai-journey/blob/main/Sign_Lang_using_gTTS.ipynb)**  
→ **[my-ai-journey](https://github.com/DATAITINA/my-ai-journey)**

This repository serves as the academic project record and entry point.

---

### Evaluation & Design Notes

- Focus on real-time feasibility rather than large-scale open-vocabulary recognition.
- MobileNetV2 chosen for speed/accuracy trade-off on modest hardware.
- Limited to 7 gesture classes for controlled evaluation.
- Human-in-the-loop and confidence-aware extensions are natural next steps (see also Dokusure’s confidence pattern).

---

### Limitations & Future Work

- Small number of classes (7)
- Limited public dataset size and diversity
- No production API or deployment packaging in this repo
- Quantitative metrics (accuracy, latency, confusion matrix) should be documented more formally

**Future directions:** expand gesture vocabulary, add confidence thresholds, package as a FastAPI service, and collect more diverse training data.

---

### Status

Academic / research project. Primary implementation artifacts live in `my-ai-journey`.

**Author:** David Itina  
**Background:** B.Sc. Industrial Mathematics, Covenant University
