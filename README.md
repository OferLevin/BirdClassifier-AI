My Project is an AI tool that classifies images of birds into a set of two species: Birds of Paradise or Banded Broadbill. 
The codes that were used to train the images:

Install YOLO8: pip install ultralytics

Trin the Model: yolo task=classify mode=train model=yolov8n-cls.pt data=/home/nvidia04/jetson-inference/Final-Project/Dataset epochs=50 imgsz=224

Validate the Model: yolo task=classify mode=val model=runs/classify/train2/weights/best.pt data=/home/nvidia04/jetson-inference/Final-Project/Dataset

Use the Model to Make Predictions: yolo task=classify mode=predict model=/home/nvidia04/jetson-inference/Final-Project/runs/classify/train2/weights/best.pt source=/home/nvidia04/jetson-inference/Final-Project/Dataset/test

Export the Model: yolo export model=/home/nvidia04/jetson-inference/Final-Project/runs/classify/train2/weights/best.pt format=onnx
