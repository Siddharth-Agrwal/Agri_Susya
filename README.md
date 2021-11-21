# Agri Susya App

### Overview

A flutter based app for farmers integrated with machine learning

App has multiple features - 

* Authentication (OTP based)
* Multilingual for efficient use 
* Rent farming tools
* Plant disease detection
* Crop plantation prediction 

### Technology used

* Flutter
* Tensorflow
* Firebase
* Firestore
* Cloud Messaging
* Firebase Authentication
* Google Teachable Machine
* Pandas
* Numpy
* Real-time Database

### Screenshots/Demo Video



<img src="https://github.com/Kartikey0212/Agri-Susya/blob/main/disease%20recog.jpg" width="250" title="hover text">

<img src="https://github.com/Kartikey0212/Agri-Susya/blob/main/IMG_20210421_083435.jpg" width="250" title="hover text">
<img src="https://github.com/Kartikey0212/Agri-Susya/blob/main/rent.jpg" width="250" title="hover text">
<img src="https://github.com/Kartikey0212/Agri-Susya/blob/main/feed.jpg" width="250" title="hover text">





### Usage

_In order to run the application on your local device make sure to have flutter environment setup on your local device_

[Flutter setup video](https://www.youtube.com/watch?v=fDnqXmLSqtg "Video")

_Clone the repo and open it in any text editor - VS Code for example_

_Connect your mobile in USB Debug mode_

_write in terminal "flutter run"_




ML Powered App to assist farmers in crop disease detection and alerts.

## Machine Learning Model

Multi-Class Image classifier Built on PyTorch framework using CNN architecture. Currently Project Detects 17 States of disease in 4 plants ( Aiming Kerala State ) namely Cherry, Pepper, Potato and tomato.

* Framework : PyTorch
* Architecture : Convolutional Neural Networks
* Validation Accuracy : 77.7%



#### How to train

Upload the **[Python notebook](https://github.com/nadakishormpai2001/Plant_Disease_Detector/blob/main/model/Plant_Disease_Identifier.ipynb)** to Google Colab and run each cell for training the model. I have included a demo dataset to configure quickly. You can use this **[Kaggle Dataset](https://www.kaggle.com/vipoooool/new-plant-diseases-dataset)** which is the original one with huge amount of pictures.

#### How It Works

The input image dataset is converted to tensor and is passed through a CNN model, returning an output value corresponding to the plant disease. Input image tensor is passed through four convolutional layers and then flattened and inputted to fully connected layers.

## API

API is built using Flask framework and hosted in Heroku. The API provides two functionalities, they are

- Plant Disease Detection

    Accepts a POST request with an image in the form of base64 string and returns plant, disease and remedy.
    
- Notification
    
    Accepts a POST request with plant, user and disease , which is then pushed as a notification to other users to warn them regarding a probable outbreak of disease.
    

#### How to use

API has been built on this classifier. URL = "https://plant-disease-detector-pytorch.herokuapp.com/"

User has to send a POST request to the given api with Base64 string of the Image to be input. 

```python
import requests
url = "https://plant-disease-detector-pytorch.herokuapp.com/"
#imgdata = base64 string of image
r = requests.post(url,json = {"image":imgdata})
print(r.text.strip())
```
Output
```python
'{"disease":"Septoria leaf spot","plant":"Tomato","remedy":"Remove infected leaves immediately,......Fungonil and Daconil)."}'
```

## App

#### To Run App

```shell
$ cd app
$ flutter run
```

#### To Build App

```shell
$ cd app 
$ flutter build apk
```








