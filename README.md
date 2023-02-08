# CCTV_CNN

This is a project to detect the danger when a lot of people gather in one place.

## 1. Topic description

+ The goal of this project is to predict pressure accidents in advance when enormous people are concentrated considering the number of people and the direction of their movement.

## 2. Problem definition

+ A few months ago, there was a very tragic accident called the 'Itaewon crowd crush' in South Korea. In addition, there have been many crush accidents not only in Itaewon but also in the world. In order to prevent these accidents, the system that can be predicted can prevent possible crushing accidents in the future.

+ One solution is to collect real-time location data using people's cell phones to determine the degree of crowding. This data is called 'base station-based data', but my team couldn't get it, so we considered another solution. And, it's using CCTV.

Reference: https://biz.newdaily.co.kr/site/data/html/2022/11/08/2022110800078.html (Article - predicting possible crushing accidents using base station-based data)

## 3. Analysis Plan

+ First, count the number of people in CCTV footage using yolo technique. (1_Dataset.ipynb, 2_Yolo.ipynb, 3_Count_People.ipynb)

+ Second, count the number of cars. (0_preprocessing.ipynb, 4_Count_Car.ipynb)

+ Third, add the number of people and the number of cars.

## 4. Dataset

+ When count the number of people, CCTV video is used.

+ When count the number of cars, JSON file is used.

## 5. Count the number of people (Deep Learning)

+ Yolo: It is a single-step object detection algorithm. The YOLO algorithm divides the original image into equal-sized grids.

+ Yolo detects human objects and measures the number of people by dividing them by frame. And we randomly divided the criteria to determine the degree of safety.

## 6. Count the number of cars (Machine Learning)

+ Preprocessing: It extracts car data using 'objects' key in JSON file.

+ It measures the number of cars by dividing them by frame. And we randomly divided the criteria to determine the quantity.

## 7. Conclusion

### 1) Limitations

+ The direction in which people or cars move has not been made into a deep learning model.

+ It was difficult to specifically calculate how the direction of movement of people or cars affects the degree of risk.

### 2) Human Pose Estimation

+ Introduction: Human pose estimation is performed by optimizing the objective function for geometric model fitting or by computing either the maximum likelihood estimate or the maximum a posteriori probability estimate in the probabilistic model.

+ (1) Training Data: It predefines to directly localize the particular skeletal joints of interest or to be combined to predict the position of other joints and the method applies the random-forest-based body part recognition algorithm to each pixel of the human region in the input depth image.

+ (2) Random Forest Classification: For each tree, new training images are selected by sampling from the training images uniformly with replacement.

+ (3) Mean Shift Mode Detection: The gradient vector is expressed by computing the weighted mean in the window centered on the current point. Finally, the mode points are obtained by merging the end points of the converging trajectories.

Reference: https://scienceon.kisti.re.kr/commons/util/originalView.do?cn=JAKO201344962318172&oCn=JAKO201344962318172&dbt=JAKO&journal=NJOU00020340

### 3) Future Plan

+ In CCTV video, it finds the area of the street and the number of people per area.

+ It creates models that predict people's path and calculates situations that can be dangerous.
