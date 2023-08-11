# Piano_Keyboard_Detection_for_SSD_MobileNet_in_GoogleColab
<p align="right">
  <b>Click on the image below to open this file in google colab.</b><br>
  <a href="https://colab.research.google.com/gist/dalabdgw/019955b172571a75a1d95269fa5abe54/keyboard_object_detection_model_for_ssd_in_googlecolab.ipynb"><img src="https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/559ed90c-8aec-47af-a5a7-1f7d56a5fc2f" width="150" height="60"></a>
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


