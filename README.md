# 800project
Title: Building Detection Based on Mask R-CNN
Model: Mask R-CNN
Environment: Tensorflow2

Project Report:

2023/2/19 - 2023/2/23
Successfully built and tested Mask R-CNN model.
During the train part, I firstly used RTX960 GPU to run the model, but failed because of OOM.
Then I bulit the model on GPU RTX3080, and change the environment from TF1.0 to TF2.0.
In the testing phase, I trained and predicted on a dataset containing three different shapes. The three shapes are triangle, circle and square.

2023/2/24 - 2023/2/27
Preparing to train my own dataset.
First, import my own dataset that I have already download.
Then, Used labelme tool to tag building objects in the picture. The total number of the tag data is 500.
I encountered some doubts when labeling the building targets：
  1. In the picture, the target building is sometimes disturbed by trees and other factors, should it be divided according to the size of the building itself as it should be, or should the obstructions be removed manually.
  2. Due to the resolution of the image, the building boundary is sometimes very blurred, if the error caused by the manual division of the target will affect the training effect.
  3. In the pictures of the dataset, sometimes there are groups of buildings blocking each other, what criteria should be used to classify the individual buildings.
I think that when I train and test my own data, I can find out whether I can solve these queries based on the results.

2023/2/27 - 
Train my own dataset by Mask RCNN
After preparing the dataset, I began to train my own data. 
For the first training, I used the best weights from the previous training of shape data process as the weights for the initial training.
At the begining, I can see that the epoch loss is 0.816 that is a very high loss. As the epoch grows, the loss is gradually decreasing. This indicates that the model is running effectively.
