# 🚗 Vehicle Detection, Tracking, and Counting System

This project implements a complete pipeline for real-time vehicle detection, tracking, and counting from traffic footage using deep learning and object tracking algorithms. Two object detectors — **Faster R-CNN** and **YOLOv8** — are trained and evaluated, with tracking handled by **ByteTrack**. The final system supports both **video file** and **webcam input** and provides optional **traffic density estimation**.

---

## Dataset & Model Access

- **Dataset and Trained Faster R-CNN Model**:  
  🔗 [Google Drive Link](https://drive.google.com/drive/folders/1HInWKaS5MQC4Wj8It91CM_pW8T58vQgs?usp=sharing)

---

## Project Tasks & Pipeline

### Dataset Exploration and Image Preprocessing
- Inspected dataset folder structure, annotation format, and class definitions.
- Applied resizing and normalization to prepare images for training.

### Object Detection Models
- **Faster R-CNN**: Trained using pretrained ResNet-50 backbone on custom traffic dataset.
- **YOLOv8**: Trained using Ultralytics' latest YOLO release with fine-tuning on vehicle classes.

### Multi-Object Tracking
- Integrated **ByteTrack** to maintain unique identities across frames.
- Enabled object-level tracking and ID persistence for accurate counting.

### Evaluation Metrics
- **Detection**:
  - `Precision`, `Recall`, `IoU`, `mAP@0.5`, `mAP@0.5:0.95`

### Training & Optimization
- Models trained for **at least 50 epochs**.
- Early stopping and validation loss monitoring used.
- Regularization strategies and augmentations applied to mitigate overfitting.

### Traffic Density Estimation
- Simple rule-based classification (based on object count threshold) used to label density as `Low`, `Medium`, or `High`.

---

## Tech Stack

- Python, OpenCV
- PyTorch (for Faster R-CNN)
- Ultralytics YOLOv8 (for YOLO detection)
- ByteTrack
- NumPy, Pandas, Matplotlib
- Google Colab / Jupyter Notebook / Kaggle

---

## Example Output

- Bounding boxes with class + object ID
- Vehicle count per frame
- Optional density label: **Low / Medium / High**
- Metrics logged: detection accuracy, tracking quality

---

## How to Run

1. Clone this repo and install dependencies.
2. Download dataset and model from the [Google Drive Link](https://drive.google.com/drive/folders/1HInWKaS5MQC4Wj8It91CM_pW8T58vQgs?usp=sharing).
3. Run `detect_and_track.py` to perform real-time inference.
4. (Optional) Use `evaluate_metrics.py` for offline metric evaluation.

---

## Author

Developed as a group of students as part of a computer vision project focused on traffic analysis.

---

## License

This project is for educational and research use only.
