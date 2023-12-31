# Piano_Keyboard_Detection_for_SSD_MobileNet_in_GoogleColab
<p align="right">
  <b>Click on the hyperlink below to open this file in google colab.</b><br>
  <a href="https://colab.research.google.com/gist/dalabdgw/019955b172571a75a1d95269fa5abe54/keyboard_object_detection_model_for_ssd_in_googlecolab.ipynb">Open this file in google colab</a>
</p>

### Description
The piano keyboard detection is an object detection task that detects keyboard on a piano in pictures or videos. This repository includes a demo for building the keyboard detector using SSD-MobileNet model.<br>
For more information, please refer to Keyboard_Object_Detection_Model_for_SSD_in_GoogleColab.ipynb file attached from this repository.

### Files & Folder Structure
In order to have the following file structure, please follow the instructions given by opening code in google colab.
It is important for the SSD MobileNet model to keep files and folder structure.
```bash
content
├── images.zip
├── labelmap.pbtxt
├── labelmap.txt
├── train.tfrecord
├── val.tfrecord
├── custom_model_lite
│   └── saved_model
│       ├── assets
│       └── variables
├── images
│   ├── all
│   ├── new_test
|   ├── test
│   ├── train
│   └── validation
├── mAP
|   ├── input
│   ├── outputs
│   └── scripts
├── models
│   ├── community
│   ├── docs
│   ├── mymodel
│   ├── official
│   ├── orbit
│   ├── research
│   │   └── object_detection
│   └── tensorflow_models
└── training
```

# Data
We collected data in a variety of ways.
![ssd-mobilenet](https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/8ee67d80-1424-45cd-b142-d7ceaee5b29f)

### Dataset
The class is defined as follow:
- keyboard

### Data Collection
1. We collected 2,605 images from related videos divided in five classes using OpenPose.(fps: 30)

2. We collected about 10 images by searching "playing piano" in google.

#### Data Labeling
First, we create labeled data using DarkLabel(Data Labeling Program operating in a Windows environment) for YOLOv5.<br>
Second, we converted labeled data for YOLOv5 to Pascal VOC data.<br>
Finally, we converted Pascal VOC data to csv files to make tfrecord files.
![259731714-e581d9e1-5ff1-4e64-831b-55168e58180a](https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/c0b45a18-842d-40b6-ab7b-ef87a1c718b7)
* You can download DarkLabel in Github (https://github.com/darkpgmr/DarkLabel)


# Result 
### Training Result

|steps|loss function|learning rate|
|---|---|---|
|20,000|![image](https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/ee43dc33-d673-4256-ad93-a155989cf22e)|![image](https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/c81508a1-c959-45d7-b4a1-c9cb4f4e2dae)|
|30,000|![image](https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/84db9aec-3935-4b40-b455-6ff9435b1ea5)|![image](https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/bf929068-6fa3-4150-9943-334791e26f2e)|


### Test Result (tested on models with training steps 30,000)

|existed datasets|new test dataset|
|---|---|
|![image](https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/07dbe973-d327-4801-89c8-4c3b4fbde5d6)|![image](https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/b188755b-36da-4e93-b011-492e7cd2900f)|


