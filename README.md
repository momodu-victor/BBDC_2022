# Bremen Big Data Challenge 2022

## Task/Goal

A block of missing frames has resulted from the absence of several consecutive frames in the appropriate files. The length, number, and placement of the missing frame components varies. There may be a difference in the amount of missing frame blocks between the video and motion capture data. 

The task of sequence modelling is the focus of the Bremen Big Data Challenge 2022. It's all about correctly reconstructing missing data from movement sequences recorded with two separate modalities in detail.

## Data Background
The Bremen Big Data Challenge Committee provided the dataset used. 

The video data was recorded from the first-person perspective and had a resolution of 96x160 pixels and a frame rate of 30 frames per second (fps). 

The head motion capture recordings with 9 features parallel to each frame of video data. The values are given in absolute spatial positions. 

The centre of the room is indicated by the coordinates (0,0,0). Millimetres are the unit of measurement for features.
  
## Methodology

This big data challenge was approached with RNN Multivariate Time Series Forecasting using LSTM to identify the sequence of missing frames. We were able to predict both motions captured, and video captured missing frames and converted the pixels to video.

![image](https://user-images.githubusercontent.com/62265294/173184138-fa761a02-5e36-4e59-b6a3-ccfd38aa8854.png)


## Results

After the training and predictions were complete, the predicted values captured in motion are saved in a single csv file. Similarly, the predicted pixel values from all 39 videos captured are saved in a single csv file.
The total number of observations in the final motion capture was 20,888, with 9 variables. The predicted pixel values for video data were first converted into images and then into video files. The video file had 96x159 variables and 62,953 frames, with a total duration of 11 minutes and 39 seconds.
The final files "video.mp4" and "mocap.csv" were filled with the reconstructed frames. These was then uploaded to the BBDC 2022 Submission Portal, and the score was then automatically calculated and displayed on the leader board. After evaluation, a score of 0.3325 was obtained after 2 submissions.
