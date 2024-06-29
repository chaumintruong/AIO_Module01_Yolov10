# Project: YOLOv10 Helmet Safety Detection

## Overview

This project aims to train the YOLOv10 model for Helmet Safety Detection using a custom dataset. YOLOv10 is fine-tuned on the dataset to detect workers wearing safety helmets.

## Steps to Train the Model

1. Dataset Download and Preparation:

- Download the Helmet Safety Detection dataset from the provided link.
- Extract the dataset into the `safety_helmet_dataset` folder.

```
!gdown '1twdtZEfcw4ghSZIiPDypJurZnNXzMO7R'
!mkdir safety_helmet_dataset
!unzip -q '/content/Safety_Helmet_Dataset.zip' -d '/content/safety_helmet_dataset'
```

2. Install Required Libraries:

- Clone the YOLOv10 repository and install dependencies.

```
!git clone https://github.com/THU-MIG/yolov10.git
%cd yolov10
!pip install -q -r requirements.txt
!pip install -e .
```

3. Initialize YOLOv10 Model:

- Initialize YOLOv10 with the nano version (`yolov10n.pt` pretrained weights).

```
from ultralytics import YOLOv10

MODEL_PATH = 'yolov10n.pt'
model = YOLOv10(MODEL_PATH)
```

4. Model Training:

- Train the YOLOv10 model on the Helmet Safety Detection dataset for 50 epochs with image size 640.

```
YAML_PATH = '../safety_helmet_dataset/data.yaml'
EPOCHS = 50
IMG_SIZE = 640
BATCH_SIZE = 256

model.train(data=YAML_PATH,
            epochs=EPOCHS,
            batch=BATCH_SIZE,
            imgsz=IMG_SIZE)
```

5. Model Evaluation:

- Evaluate the trained model on the test set.

```
TRAINED_MODEL_PATH = 'runs/detect/train/weights/best.pt'
model = YOLOv10(TRAINED_MODEL_PATH)

model.val(data=YAML_PATH,
          imgsz=IMG_SIZE,
          split='test')
```

## Conclusion

- This readme provides a comprehensive guide to setting up and training the YOLOv10 model for Helmet Safety Detection using custom data. Adjust paths and parameters as necessary for your specific setup.