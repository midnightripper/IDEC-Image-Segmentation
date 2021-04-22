# IDEC Image Segmentation

Advanced Image Processing Lecture based on Deep Learning in **한국과학기술원 반도체설계교육센터 [(KAIST IDEC)](https://www.idec.or.kr/)**

**Pneumonia Classification and Pet Data Image Segmentation with U-Net**
<br>In 2021 Advanced Image Processing Lecture with KAIST IDEC

## DataSet

- Pet Data - 1190 Images (Ragdoll, saint_bernard, scottish_terrier, Siamese, staffordshire_bull_terrier, yorkshire_terrier)<br>
**[University of OXFORD : Open Dataset]**<br>
(https://www.robots.ox.ac.uk/~vgg/data/pets/data/images.tar.gz)
(https://www.robots.ox.ac.uk/~vgg/data/pets/data/annotations.tar.gz)

- Pneumonia Data - 1200 Images (Normal, Pneumonia)<br>
**[[Identifying Medical Diagnoses and Treatable Diseases by Image-Based : Open Dataset]](https://www.cell.com/cell/fulltext/S0092-8674(18)30154-5)**
(http://download.tensorflow.org/data/ChestXRay2017/train/images.tfrec)
(http://download.tensorflow.org/data/ChestXRay2017/train/paths.tfrec)

## Application

| Model | Loss Function | Optimizer | Epoch | Total Loss | Accuracy<br>(Classification)<br>(=F1-Score) | Dataset | Result | 
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| U-Net | Sparse Categorical Crossentropy | RMSProp | 200 | 0.0269<br>(Train) | . | Pet Data | [Result_01](#Result_01)<br>**(Segmentation)** |
| U-Net | Sparse Categorical Crossentropy | RMSProp | 1000 | 0.0041<br>(Train) | . | Pet Data | [Result_02](#Result_02)<br>**(Segmentation)** |
| U-Net<br>Leaky ReLU | Sparse Categorical Crossentropy | RMSProp | 1000 | 0.0048<br>(Train) | . | Pet Data | [Result_03](#Result_03)<br>**(Segmentation)** |
| FCN | Binary Crossentropy | Adam | 200 | 1.0335<br>**(Test)**  | ***0.8650***<br>**(Test)** | Pneumonia Data | [Result_04](https://github.com/gh-BumsooKim/IDEC-Image-Segmentation/blob/main/05-TrainPneumoniaFCN.ipynb)<br>**(Classification)** |
| FCN | MSE | Adam | 200 | ***0.1464***<br>**(Test)**  | 0.8500<br>**(Test)** | Pneumonia Data | [Result_05](https://github.com/gh-BumsooKim/IDEC-Image-Segmentation/blob/main/11-TrainPneumoniaFCN-MSE.ipynb)<br>**(Classification)** |
| FCN | Binary Crossentropy | Nadam | 200 | 1.6821<br>**(Test)**  | 0.7500<br>**(Test)** | Pneumonia Data | [Result_06](https://github.com/gh-BumsooKim/IDEC-Image-Segmentation/blob/main/12-TrainPneumoniaFCN-Nadam.ipynb)<br>**(Classification)** |
| FCN | Binary Crossentropy | AdaDelta | 200 | 0.3628<br>**(Test)**  | 0.8600<br>**(Test)** | Pneumonia Data | [Result_06](https://github.com/gh-BumsooKim/IDEC-Image-Segmentation/blob/main/13-TrainPneumoniaFCN-AdaDelta.ipynb)<br>**(Classification)** |


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

## Sample Dataset

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

## Reference
https://keras.io/examples/vision/
