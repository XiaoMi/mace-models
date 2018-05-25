deeplab-v3-plus-mobilenet-v2 model
=====

This folder contains deeplab v3+ mobilenet v2 model deployment configurations.

Introduction
---
DeepLab is a state-of-art deep learning model for semantic image segmentation.[[link]](https://github.com/tensorflow/models/tree/master/research/deeplab)

The original pretrained model is [here](https://github.com/tensorflow/models/blob/master/research/deeplab/g3doc/model_zoo.md) (mobilenetv2_coco_voc_trainaug)

In order to facilitate model optimization, we use the fixed-shape node "sub_7" as input and "ResizeBilinear_2" as output.

