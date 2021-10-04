# The born recognition system using Mediapipe by google

### Environment
- Windows 10 home Insider Preview 10.0.21327 build 221327
  - Core(TM) i7-9700K CPU @ 3.60GHz
- Anaconda 4.8.2
- Web Camera

### Requirement
- mediapipe==0.8.5
- opencv-python==4.5.1.48


### Usage
#### Setup
```
(base) $ git clone https://github.com/T-Sumida/mediapipe_python4windows.git
(base) $ conda create -n mediapipe python=3.7
(base) $ conda activate mediapipe
(mediapipe) $ conda install requests
(mediapipe) $ pip install mediapipe==0.8.5, loguru
```

#### Demo
```
(mediapipe) $ python mediapipe_sample.py -h
usage: mediapipe_sample.py [-h] [--device DEVICE] [--width WIDTH]
                           [--height HEIGHT]
                           {FaceDetector,FaceMesh,HandTracker,PoseEstimator,Objectron,Holistic,SelfieSegmentation}
                           ...

positional arguments:
  {FaceDetector,FaceMesh,HandTracker,PoseEstimator,Objectron,Holistic,SelfieSegmentation}
    FaceDetector
    FaceMesh
    HandTracker
    PoseEstimator
    Objectron
    Holistic
    SelfieSegmentation

optional arguments:
  -h, --help            show this help message and exit
  --device DEVICE       device id
  --width WIDTH         capture width
  --height HEIGHT       capture height
```

##### Hands
The sample is to get the landmark of hands
```
(mediapipe) $ python mediapipe_sample.py HandTracker -h
usage: mediapipe_sample.py HandTracker [-h] [--max_num_hands MAX_NUM_HANDS]
                                       [--min_detection_confidence MIN_DETECTION_CONFIDENCE]
                                       [--min_tracking_confidence MIN_TRACKING_CONFIDENCE]

HandTracker

optional arguments:
  -h, --help            show this help message and exit
  --max_num_hands MAX_NUM_HANDS
                        最大検出手数
  --min_detection_confidence MIN_DETECTION_CONFIDENCE
                        手検出モデルの最小信頼値 [0.0, 1.0]
  --min_tracking_confidence MIN_TRACKING_CONFIDENCE
                        ランドマーク追跡モデルの最小信頼値 [0.0, 1.0]
```
Example
```
(mediapipe) $ python mediapipe_sample.py HandTracker
```
<img src=./pic/hand.jpg width=500>


##### Pose
The sample is to get the human born
```
(mediapipe) $ python mediapipe_sample.py PoseEstimator -h
usage: mediapipe_sample.py PoseEstimator [-h]
                                         [--min_detection_confidence MIN_DETECTION_CONFIDENCE]
                                         [--min_tracking_confidence MIN_TRACKING_CONFIDENCE]

PoseEstimator

optional arguments:
  -h, --help            show this help message and exit
  --min_detection_confidence MIN_DETECTION_CONFIDENCE
                        姿勢推定モデルの最小信頼値 [0.0, 1.0]
  --min_tracking_confidence MIN_TRACKING_CONFIDENCE
                        ランドマーク追跡モデルの最小信頼値 [0.0, 1.0]
```
Example
```
(mediapipe) $ python mediapipe_sample.py PoseEstimator
```



##### Holistic
The sample is to get functions (e.g. Face Mesh、Hands、Pose) by google
```
(mediapipe) $ python mediapipe_sample.py Holistic -h
usage: mediapipe_sample.py Holistic [-h]
                                    [--min_detection_confidence MIN_DETECTION_CONFIDENCE]
                                    [--min_tracking_confidence MIN_TRACKING_CONFIDENCE]

Holistic

optional arguments:
  -h, --help            show this help message and exit
  --min_detection_confidence MIN_DETECTION_CONFIDENCE
                        人物検出モデルの最小信頼値 [0.0, 1.0]
  --min_tracking_confidence MIN_TRACKING_CONFIDENCE
                        ランドマーク追跡モデルの最小信頼値 [0.0, 1.0]
```
Example
```
(mediapipe) $ python mediapipe_sample.py Holistic
```
