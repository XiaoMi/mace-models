Mobilenet V1 model
=====

This folder contains Mobilenet v1 MACE model deployment configurations.

Introduction
---
The original pretrained model is [here](https://github.com/tensorflow/models/tree/master/research/slim#pre-trained-models) (MobileNet_v1_1.0_224)

The quantization-aware trained model is [here](https://github.com/tensorflow/models/blob/master/research/slim/nets/mobilenet_v1.md) (MobileNet_v1_1.0_224_quant)

The quantization-friendly trained model is trained by XiaoMi internally according to [here](https://arxiv.org/abs/1803.08607), with enhanced post-quantization for activations. The accuracy is 70.20% which is similar with fp32 model.
