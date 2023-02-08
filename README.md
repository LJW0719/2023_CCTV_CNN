# CCTV_CNN

This is a project to detect the danger when a lot of people gather in one place.

## 1. Topic description

+ The goal of this project is to predict pressure accidents in advance when enormous people are concentrated considering the number of people and the direction of their movement.

## 2. Problem definition

+ A few months ago, there was a very tragic accident called the 'Itaewon crowd crush' in South Korea. In addition, there have been many crush accidents not only in Itaewon but also in the world. In order to prevent these accidents, the system that can be predicted can prevent possible crushing accidents in the future.

+ One solution is to collect real-time location data using people's cell phones to determine the degree of crowding. This data is called 'base station-based data', but my team couldn't get it, so we considered another solution. And, it's using CCTV.

Reference: https://biz.newdaily.co.kr/site/data/html/2022/11/08/2022110800078.html (Article - predicting possible crushing accidents using base station-based data)

## 3. Analysis Plan

+ It counts the number of people in CCTV footage using yolo technique. (1_Dataset.ipynb, 2_Yolo.ipynb, 3_Count_People.ipynb)

+ It counts the number of cars. (0_preprocessing.ipynb, 4_Count_Car.ipynb)

## 4. Dataset
