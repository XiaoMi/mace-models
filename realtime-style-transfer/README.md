realtime style transfer
=====

This folder contains realtime style transfer examples and benchmark results on Qualcomm Snapdragon 821 and 845.

Introduction
---
This realtime style tranfer model was compressed and optimized from [here](https://github.com/lengstrom/fast-style-transfer) (fast style transfer project). 

Compared to the original fast style transfer:

- realtime: 10x faster .
- tiny(90kB): 98% model size compression from fast style transfer(6.7MB).
- easier to deploy: support variable input size.

And we used a step-traning method to train this model with different params in different step. We have put the step-training code [here](https://github.com/lengstrom/fast-style-transfer/pull/175)(step-training).


Benchmark:
---
The following is the realtime style transfer running latency on Mi5S (Snapdragon 821) and MIX2s (Snapdragon 845), using GPU runtime.
 
| Resolution  | 821 (ms) | 845 (ms)|
| :--------: | :----------: | :------------: |
| 480x640   | 53.733    | 32.559      |
| 720x1280   | 161.380  | 96.855      |
| 960x1280   | 214.966  | 128.729     |
| 1080x1920  | 362.927  | 223.070     |




## Examples:

Compared with [fast style transfer](https://github.com/lengstrom/fast-style-transfer) .


Content image:
<div  align="center">
<img src="imgs/inputs/chicago.jpg" width = "320" height = "240" alt="chicago" />
</div>

Styles and results:

| style | fast style transfer | realtime style transfer |
| :---: | :----: | :----: |
|<img src="imgs/styles/la_muse.jpg" height="240" >  | <img src="imgs/tf-results/chicago_la_muse.jpg"> | ![](imgs/results/la_muse/chicago.jpg)|
|<img src="imgs/styles/wave.jpg" height="240" >  | ![](imgs/tf-results/chicago_wave.jpg)| ![](imgs/results/wave/chicago.jpg)  |
| <img src="imgs/styles/the_scream.jpg" height="240" >  | ![](imgs/tf-results/chicago_scream.jpg)|  ![](imgs/results/scream/chicago.jpg)  |
| <img src="imgs/styles/udnie.jpg" height="240" > | ![](imgs/tf-results/chicago_udnie.jpg)|  ![](imgs/results/udnie/chicago.jpg)  |


## Other examples 

 | input | femme| udnie | wave | wreck | la_muse | scream |
 | :---:  | :---:  | :---: | :---: | :---: | :---: | :---: |
 | style  | <img src="imgs/styles/femme.jpg" width="320"> | <img src="imgs/styles/udnie.jpg" width="320"> | <img src="imgs/styles/wave.jpg" width="320"> | <img src="imgs/styles/the_shipwreck_of_the_minotaur.jpg" width="320"> | <img src="imgs/styles/la_muse.jpg" width="320"> | <img src="imgs/styles/the_scream.jpg" width="320"> |
| ![](imgs/inputs/areuok.jpg)  | ![](imgs/results/femme/areuok.jpg) | ![](imgs/results/udnie/areuok.jpg) | ![](imgs/results/wave/areuok.jpg) | ![](imgs/results/wreck/areuok.jpg) | ![](imgs/results/la_muse/areuok.jpg) | ![](imgs/results/scream/areuok.jpg) |
|  ![](imgs/inputs/model1.jpg) |  ![](imgs/results/femme/girl1.jpg) |![](imgs/results/udnie/girl1.jpg) |![](imgs/results/wave/girl1.jpg) |![](imgs/results/wreck/girl1.jpg) |![](imgs/results/la_muse/girl1.jpg) |![](imgs/results/scream/girl1.jpg) |
|  ![](imgs/inputs/model2.jpg)| ![](imgs/results/femme/girl2.jpg) | ![](imgs/results/udnie/girl2.jpg) | ![](imgs/results/wave/girl2.jpg) | ![](imgs/results/wreck/girl2.jpg) | ![](imgs/results/la_muse/girl2.jpg) | ![](imgs/results/scream/girl2.jpg) | 
|  ![](imgs/inputs/Louvre.jpg)| ![](imgs/results/femme/Louvre.jpg)  | ![](imgs/results/udnie/Louvre.jpg)  | ![](imgs/results/wave/Louvre.jpg)  | ![](imgs/results/wreck/Louvre.jpg)  | ![](imgs/results/la_muse/Louvre.jpg)  | ![](imgs/results/scream/Louvre.jpg)  |
|  ![](imgs/inputs/mi-office.jpg)| ![](imgs/results/femme/mi-office.jpg)  | ![](imgs/results/udnie/mi-office.jpg)  | ![](imgs/results/wave/mi-office.jpg)  | ![](imgs/results/wreck/mi-office.jpg)  | ![](imgs/results/la_muse/mi-office.jpg)  | ![](imgs/results/scream/mi-office.jpg)  |

<!--
 | input | femme| udnie | wave | wreck | la_muse | scream |
 | :---:  | :---:  | :---: | :---: | :---: | :---: |
 |input  | ![](inputs/areuok.jpg) |   ![](inputs/model1.jpg) | ![](inputs/model2.jpg) |   ![](inputs/Louvre.jpg) |   ![](inputs/mi-office.jpg) |
 | <img src="styles/femme.jpg" width="320" >  | ![](results/femme/areuok.jpg) |  ![](results/femme/girl1.jpg) |![](results/femme/girl2.jpg) |![](results/femme/Louvre.jpg)  |![](results/femme/mi-office.jpg)  | 
 |<img src="styles/udnie.jpg" width="320" > | ![](results/udnie/areuok.jpg) |![](results/udnie/girl1.jpg) | ![](results/udnie/girl2.jpg) | ![](results/udnie/Louvre.jpg)  |![](results/udnie/mi-office.jpg)  |
 | <img src="styles/wave.jpg" width="320" > | ![](results/wave/areuok.jpg) |![](results/wave/girl1.jpg) |![](results/wave/girl2.jpg) |![](results/wave/Louvre.jpg)  |  ![](results/wave/mi-office.jpg)  |
 |<img src="styles/the_shipwreck_of_the_minotaur.jpg" width="320"> | ![](results/wreck/areuok.jpg) |![](results/wreck/girl1.jpg) |![](results/wreck/girl2.jpg) |  ![](results/wreck/Louvre.jpg)  |  ![](results/wreck/mi-office.jpg) |
 |<img src="styles/la_muse.jpg" width="320" > | ![](results/la_muse/areuok.jpg) | ![](results/la_muse/girl1.jpg) |  ![](results/la_muse/girl2.jpg) | ![](results/la_muse/Louvre.jpg)  |![](results/la_muse/mi-office.jpg)  | 
 | <img src="styles/the_scream.jpg" width="320" >|![](results/scream/areuok.jpg) |![](results/scream/girl1.jpg) |![](results/scream/girl2.jpg) | ![](results/scream/Louvre.jpg)  |![](results/scream/mi-office.jpg)  |

-->
<!--

  Udnie Style:
  <div  align="center">
  <img src="styles/udnie.jpg" width = "256" height = "256" alt="udnie" />
  </div>

 | input | output| 
 | :---:  | :---:  |
| ![areuok](inputs/areuok.jpg)  | ![](results/udnie/areuok.jpg)|
|  ![](inputs/model1.jpg) |  ![](results/udnie/girl1.jpg) |
|  ![](inputs/model2.jpg)| ![](results/udnie/girl2.jpg) |
|  ![](inputs/Louvre.jpg)| ![](results/udnie/Louvre.jpg)  |
|  ![](inputs/mi-office.jpg)| ![](results/udnie/mi-office.jpg)  |


Shipwreck Style:
<div  align="center">
<img src="styles/the_shipwreck_of_the_minotaur.jpg" width = "256" height = "256" alt="wreck" />
</div>

 | input | output| 
 | :---:  | :---:  |
| ![areuok](inputs/areuok.jpg)  | ![](results/wreck/areuok.jpg)|
|  ![](inputs/model1.jpg) |  ![](results/wreck/girl1.jpg) |
|  ![](inputs/model2.jpg)| ![](results/wreck/girl2.jpg) |
|  ![](inputs/Louvre.jpg)| ![](results/wreck/Louvre.jpg)  |
|  ![](inputs/mi-office.jpg)| ![](results/wreck/mi-office.jpg)  |


Wave Style:
<div  align="center">
<img src="styles/wave.jpg" width = "464" height = "257" alt="wave" />
</div>

 | input | output| 
 | :---:  | :---:  |
| ![areuok](inputs/areuok.jpg)  | ![](results/wave/areuok.jpg)|
|  ![](inputs/model1.jpg) |  ![](results/wave/girl1.jpg) |
|  ![](inputs/model2.jpg)| ![](results/wave/girl2.jpg) |
|  ![](inputs/Louvre.jpg)| ![](results/wave/Louvre.jpg)  |
|  ![](inputs/mi-office.jpg)| ![](results/wave/mi-office.jpg)  |


la muse Style:
<div  align="center">
<img src="styles/la_muse.jpg" width = "256" height = "256" alt="wave" />
</div>

 | input | output| 
 | :---:  | :---:  |
| ![areuok](inputs/areuok.jpg)  | ![](results/la_muse/areuok.jpg)|
|  ![](inputs/model1.jpg) |  ![](results/la_muse/girl1.jpg) |
|  ![](inputs/model2.jpg)| ![](results/la_muse/girl2.jpg) |
|  ![](inputs/Louvre.jpg)| ![](results/la_muse/Louvre.jpg)  |
|  ![](inputs/mi-office.jpg)| ![](results/la_muse/mi-office.jpg)  |


Scream Style:
<div  align="center">
<img src="styles/the_scream.jpg" width = "256" height = "256" alt="scream" />
</div>

 | input | output| 
 | :---:  | :---:  |
| ![areuok](inputs/areuok.jpg)  | ![](results/scream/areuok.jpg)|
|  ![](inputs/model1.jpg) |  ![](results/scream/girl1.jpg) |
|  ![](inputs/model2.jpg)| ![](results/scream/girl2.jpg) |
|  ![](inputs/Louvre.jpg)| ![](results/scream/Louvre.jpg)  |
|  ![](inputs/mi-office.jpg)| ![](results/scream/mi-office.jpg)  |
-->
