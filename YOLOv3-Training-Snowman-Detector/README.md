# Training YOLOv3 : Deep Learning based Custom Object Detector

**This repository contains the code for [Training YOLOv3 : Deep Learning based Custom Object Detector](https://learnopencv.com/training-yolov3-deep-learning-based-custom-object-detector/) blog post**.

[<img src="https://learnopencv.com/wp-content/uploads/2022/07/download-button-e1657285155454.png" alt="download" width="200">](https://www.dropbox.com/sh/y7nhwlcwdy5x923/AABNYP3WuaZlAE_Oz5sT-8usa?dl=1)

1. Install awscli

`sudo pip3 install awscli` 

2. Get the relevant OpenImages files needed to locate images of our interest

`wget https://storage.googleapis.com/openimages/2018_04/class-descriptions-boxable.csv`

`wget https://storage.googleapis.com/openimages/2018_04/train/train-annotations-bbox.csv`

3. Download the images from OpenImagesV4

`python3 getDataFromOpenImages_snowman.py`

4. Create the train-test split

`python3 splitTrainAndTest.py /data-ssd/sunita/snowman/JPEGImages`

Give the correct path to the data JPEGImages folder. The 'labels' folder should be in the same directory as the JPEGImages folder.

5. Install Darknet and compile it.
```
cd ~
git clone https://github.com/pjreddie/darknet
cd darknet
make
```
6. Get the pretrained model

`wget https://pjreddie.com/media/files/darknet53.conv.74 -O ~/darknet/darknet53.conv.74`

7. Fill in correct paths in the darknet.data file

8. Start the training as below, by giving the correct paths to all the files being used as arguments

`cd ~/darknet`

`./darknet detector train /path/to/snowman/darknet.data  /path/to/snowman/darknet-yolov3.cfg ./darknet53.conv.74 > /path/to/snowman/train.log`

9. Give the correct path to the modelConfiguration and modelWeights files in object_detection_yolo.py and test any image or video for snowman detection, e.g.

`python3 object_detection_yolo.py --image=snowmanImage.jpg`



# AI Courses by OpenCV

Want to become an expert in AI? [AI Courses by OpenCV](https://opencv.org/courses/) is a great place to start. 

<a href="https://opencv.org/courses/">
<p align="center"> 
<img src="https://learnopencv.com/wp-content/uploads/2023/01/AI-Courses-By-OpenCV-Github.png">
</p>
</a>
