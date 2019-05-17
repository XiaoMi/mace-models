Kaldi models
=====

This folder contains configuration files for numbers of Kaldi nnet2 and nnet3 models which have been converted to ONNX format.

The original Kaldi models are from [here](http://kaldi-asr.org/models.html).

Introduction
---
[Kaldi](http://github.com/kaldi-asr/kaldi) is a toolkit for speech recognition, intended for use by speech recognition researchers and professionals.

MACE already supports most frequently used components in Kaldi and ONNX format models. So we converted most of the open sourced Kaldi models and put them here as examples.

We have also opensourced the [kaldi-onnx](https://github.com/XiaoMi/kaldi-onnx) converting tool.

|   Nnet2 models      | Nnet3 models |
|  ---------------         | --------- |
| [Fisher English](http://kaldi-asr.org/downloads/build/8/trunk/egs/fisher_english/s5/exp/nnet2_online/nnet_a_online/final.mdl)  | [CVTE](http://kaldi-asr.org/models/m2) |
| [Librispeech](http://kaldi-asr.org/downloads/build/10/trunk/egs/librispeech/s5/exp/nnet2_online/nnet_ms_a_online/final.mdl) |  [SRE16](http://kaldi-asr.org/models/m3) |
| [RM](http://kaldi-asr.org/downloads/build/4/trunk/egs/rm/s5/exp/nnet4c_gpu_ali/final.mdl) |[ASpIRE](http://kaldi-asr.org/models/m4)  |
| [Tedlium](http://kaldi-asr.org/downloads/build/9/trunk/egs/tedlium/s5/exp/nnet2_online/nnet_ms_sp_online/final.mdl) |[Tedlium](http://kaldi-asr.org/models/m5) |
| [Timit](http://kaldi-asr.org/downloads/build/7/trunk/egs/timit/s5/exp/tri4_nnet/final.mdl) |  [Callhome](http://kaldi-asr.org/models/m6) |
| | [VoxCeleb Models](http://kaldi-asr.org/models/m7) |
| |  [SITW Model](http://kaldi-asr.org/models/m8) |


Here we use the 'validation_inputs_data' and 'validation_outputs_data' to validate MACE's inference results.

The 'validation_outputs_data' is the result of using 'nnet2-am-compute' or 'nnet3-compute' to compute the model's propogation with input 'validation_inputs_data'.
