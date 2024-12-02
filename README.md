# BGRacing - Cone Detection

### Prerequisits:
1. Python <= 3.12
2. Jupyter Notebook
3. Roboflow account

### Installation and Running:
1. clone the project to your machine.
2. Change The API-Key in the Roboflow connection (replace the place holder)
3. run the notebook

### The approach:
The code is based on the YOLOv5s model for object detection.
The v5s version is suitable for this case because it is suitable for running on the cpu, and compared to more advanced versions such as the v8 it is considered more user friendly and begginner aproachable.
The model is trained on cone images found in [roboflow](https://universe.roboflow.com/mms-ceu49/cone_detection-q6gnx/dataset/1).
The data is seprated in advanced (existing roboflow project) to train, test and validation.
#### Training:
The YOLOv5 repository contains a python script for training the model, and exporting the weights after the run.
There are 2 outputs after the training:
  - best.pt: the trained model weight with best loss score between the epochs
  - last.pt: the trained model weights after the last epoch.
The chosen trained model in the notebook is the best.pt, though there was only one epoch that ran succesfully therefore both weights are equal.

#### Running:
The YOLOv5 repository contains a python script for object detection. The input of this script is the video to detect on, the weights of the model, and a confidence level.
When a label (cone detection and color) receives a higher probability than the confidence level, the label is added to the video.

