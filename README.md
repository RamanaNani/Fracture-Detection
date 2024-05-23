<center><h1>Bone Fracture Detection</h1></center>

It is a multi class object detection task.

## Problem Statement
The main of the project is to develop a model for automated bone fracture detection.

## Dataset Description
To know more about the dataset go through [Roboflow](https://universe.roboflow.com/veda/bone-fracture-detection-daoon/dataset/4)

The dataset contains images categorized into different classes, each representing a specific type of bone fracture. These classes include
* Elbow Positive
* Fingers Positive
* Forearm Fracture
* Humerus Fracture
* Shoulder Fracture
* Wrist Positive

## Methodolody
### Augmentation
The data augmentation techniques we have performed are:
* Random Brightness Contrast: To mimic the variations in X-ray expsoure levels
* Elastic transform: Creates realistic and non-realistic distortions in images which simulate minor variations in the positioning of patients or soft tissuse around the bones
* CLACHE: Enhance X-ray images by improving the visibility of subtle fractures and by enhancing local contrast with out amplifying the noise
* Sharpen: Enhance the edges and details of X-ray image which make the features easier to perceive. Minly useful to identify hairline fractures
* Gaussian noise: To mimic the varying levels of noise to X-ray machine qualities

### Models
We have trained the data using YOLOv4, Faster R-CNN and Detection transformers. We used Detection transformers because detection transformers excel in this bone fracture detection dataset due to their ability to capture complex spatial relationships and patterns within images, crucial for accurate detection of fractures. Their self-attention mechanism enables effective feature extraction across varying fracture types and anatomical regions, enhancing model performance. Additionally, detection transformers can efficiently handle the diverse classes and annotations present in the dataset, facilitating robust training and evaluation of fracture detection algorithms. Leveraging detection transformers accelerates the development of precise and scalable computer vision solutions for automated fracture detection, advancing medical diagnostics and enhancing patient care.

### Conclusion
By experimenting with these three models, Detection transformer is working well to classify the image type and create bounding boxes as compared to remaining two models. The main reason behind this is it’s attention mechanism and number of parameters. The number of epochs used to train the models are YOLOv4 (14000 epochs), Faster R-CNN (70 epochs) and for Detection Transformers(75 epochs). From the three models only Detection transformer is able to predict the Bone fracture class and creating bounding boxes.
