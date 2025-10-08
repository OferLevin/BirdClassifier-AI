# Bird Species Classifier

## Introduction
This project is an AI tool that classifies images of birds into **two species**:
- Birds of Paradise  
- Banded Broadbill  

The model is trained using **YOLOv8** for image classification.

---
Make Sure Everything Is Sorted into BANDED BROADBILL and BIRD OF PARADISE Folders inside Validate, Train and Test
## Steps to Run the Project

### 1. Install YOLOv8
```bash
pip install ultralytics
```
### 2. Navigate to Jetson Inference Folder
```bash
cd Jetson-inference
```
### 3. Create Project Folder
```bash
mkdir Final-Project
```
### 4. Train the Model
```bash
yolo task=classify mode=train \ model=yolov8n-cls.yaml \ data=/home/nvidia04/jetson-inference/Final-Project/Dataset \ epochs=100 \ batch=16
 ```
### 5. Validate The Model
```bash
yolo task=classify mode=val \
  model=runs/classify/train2/weights/best.pt \
  data=/home/nvidia04/jetson-inference/Final-Project/Dataset
 ```
### 6. Use Model for Predictions
```bash
yolo task=classify mode=predict \
  model=/home/nvidia04/jetson-inference/Final-Project/runs/classify/train2/weights/best.pt \
  source=/home/nvidia04/jetson-inference/Final-Project/Dataset/test
```
### 7. Export The Model
```bash
yolo export \
  model=/home/nvidia04/jetson-inference/Final-Project/runs/classify/train2/weights/best.pt \
  format=onnx
```
