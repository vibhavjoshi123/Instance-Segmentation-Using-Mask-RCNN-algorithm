# Instance-Segmentation-Using-Mask-RCNN-algorithm
Using Custom dataset we will do instance segmentation on laptop and keyboard as clases

Mask RCNN has been the new state of art in terms of instance segmentation. There are rigorous papers, easy to understand tutorials with good quality open source codes around for your reference. Here I want to share some simple understanding of it to give you a first look.


Mask RCNN is a deep neural network aimed to solve instance segmentation problem in machine learning or computer vision. In other words, it can separate different objects in a image or a video. You give it a image, it gives you the object bounding boxes, classes and masks.


There are two stages of Mask RCNN. First, it generates proposals about the regions where there might be an object based on the input image. Second, it predicts the class of the object, refines the bounding box and generates a mask in pixel level of the object based on the first stage proposal. Both stages are connected to the backbone structure.


What is backbone? Backbone is a FPN style deep neural network. It consists of a bottom-up pathway , a top-bottom pathway and lateral connections. Bottom-up pathway can be any ConvNet, usually ResNet or VGG, which extracts features from raw images. Top-bottom pathway generates feature pyramid map which is similar in size to bottom-up pathway. Lateral connections are convolution and adding operations between two corresponding levels of the two pathways. FPN outperforms other single ConvNets mainly for the reason that it maintains strong semantically features at various resolution scales.

![rc1](https://user-images.githubusercontent.com/37294597/90334256-f809fe80-dfe9-11ea-9f56-66bb0c555343.jpeg)


![rc2](https://user-images.githubusercontent.com/37294597/90334260-fb04ef00-dfe9-11ea-9c4e-685a657ff2d1.png)

Used custom dataset of laptops and labelled them and drew mask on them using labelling software

converted them to json and split them in train and test dataset

Converted them to COCO dataset format using script to convert them

Using google colab registered them with COCO dataset

Using Detectron 2(open source library )performed transfer learning to train model on custom dataset for mask of laptop and keyboard

Using test dataset we tested our model to draw mask and it performed very well for mask on laptop and keyboard


![rc3](https://user-images.githubusercontent.com/37294597/90334295-4a4b1f80-dfea-11ea-8d74-11ef54c8f431.png)



![rc4](https://user-images.githubusercontent.com/37294597/90334297-4f0fd380-dfea-11ea-8a97-6099e2fda206.png)
