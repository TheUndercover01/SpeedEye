# SpeedEye : Redefining Motion Awareness, One Frame at a Time!

<h3>How does it work</h3>

<h4>DeepSort</h4>

<h5>What is DeepSort</h5>

Imagine you're watching a video of a busy street. DeepSORT is like a smart detective that watches the video and keeps an eye on things for you. It can follow cars as they move around, even if they temporarily disappear behind something. DeepSORT is great at remembering how cars move and what they look like. So, even if things get a bit tricky and you can't see a car for a moment, DeepSORT can still figure out which car is which and where they're headed. It's like a friendly tracker that makes sure no car goes unnoticed in the video. There are three critical parts in DeepSORT : 

Detection:
The detection component involves identifying and localizing objects of interest within video frames. In this project, YOLOv8 is utilized for this purpose, enabling rapid and accurate car detection. YOLOv8 processes each frame and generates bounding box coordinates along with class labels, indicating the presence of cars. These detections serve as the starting point for object tracking in the DeepSORT algorithm.

Kalman Filter:
The Kalman filter is a mathematical technique used for predicting and estimating the state of dynamic systems. In the context of DeepSORT, the Kalman filter is applied to predict the future location of each detected object based on its previous trajectory and motion patterns. As video frames progress, the Kalman filter's predictions are continually updated using both new detection information and the object's historical trajectory. This prediction-correction process helps account for uncertainties in object movement, providing a smoother and more accurate estimate of an object's position.

Deep Association Metric:
The deep association metric is a key element in DeepSORT's ability to associate and match detected objects across frames. It involves calculating a similarity score between the embeddings (numerical representations) of detected objects in consecutive frames. These embeddings capture object appearance characteristics. By comparing the embeddings of current detections with those from previous frames, DeepSORT establishes associations between objects over time. The deep association metric helps determine which detections correspond to the same real-world object, even if their appearances slightly vary due to changes in lighting, orientation, or occlusions.

<h6>How was DeepSORT implemented?</h6>

There were a couple implementation issues with DeepSORT, 

First - It is incompatable with tensorflow 2.0 and above. Solution : change the sourse code accordingly
Second - There is no particular way to integrate our own detection system . Solution : I wanted to use the best detection model i.e. Yolov8, and to do so I needed to implement a complete tracker (shown in class Tracker). 

Once you get these issues sorted, it is straight forward. But one thing is still left!

Link to the Github repo for deepSORT : https://github.com/nwojke/deep_sort.git

Link to the paper : https://arxiv.org/abs/1703.07402

<h5>What is Yolov8</h5>

A much better and detailed explanation can be give by this article : https://medium.com/cord-tech/yolov8-for-object-detection-explained-practical-example-23920f77f66a

