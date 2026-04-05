🌊 Flood Detection using Geospatial Deep Learning (AISEHack)

📌 Project Overview

This project focuses on multi-class flood segmentation using multi-modal satellite imagery. The objective is to classify each pixel into:

- 0 → No Flood
- 1 → Flood
- 2 → Water Body

The solution leverages deep learning to improve flood detection accuracy for real-world disaster response.


📊 Dataset Information

- Input: 512 × 512 satellite image patches
- Channels:
  - SAR: HH, HV
  - Optical: Green, Red, NIR, SWIR
- Labels:
  - 0: No Flood
  - 1: Flood
  - 2: Water Body
- Data split:
  - Train / Validation / Test (provided)

🧠 Model Architecture

- Model: U-Net
- Encoder: ResNet34 (pretrained on ImageNet)
- Input: 6-channel multi-modal data
- Output: 3-class segmentation mask


⚙️ Training Strategy

- Loss Function:
  - Class-weighted CrossEntropy
  - Dice-based refinement (for flood class)
- Optimization:
  - AdamW optimizer
  - Learning rate scheduling
  - Gradient clipping
- Training:
  - Two-stage training (base + fine-tuning)
- Data Processing:
  - Per-channel normalization

📊 Results

- Flood IoU: ~0.20
- Mean IoU (mIoU): ~0.36
- Kaggle Score: 0.1722

🔧 Inference Strategy

- Threshold-based flood detection
- Water-body suppression to reduce misclassification
- RLE encoding for submission format


🔗 Important Links

📓 Kaggle Notebook

👉 (https://www.kaggle.com/code/msohniarunima/final)


📦 Model Checkpoint

👉 ((https://www.kaggle.com/models/msohniarunima/unet-best-model-anrf/PyTorch/unet-best-model-v1))

📄 Report (Executive Summary)

👉 https://drive.google.com/file/d/1aU3x4jU_M9PROqVMbw1s1Z9MTYYgIQ2U/view?usp=sharing


📁 Repository Structure

flood-detection-aisehack/
│
├── README.md
├── LICENSE
├── requirements.txt
├── final.ipynb
├── best_model_link.txt   
│── submission.csv
├── Appendix
│   


🧾 Notes

- Fully reproducible pipeline within a single notebook
- Only best-performing model is included
- Designed for efficient and scalable flood detection

✅ Final Submission

This repository corresponds to the best-performing solution achieving a leaderboard score of 0.1722, with optimized training and inference strategies.
