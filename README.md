# ASL Alphabet Classification

A deep learning project for classifying American Sign Language (ASL) alphabet hand signs, exploring CNN baselines, transfer learning, and hand landmark detection.

---

## Overview

This project tackles ASL alphabet classification using two Kaggle datasets:

- [ASL Alphabet](https://www.kaggle.com/datasets/grassknoted/asl-alphabet) — the primary dataset
- [Synthetic ASL Alphabet](https://www.kaggle.com/datasets/lexset/synthetic-asl-alphabet) — added to introduce more background variety, since the first dataset had relatively uniform backgrounds

Four models are implemented and evaluated:

| Model | Type |
|---|---|
| CNN | Baseline |
| MobileNetV2 | Transfer Learning |
| EfficientNetB3 | Transfer Learning |
| ResNet50 | Transfer Learning |

The project also includes an exploratory section using **Google's MediaPipe** for hand landmark detection as an alternative approach to the classification problem.

---

## Project Structure

The project lives in a single notebook, organised into the following sections:

```
├── asl_alphabet_classification.ipynb
│   ├── Introduction
│   ├── Data Analysis and Preprocessing
│   ├── CNN Model
│   │   └── Evaluation
│   ├── Transfer Learning & Fine Tuning
│   │   ├── MobileNetV2
│   │   ├── EfficientNetB3
│   │   └── ResNet50
│   ├── Results Analysis - CNN & Transfer Learning
│   ├── Exploratory Section - MediaPipe
│   └── Conclusion & Summary
├── README.md
└── requirements.txt
```

---

## Models & Results

Model results are analysed in depth in the **Result Analysis — CNN & Transfer Learning** section of the notebook. In brief:

- The **plain CNN** serves as a baseline to compare against transfer learning approaches.
- **MobileNetV2**, **EfficientNetB3**, and **ResNet50** were each fine-tuned on the dataset and compared across accuracy, training time, and generalisation.

---

## Key Technical Notes

**Dataset pipeline:** `ImageDataGenerator` is not compatible with Keras 3.0 and resulted in very slow training. Switching to a **TensorFlow dataset pipeline** resolved this — a frustrating but valuable lesson worth noting if you run into the same issue.

**Fine-tuning:** Transfer learning and fine-tuning were applied to all three pre-trained models. The process and results are documented throughout the notebook.

---

## Limitations

This is a learning project. While the models achieved strong results, they are not production-ready:

- Training images are relatively clean and high quality — models would likely struggle with lower quality or noisier real-world inputs.
- The synthetic dataset was added to introduce background variety, but more diverse data and additional augmentation would further improve robustness.

---

## What I'd Do Differently

A few improvements planned for future projects:

- Report model size as part of the evaluation metrics
- Surface misclassified samples for error analysis
- Consolidate transfer learning and fine-tuning logic into reusable functions

---

## Inspirations

The following Kaggle notebooks were a source of ideas and reference throughout this project:

- [Yolo11n](https://www.kaggle.com/code/nishida003/yolo11n) — nishida003
- [MobileNetV2](https://www.kaggle.com/code/letuankietk18hl/mobilenetv2) — letuankietk18hl
- [ASL Detection - 99% Accuracy](https://www.kaggle.com/code/sarthakparajuli/asl-detection-99-accuracy) — sarthakparajuli
- [ASL Gesture Recognition with ResNet-34](https://www.kaggle.com/code/alinamironova/asl-gesture-recognition-with-resnet-34) — alinamironova
- [ASL Alphabet Detection](https://www.kaggle.com/code/mahmoudehab6677/asl-alphabet-detection) — mahmoudehab6677
- [SignSense](https://www.kaggle.com/code/hvvsathwik/signsense) — hvvsathwik

---

## Datasets

- [ASL Alphabet — Grassknoted](https://www.kaggle.com/datasets/grassknoted/asl-alphabet)
- [Synthetic ASL Alphabet — Lexset](https://www.kaggle.com/datasets/lexset/synthetic-asl-alphabet)

---

## Requirements

```bash
pip install -r requirements.txt
```

Main dependencies: `tensorflow`, `keras`, `mediapipe`, `numpy`, `matplotlib`, `scikit-learn`
