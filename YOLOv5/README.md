# Piano_Keyboard_Detection_using_YOLOv5
### Description
The piano keyboard detection is an object detection task that detects keyboard on a piano in pictures or videos.<br>
This repository includes a demo for building the keyboard detector using YOLOv5 model.<br>

### Description ipynb files
* <b>Object_Detection_with_YOLO_v5_keyboard.ipynb</b><br>
  An overview file for model training<br>
  Through this file, You can see the process by which we have learned the model, verified it, and performed predictions.<br>
  (You don't need to modify the code to perform it.)
* <b>./pretrained_files/weights/best.pt</b><br>
  This is a model file that pre-learned 2,605 keyboard images with epochs 50.<br>

# Data
  
### Dataset
We collected 2,605 images from divided in 5 technique related videos and we trained these data.<br>
The class is defined as follow:<br>
* keyboard
  
#### File Structure
```bash
keyboard
├── images
│   ├── test
│   ├── train
│   └── val
└── labels
    ├── test
    ├── train
    └── val
```


### Data Collection
We collected data in a variety of ways.<br>
1. We collected 2,605 images from related videos divided in five classes using OpenPose.(fps: 30)<br>

2. We collected about 10 images by searching "playing piano" in google. <br>
#### Data Labeling
##### 1. YOLOv5
We used DarkLabel(Data Labeling Program operating in a Windows environment)
* You can download DarkLabel in Github (https://github.com/darkpgmr/DarkLabel)<br>
* We labeled data following this file. => [DarkLabel.pdf](https://github.com/dalabdgw/Hijab_Detection/files/12026408/DarkLabel.pdf) <br>
![스크린샷 2023-08-10 205234](https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/e581d9e1-5ff1-4e64-831b-55168e58180a)

### Setup
* Clone this repository and install YOLOv5
<pre><code>git clone https://github.com/dalabdgw/Hijab_Detection.git

# install YOLOv5
!git clone https://github.com/ultralytics/yolov5.git
!pip install -r ./yolov5/requirements.txt
</code></pre>

### Training
* --data : yaml file path (yaml file with data set information)
* --weights : Pre-Trained model file path (pt format file), if no value is entered (‘’), initialize and train with a random weight value
* --epochs : epoch size
* --batch : batch size
* --cfg : The model size determined above (saved as a yaml file in the yolov5/models folder)
  * s is the lightest model x is the heaviest model Of course, s has the lowest performance but the highest FPS, and x has the highest performance but the lowest FPS.
<pre><code>python ./yolov5/train.py --img 640 --batch 16 --epochs 50 --data ./dataset/keyboard.yaml --cfg ./models/yolov5s.yaml --weights yolov5s.pt --name piano_yolov5s_results</code></pre>

### Inference
* If training the model was finished, use the following command for inference.
* example
<pre><code>val_img_path = './keyboard/images/test/0_output_staccato_amateur_chopin_etudeop10no4_amateur_staccato_000000000029_rendered.png'
!python ./yolov5/detect.py --weights ./yolov5/runs/train/hijab_yolov5s_results/weights/best.pt --source "{val_img_path}"</code></pre>

# Result 
### Training Result

|epochs|50|100|368|
|---|---|---|---|
|precision|0.999|0.999|0.999|
|recall|1|1|1|
|mAP_0.5|0.995|0.995|0.995|
|mAP_0.5:0.95|0.786|0.805|0.808|
|result_img|![image](https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/502bc0b9-c7ef-4692-91ab-8b88f7714e05)|![image](https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/05eb0390-877f-480f-b136-836fd35a1c94)|![image](https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/469ac853-a389-4b00-8319-727ddc278bd6)|


### Test Result

|epochs 50|
|---|
|![image](https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/b18add1f-dcc4-45f2-bbf8-37b846f0a125)|
|epochs 100|
|![image](https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/f5f6b853-2efc-481d-81a9-0c54f6745684)|
|epochs 368|
|![image](https://github.com/dalabdgw/Piano_Keyboard_Detection/assets/135303032/87833d5e-4d4a-44d2-85a6-b51da6092f89)|
