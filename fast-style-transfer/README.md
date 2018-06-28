fast style transfer model
=====

This folder contains fast style transfer MACE model deployment configurations.

Introduction
---
The original pretrained model is [here](https://github.com/lengstrom/fast-style-transfer) (fast style transfer project).

## Samples:

Content image:
<div  align="center">
<img src="imgs/content/chicago.jpg" width = "320" height = "240" alt="chicago" />
</div>

Styles and results:

| style | tensorflow results | mace results |
| :---: | :----: | :----: |
| ![la_muse](imgs/style/la_muse.jpg) | ![](imgs/tf-results/chicago_la_muse.jpg)|  ![](imgs/mace-results/chicago_la_muse.jpg)  |
| ![rain_princess](imgs/style/rain_princess.jpg) | ![](imgs/tf-results/chicago_rain_princess.jpg)|  ![](imgs/mace-results/chicago_rain_princess.jpg)  |
| ![scream](imgs/style/the_scream.jpg) | ![](imgs/tf-results/chicago_scream.jpg)|  ![](imgs/mace-results/chicago_scream.jpg)  |
| ![udnie](imgs/style/udnie.jpg) | ![](imgs/tf-results/chicago_udnie.jpg)|  ![](imgs/mace-results/chicago_udnie.jpg)  |
