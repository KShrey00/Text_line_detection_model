# Text Line Detection in Documents

This repository contains code for detecting and localizing text lines in scanned document images using a CNN-based sliding window approach. The solution is built around the FUNSD dataset and includes preprocessing, model training, inference, and evaluation components.

## Project Overview

Text line detection is a key preprocessing step for document understanding and OCR systems. This project involves:

- Converting scanned documents to binary form
- Training a CNN classifier to detect the presence of text lines in image patches
- Using a sliding window to locate lines across the document
- Drawing bounding boxes on detected lines
- Evaluating the model using precision, recall, and F1-score with IoU-based matching

## Dataset

The project uses the [FUNSD](https://guillaumejaume.github.io/FUNSD/) dataset, which contains scanned document images and their annotations in JSON format.

Directory structure after unzipping:
```bash
/training_data/
├── images/
└── annotations/

/testing_data/
├── images/
└── annotations/
```

Each annotation file includes word-level bounding boxes, which are grouped and used to create ground truth text line regions.

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/text-line-detector.git
   cd text-line-detector
   ```
2. Install the required packages:
```bash
   pip install -r requirements.txt
```
3.  Download and unzip the FUNSD dataset into the data/ directory.
4.  Run the Colab notebook or your own training pipeline to train the model.
   
## Evaluation

Model predictions are evaluated against ground truth using IoU matching. The following metrics are computed:

    Precision: Ratio of correctly predicted line boxes to total predicted boxes

    Recall: Ratio of correctly predicted line boxes to total ground truth boxes

    F1 Score: Harmonic mean of precision and recall 
## Notes

    The model is currently designed for binary classification (text line / not a line).

    The bounding boxes are generated using a sliding window approach and are filtered by a prediction threshold.

    Image preprocessing includes grayscale conversion and Otsu binarization.

  ### Author
  Shreya Kumari
