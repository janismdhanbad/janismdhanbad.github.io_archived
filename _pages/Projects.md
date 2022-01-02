---
permalink: /projects/
title: "Projects"
---


## Projects

### Pavement Digital asset management using Deep Learning at Atkins:
Here, the target was to detect and recognize the type and severity of defect on top-view roadimages. For transforming input data to make it deep learning training ready, GDAL and shapelywas used. The final solution consisted of classification of an input image into asphalt/concreteusing a ResNet-18(accuracy 88%) model followed by the detection and classification of type andseverity of the defects. For Asphalt, I used Mask-RCNN(accuracy 77%) to detect and classify thedefect type which was then input to a classification (ResNet-50 accuracy 94%) network giving theseverity(low, medium, high) of cropped defective sections. For Concrete, I trained three end-to-end models for Joints, corner and center defects type and severity of that gave an accuracy ofabout 85% each. Each model used InceptionV3 as a feature extractor followed by fully connectedlayers giving type, location and severity of the defects. Apart from the core computer visionsolution, I also worked on post processing the distress information so that it can be used in anAtkins proprietary tool. The final outputs were in the form of shapefiles which can be visualized inQGIS for analysis of pavements and decision making on them. This was awarded with Excellenceaward. (SE): keras, tensorflow, fastai GDAL, shapely, OpenCV, scikit-image, AWS

### SparseTensor VAE for 3D data:

This is an ongoing research project where I am working under Professor Justin Johnson on the problemof reconstruction of 3D data using Variational Autoencoder with quantized latent space. The overallresearch premise is to decouple different attributes in a 3D scene using quantized embeddings andleveraging different embeddings to generate novel scenes.


### Intent estimation and activity recognition at Intvo:

In this project, my task was to develop a deep learning model for intent(of a person crossing theroad) estimation and an activity recognition model for pedestrians using JAAD and PIE dataset.The final solution was a two-stage model where the first stage was responsible for pedestriandetection and tracking using FairMOT model architecture followed by CNN+RNN based networkto take input as a stream of 15 frames and give the required intent and two activities namelyperson standing/walking and looking/not-looking at the ego vehicle. This two-stage model wasdeployed on Nvidia Xavier using TensorRT and achieved 10 FPS with an accuracy of ~80 percent.

### Aerial imagery feature extraction using image processing for Network Rail at Atkins:

In this project, I extracted information from geo-tagged TIFF files by differencing the Digital TerrainModel (DTM) of two years to find the land use change between these years. This differenced file wasthen used to find any depression(<-1 m) occurring within 100 metres of a land elevation(> 1 m) that cancause an accident on the nearby tracks. Blob detection used segment depression and elevation in thedifferenced TIFF along with k-means clustering to remove the noise. Distance was calculatedbetween these elevation and depression blobs and then thresholded for anything lying under 100m.The code was written in PySpark on Databricks to enable distributed processing. Was awarded withThe Institute of Asset Management Innovation Award SE: Python, OpenCV, GDAL, PDAL, Databricks,Pyspark, Azure.

### Lineside feature detection for Network Rail using RGB-D data(Atkins):

This was an instance segmentation problem to detect and classify objects(gantries, cantilevers andponds) from aerial imagery. The size of each image being huge(12500x12500) and resizing would meana loss of pixel information, I broke it down into sections of 1024x1024. I also extracted a Digital Surface(DSM) at .2 m spatial resolution of these sections using inverse weighted distance method forinterpolation on sliced LiDAR data and added it as a 4th chanel to the RGB image(at 0.04 spatialresolution) by resizing the DSM to the size of image . This 4-channel image was used as an input totrain a Mask-RCNN network. Also, due to the huge size of ponds some sections were completelycovered with water so I detected coastline instead of water that made the training more sensible. SE:PDAL, GDAL, python, Keras, tensorflow, numpy, Azure

### Point Cloud Classification on Railway assets(Atkins):

Here, the aim was to perform semantic segmentation on the incoming Point cloud data taken from aLiDAR sensor fixed in the front of a train. The Objects here varied in sizes, for e.g. from Platforms to aSignal Post. Also, Due to unavailability of training data, the annotation was done in-house with a teamthat specializes on Point Cloud Classification. Annotation was expedited using a pre-classified outputgenerated from a model(Point-Voxel CNN) trained on a small amount of data. The final accuracyachieved was 94% with IOU of 0.67. SE: Pytorch, PDAL, GDAL, Azure