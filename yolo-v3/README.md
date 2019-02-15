YOLOv3 model
=====

This folder contains Yolov3 model deployment configurations.

Introduction
---
The original model is [here](https://github.com/pjreddie/darknet/blob/master/cfg/yolov3.cfg) and we converted it to the tensorflow version. In order to facilitate model optimization, we use the node "conv2d_59/BiasAdd:0", "conv2d_67/BiasAdd:0", "conv2d_75/BiasAdd:0" as output.
