# tensorflow_glasses_classifier_plus_tflite


Transfer learning with Inception and MobileNet was used as out-of-box solution with options for rapid experimentation in limited time. After series of trials MobileNet was chosen for better inference time and requirement <3mb for model with low latency (compressed to tflite, realtime <50ms on Mali-T880 MP12). Although more data is required for better accuracy. 

Launching 
```
git clone https://github.com/ZackPashkin/tensorflow_glasses_classifier_plus_tflite
cd tensorflow_glasses_classifier_plus_tflite
```


```
# Put your data in tf_files/dataset
# MobileNet is available 0.25; 0,5; 0.75 and 1.0
# Image size can be 128,160,192, 224 pixels.

IMAGE_SIZE=224 
ARCHITECTURE="mobilenet_0.50_${IMAGE_SIZE}"
  
python -m scripts.retrain \
  --bottleneck_dir=tf_files/bottlenecks \
  --how_many_training_steps=1000 \
  --model_dir=tf_files/models/ \
  --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" \
  --output_graph=tf_files/retrained_graph.pb \
  --output_labels=tf_files/retrained_labels.txt \
  --architecture="${ARCHITECTURE}" \
  --image_dir=tf_files/dataset 
  
```

```
#make prediction
#change image adding name from your dataset
 python -m scripts.label_image \
    --graph=tf_files/retrained_graph.pb  \
    --image=tf_files/dataset/without_glasses/000004.jpg \
    --labels=tf_files/retrained_labels.txt

```


```
#Compress model converting to TFlite format

#IMAGE_SIZE=224
!tflite_convert \
  --graph_def_file=tf_files/retrained_graph.pb \
  --output_file=tf_files/optimized_graph025_224.lite \
  --input_format=TENSORFLOW_GRAPHDEF \
  --output_format=TFLITE \
  --input_shape=1,224,224,3 \
  --input_array=input \
  --output_array=final_result \
  --inference_type=FLOAT \
  --input_data_type=FLOAT
```
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

