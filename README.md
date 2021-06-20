# Object-detection-and-classification-using-ROS
Detected object Meassage
-  deep-object-detection/Object[] objects Detected objects
-  string observation-path The observation path
  Object message
-  Header header
-  string label # label of the object
-  uint32 x # x coordinate of the anchor position of bounding box
-  uint32 y # y coordinate of the anchor position of bounding box
-  uint32 width # width of the bounding box
-  uint32 height # height of the bounding box
-  uint32 imageID # the id of the image that the object belongs to
-  float32 con dence # the con dence value of the neural net

Use the download-models.sh script, to download the Caffe model files.
You can run the node using the command: rosrun deep-object-detection/object-detection.py

By default the node will run in CPU mode. In order to run on the GPU, you should set the gpu flag as - gpu GPU-ID where GPU-ID is the id of the GPU that you want to use which is usually 0.

  By default VGG16 network will be used but you can also use the ZF network using -net zf or the  ne-tuned 3-class KTH model using -net vgg16KTH.
 
 For using the RFCN models, you should use - net ResNet-50 or -net
ResNet-101 commands.


There are 2 services advertised by this node:
  /deep-object-detection/get-labels This service will return you the list of
object labels that can be recognized. There are 20 labels.
  /deep-object-detection/detect-objects This service will return the detected
objects as a vector of images. The bounding box, label and con dence
information of each detected object is returned.