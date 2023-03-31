
# Emotion Detection

Emotion Detection Model Detects the realtime Face expressions or any detects the expression in any video which is passed in the model with the help opencv library and keras library.


## Screenshots

![App Screenshot](https://github.com/Suyash9422/tp/blob/main/Screenshot%20(768).png?raw=true)

For Now The Accuracy of the model is low 


## Requirements

```bash
  Firstly you need any IDE installed on your system (For eg VS Code,Pycharm,etc)
```
Then You need to download Dataset ,which can be found on kaggle using following link or you can found it in the zip file of project.
```bash
 https://www.kaggle.com/datasets/msambare/fer2013
```

Following Libraries Should be downloaded in yuor system before working on model
```bash
 pip install tensorflow
 pip install pillow
 pip install keras
 pip install opencv-python
```
```bash
 IMPORTANT NOTE : THIS MODEL NEEDS COMPUTIONAL POWER SO TRY ONLY WHEN YOU HAVE HIGH CONFIGURATION SYSTEM OR VM(VIRTUAL MACHINE)
```
IN MY CASE I HAVE RYZEN 5 -3550h CPU AND 16 GB RAM AND IT TAKES AROUND 3 HOURS ON THIS SYSTEM.
## Deployment

To deploy this project follow following steps :

Firstly Download the zip file of the project from my github repo using following link
```bash
  https://github.com/Suyash9422/Machine_learning/tree/main/Emotion_detection
```
Then after downloading the zip file extract it to directorary of your choice.

Then open the extracted folder from vs code.
then open the TrainEmotionDetection.py file ans replace line number no. 15,23 according to the downloaded dataset from kaggle. 
```bash
  train_generator = train_data_gen.flow_from_directory(
        'data/train',     #this one
        target_size=(48, 48),
        batch_size=64,
```

```bash
  validation_generator = validation_data_gen.flow_from_directory(
        'data/test',
        target_size=(48, 48),
        batch_size=64,
```
Then run the code , it will around 3-5 Hours to train the dataset depending on your machine.

After complete Execution , open the TestEmotionDetection file and replace line no. 9,15 with the full address of the emotion_model.json and  emotion_model.h5 file address 

```bash
json_file = open('f:/ML/Emotion_detection/model/emotion_model.json', 'r')   #REPLACE ADRRESS ACCORDING TO YOUR SYSTEM 
loaded_model_json = json_file.read()
json_file.close()
emotion_model = model_from_json(loaded_model_json)
```
```bash
emotion_model.load_weights("f:/ML/Emotion_detection/model/emotion_model.h5")    #REPLACE ADRRESS ACCORDING TO YOUR SYSTEM
print("Loaded model from disk")
```
Then if you want to test model on live cenerio then comment out line no 24 and uncomment line no 23 and if we you want to test on video comment line no. 23 and uncomment line no. 24 and pass the full address of the video file.

```bash
#cap = cv2.VideoCapture(0)
cap = cv2.VideoCapture("F:/ML/Emotion_detection/test1.mp4")
```
Lastly Replace the line no. 32 with the full address of haarcascades file according to your case.

```bash
face_detector = cv2.CascadeClassifier('f:/ML/Emotion_detection/haarcascades/haarcascade_frontalface_default.xml')   #REPLACE ADRRESS ACCORDING TO YOUR SYSTEM
```

After all this changes click the run button and that's all !!!