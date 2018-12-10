# tensorflow_glasses_classifier_plus_tflite


Transfer learning with Inception and MobileNet was used as out-of-box solution with options for rapid experimentation in limited time. After series of trials MobileNet was chosen as having less inference time and to satisfy requirement =<3mb for model with low latency (compressed to tflite, realtime <50ms on Mali-T880 MP12). Although more data is required for better accuracy.


[Colab Notebook](https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/Glasses_TensorFlow_Classifier1.ipynb)


<table class="tfo-notebook-buttons" align="left"><td>
<a target="_blank"  href="https://colab.research.google.com/drive/10aiqHcCykGfzd6cIYslzACa8JIve0eUW">
    <img src="https://www.tensorflow.org/images/colab_logo_32px.png" />Run in Google Colab</a>  
</td><td>


<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/Screenshot%20from%202018-12-10%2004-03-46.png" width="1100" height="600" />


<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/Screenshot%20from%202018-12-10%2008-35-58.png" width="1100" height="500" />
<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/Screenshot%20from%202018-12-10%2008-36-55.png" width="1100" height="500" />
<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/Screenshot%20from%202018-12-10%2008-37-51.png" width="1100" height="500" />
<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/Screenshot%20from%202018-12-10%2008-39-24.png" width="1100" height="500" />

<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/Screenshot%20from%202018-12-10%2008-43-14.png" width="1100" height="500" />



MobileNet 0,25 with 224 image size was used to make 1.9mb tflite model then imported on  
[android](https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/tree/master/tflite)








<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/tflite/Screenshot_20181210-015903_TfLiteCameraDemo.jpg" width="300" height="500" />
<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/tflite/Screenshot_20181210-020443_TfLiteCameraDemo.jpg" width="300" height="500" />
<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/tflite/Screenshot_20181210-033728_MTP%20application.jpg" width="300" height="500" />
<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/tflite/Screenshot_20181210-015518_TfLiteCameraDemo.jpg" width="300" height="500" />

Dataset:
See 
[with_glasses.zip](https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/with_glasses.zip)

[without_glasses.zip](https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/without_glasses.zip)
Images from CelebA dataset were used 


Demo app:[apk](https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/glassses_classifier.apk)



Possible improvements:
- Add more data (now it's only <150images/label)
- [MobileNetV2 architecture](https://ai.googleblog.com/2018/04/mobilenetv2-next-generation-of-on.html)

<img src="https://2.bp.blogspot.com/-E7CT0RHBWq4/WsKlTgEeX2I/AAAAAAAACh0/dp1B4yh6O2k4H1LuC7BA-EKzrL7W0L8iACLcBGAs/s640/image2.png" width="800" height="500" />

