ssd-mobilenet-v1 model (Caffe)
=====

This folder contains a specific version of the [Caffe mobilenet v1 SSD model](https://github.com/chuanqi305/MobileNet-SSD) deployment configurations.

Introduction
---
You can download pre-trained caffe model from [Caffe mobilenet v1 SSD model](https://github.com/chuanqi305/MobileNet-SSD). In order to facilitate model optimization, we use the node "mbox_loc", "mbox_conf_flatten", "mbox_priorbox" as output. For the detection output layer, you can refer to [detection_output.cc](https://github.com/XiaoMi/mace/blob/master/mace/utils/detection_output.cc).
