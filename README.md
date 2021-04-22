# IDEC Image Segmentation

Advanced Image Segmentation Lecture based on Deep Learning in **한국과학기술원 반도체설계교육센터 [(KAIST IDEC)](https://www.idec.or.kr/)**

**Pneumonia Data Image Segmentation with U-Net**
<br>In 2021 Advanced Image Segmentation Lecture with KAIST IDEC

## DataSet

- Pet Data - 1190 Images (Ragdoll, saint_bernard, scottish_terrier, Siamese, staffordshire_bull_terrier, yorkshire_terrier)<br>
**[University of OXFORD : Open Dataset]**<br>
(https://www.robots.ox.ac.uk/~vgg/data/pets/data/images.tar.gz)
(https://www.robots.ox.ac.uk/~vgg/data/pets/data/annotations.tar.gz)

- Pneumonia Data - 1200 Images (Normal, Pneumonia)<br>
**[[Identifying Medical Diagnoses and Treatable Diseases by Image-Based : Open Dataset]](https://www.cell.com/cell/fulltext/S0092-8674(18)30154-5)**
(http://download.tensorflow.org/data/ChestXRay2017/train/images.tfrec)
(http://download.tensorflow.org/data/ChestXRay2017/train/paths.tfrec)

<br>

### Sample Pet Train Raw Data (each different size)
<p align="center">
  <br>Siamese_203
  <img src="imgs/01-SampleTrainData_01.png">
<br>
  <br>yorkshire_terrier_67
  <img src="imgs/01-SampleTrainData_02.png">
</p>

<br>

### Sample Pet Train Scaling Data (160 x 160 px)
<p align="center">
  <br>Siamese_203
  <img src="imgs/01-SampleTrainData_Scale_01.png">
<br>
  <br>yorkshire_terrier_67
  <img src="imgs/01-SampleTrainData_Scale_02.png">
</p>

### Sample Pneumonia Train Scaling Data (180 x 180 px)
<p align="center">
  <br>Pneumonia
  <img src="imgs/04-SampleTrainData_Scale_01.png">
<br>

## Application

| Model | Loss Function | Optimizer | Epoch | Total Loss | Dataset | Result | 
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| U-Net | Sparse Categorical Crossentropy | RMSProp | 200 | 0.0269 | Pet Data | [Result_01](#Result_01)<br>**(Segmentation)** |
| U-Net | Sparse Categorical Crossentropy | RMSProp | 1000 | 0.0041 | Pet Data | [Result_02](#Result_02)<br>**(Segmentation)** |
| U-Net<br>Leaky ReLU | Sparse Categorical Crossentropy | RMSProp | 1000 | 0.0048 | Pet Data | [Result_03](#Result_03)<br>**(Segmentation)** |
| FCN | Binary Crossentropy | Adam | 200 | | Pneumonia Data | [Result_03](#Result_03)<br>**(Classification)** |

<br>

#### Result_01
<p>
  <img src="imgs/02-Predict_01.png">
</p>

#### Result_02
<p>
  <img src="imgs/03-Predict_01.png">
</p>

#### Result_03
<p>
  <img src="imgs/10-Predict_01.png">
</p>

## Reference
https://keras.io/examples/vision/
