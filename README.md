
![header](https://www.retinamd.com/Customer-Content/www/CMS/files/diabetic-retinopathy.jpg)

# Classifying Diabetic Retinopathy via Transfer Learning 
This notebook aims to predict the various levels of [Diabetic Retinopathy (DR)](https://en.wikipedia.org/wiki/Diabetic_retinopathy), damage to blood vessels in the eye caused by diabetes. 

The notebook demonstrates the application of [transfer learning](https://en.wikipedia.org/wiki/Transfer_learning) using a pre-trained [MobileNetV2](https://keras.io/api/applications/mobilenet/) model with weights from ImageNet.


The diabetic retinopathy dataset used for training and testing can be found on [Kaggle](https://www.kaggle.com/amanneo/diabetic-retinopathy-resized-arranged)

# Model Summary 
MobileNetV2 was chosen because of it's accuracy, and speed while being lightweight. The original output layer was replaced with a fully connected dense layer containing 5 nodes, predicting each level of severity of the instance - ranging from absence of DR, to proliferative DR.

The model was trained on 50 epochs, with a learning

## Preprocessing 
There was different lighting conditions in some of the images, leading to some being brighter than others and making the features of mild DR hard to identify. 

To enhance the features of DR in mild cases, the images were converted to greyscale, then the contrast was adjusted via [histogram equalization](https://en.wikipedia.org/wiki/Histogram_equalization). Additionally, the images were resized to 224x224 to fit MobileNetV2's input layer. 

### Preprocessed Images
![preprocessed images](https://www.kaggleusercontent.com/kf/54977248/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..TKdeojEv-uvFuv7C9r3W8w.xiQKQaYxASx_emg4iIwJ_7mu1qs_a90_Z-XagrX8pMvLS_E0e_Lsb-bVM0p8o4l18Din7nyduuBKV7gr8MD5gQZTDAk30FZD6TwMw5KkHQnCELeUY8Z7R9HoMbNUwUNwrKGkpxNX9UjYDb6dxJxoW55Nej_p6YUHZaVwywtUDbZ2GeXN6QsZ_A2Jiydti4Fz7yxOWwxtBHNflj_PswkbN1Z5Tt7Q9V8wohebPSgQiE7wIq1sI2FMOcHoSje0KydOc8jGVteX6jrnzhHwBZ02HrJacZzuntyC1pBAPS2mqNnGuvI7hZEBqq35iiDrqcsm58aSn-FZrMLEI7qNBqFD5sjR7ESQJNVhcS92fN00sZF87aL-DKay_0RdlURPXzJAoeI3o9iuVKPjxE-ED8OJ74yOzSZjwWZ4JJsRbmhuf25_NXMSn0moB8Qpx40u8zTbQMSy8Ffr9G_P7sW-WDyGTViwx8V4SmXG6bnRuJnciGfZPuaSCdl6DqMcVXKl9zbFbnQwGNuZ8pPVVPVTRaTc67k9pvTlDiLC-kPLweba7L8KBGrJX7a1yHFAeATkjURwZCHzrsRKoFF9jHPl84FOZJyqDvl5aAL0JPAvwrDSybVBhhfbVh8qn4_7bo9Eu0M7JdLsspRBzLyH8P0gepRIq_trzDcgFx2z9G2cWKXbctJGjp5jpA-BEvftGBavi4Y8.vBdHUFtRXwlagBOoWod8zg/__results___files/__results___12_2.png)

## Model Performance Metrics
|Training Parameter  | Value |
|--|--|
| Number of Epochs | 50 |
| Learning Rate| 0.001 |
| Loss Function | Categorical Crossentropy |
| Optimizer | Adam |

<hr>

| Set| Metric | Result | 
|--|--|--|--|--| 
| Training | Accuracy | 0.9286 |  |  | 
| | Loss | 0.4294 |  |  | 
| Validation| Accuracy | 0.6017 |  |  | 
| | Loss | 6.6678 |  |  | 
| Testing | Accuracy | 0.6086 |  |  | 
| | Loss | 3.9230 |  |  | 

# Technologies Used
## Modeling
- [Keras](https://keras.io/)
- [TensorFlow](https://www.tensorflow.org/)
- [Scikit-learn](https://scikit-learn.org/stable/)
- [Numpy](https://numpy.org/)
## Visuals
- [Matplotlib](https://matplotlib.org/)

---
