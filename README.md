# tensorflow_glasses_classifier_plus_tflite


Transfer learning with Inception and MobileNet was used as out-of-box solution with options for rapid experimentation in limited time. After series of trials MobileNet was chosen as having less inference time and to satisfy requirement =<3mb for model with low latency (compressed to tflite, realtime <50ms on Mali-T880 MP12). Although more data is required for better accuracy.

<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/Screenshot%20from%202018-12-10%2004-03-46.png" width="1100" height="600" />


<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/Screenshot%20from%202018-12-10%2004-33-28.png" width="1100" height="600" />
MobileNet 0,25 with 224 image size was used to make 1.9mb tflite model then imported on android


<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/tflite/Screenshot_20181210-015903_TfLiteCameraDemo.jpg" width="300" height="500" />
<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/tflite/Screenshot_20181210-020443_TfLiteCameraDemo.jpg" width="300" height="500" />
<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/tflite/Screenshot_20181210-033728_MTP%20application.jpg" width="300" height="500" />
<img src="https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/tflite/Screenshot_20181210-015518_TfLiteCameraDemo.jpg" width="300" height="500" />

Dataset:
See 
[with_glasses.zip](https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/with_glasses.zip)

[without_glasses.zip](https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite/blob/master/without_glasses.zip)
Images from CelebA dataset were used 
