## **Developed software pipeline to detect and track the vehicle in camera image & video**

This is a project for Udacity Self-Driving Car Nanodegree program. In this project, I built the algorithm to detect and track the vehicle in an image and video, using OpenCV techniques which include Histogram of Oriented Gradients (HOG), color feature extraction algorithm. As training model and classifier, support vector machine (SVM) algorithm was used. The model is implemented in the file `Vehicle_Detection&Tracking_RYANKANG.ipynb`. 

## Requirement 

- Python > 3.5.2
- OpenCV Library
- scikit-learn Library
- TensorFlow/Keras (If you want to try neural network model!)

## Run the Project 

Download training data (vehicle and non-vehicle image data) from [here](http://www.gti.ssr.upm.es/data/Vehicle_database.html) and [here](http://www.cvlibs.net/datasets/kitti/). Run the `Vehicle_Detection&Tracking_RYANKANG.ipynb` on the ipython notebook. (Skip the running 2nd cell which is unnessary part if others use) You can also use images of "test_images" folder and video file of "project_video.mp4" for this project. 

## About the Project 

I constructed the software pipeline with below steps: 

1. Extract HOG, color features with optimized parameters and trained with Linear SVM classifier
2. Implement sliding window search algorithm. 3 different size of windows are used based on the search location. Below image is the search result for test image:   
![Test image](https://github.com/KHKANG36/Vehicle-Detection-Project/blob/master/output_images/Test_example_box.png)
3. Use heatmap with proper threshold value to merge overlapped boxes and remove false positive. Below images are the example:    
![Test image](https://github.com/KHKANG36/Vehicle-Detection-Project/blob/master/output_images/Test_example_heatmap.png)
![Test image](https://github.com/KHKANG36/Vehicle-Detection-Project/blob/master/output_images/Test1_labeledbox.png)
4. Apply the pipeline to video stream. Use the 20 previous frame information to make stable and robust detection.

More detailed explanation for the project is written on "writeup_RYANKANG.pdf" file. 

## Discussion/Issues 

1. Beside of Linear SVM, it should be necessary to find optimal (better) training model such as CNN, Decision Tree model 
2. Intelligent usage of previous frame information is required for all the computer vision projects 
