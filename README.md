
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
<img src="https://github.com/JP-sDEV/Diabetic-Retinopathy-Classification/blob/main/preprocessed_imgs.png" width="100%">

## Model Performance Metrics
|Training Parameter  | Value |
|--|--|
| Number of Epochs | 50 |
| Learning Rate| 0.001 |
| Loss Function | Categorical Crossentropy |
| Optimizer | Adam |

<hr>

| Set| Metric | Result | 
|--|--|--|
| Training | Accuracy | 0.9286 |
| | Loss | 0.4294 |
| Validation| Accuracy | 0.6017 |
| | Loss | 6.6678 |
| Testing | Accuracy | 0.6086 |
| | Loss | 3.9230 |

# Technologies Used
## Modeling
- [Keras](https://keras.io/)
- [TensorFlow](https://www.tensorflow.org/)
- [Scikit-learn](https://scikit-learn.org/stable/)
- [Numpy](https://numpy.org/)
## Visuals
- [Matplotlib](https://matplotlib.org/)

---
