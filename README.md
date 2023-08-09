# Prior Guided 3D Medical Image Landmark Localization

## News
- We will update the repository as soon as possible

## Introduction 
This is the official code of Prior Guided 3D Medical Image Landmark Localization 

In this study, we present a prior guided coarse-to-fine framework for efficient and accurate 3D medical landmark detection; We utilize prior knowledge that in specific settings, physicians annotate multiple landmarks on the same slice. 

The coarse stage uses coordinate regression on downsampled 3D images to maintain the structural relationships across different landmarks. 

The fine stage categorizes landmarks as independent and correlated landmarks based on their annotation prior. For independent landmarks, we train multiple models to capture local features and ensure reliable local predictions. For correlated landmarks, we mimic the manual annotation process and propose a correlated landmark detection model that merges information from various patches to query key slices and identify correlated landmarks.

Our method is extensively evaluated on two datasets, exhibiting superior performance with an average detection error of 3.29 mm and 2.13 mm, respectively.

<div align=center>

![](images/hrnet.jpg)



#### Install
1. Install PyTorch 1.13 following the [official instructions](https://pytorch.org/)
2. Install dependencies
````bash

pip install -r requirements.txt
````
3. Clone the project
````bash 
git clone https://github.com/pang-yi-jie/MIDL2023_landmark.git
````



#### Data

1. You need to download the annotations files and images from PDDCA

Your `data` directory should look like this:

````
-- data
   |-- PDDCA
   |   |--images
   |   |   |-- head1.nii
   |   |   |-- head2.nii
   |   |-- setup
   |   |   |-- landmark.csv
   |   |   |-- cv0
   |   |   |-- cv1
   |   |   |-- cv2
   |--prostate
   |   |--images
   |   |   |--prostate1.nii
   |   |   |--prostate2.nii
   |   |-- setup
   |   |   |-- landmark.csv

````

#### Train
Please download our three-fold cross-validation division.
````bash
python tools/train_PCCDA.py
# example:
python tools/train_prostate.py
````

#### Test
````bash
python tools/test_PCCDA.py
# example:
python tools/test_prostate.py
````



## Citation
If you find this work or code is helpful in your research, please cite:
````
@inproceedings{cheng2023prior,
  title={Prior Guided 3D Medical Image Landmark Localization},
  author={Cheng, Pujin and Lyu, Junyan and Tang, Xiaoying and others},
  booktitle={Medical Imaging with Deep Learning},
  year={2023}
}
````

## Reference
[1] Deep High-Resolution Representation Learning for Visual Recognition. Jingdong Wang, Ke Sun, Tianheng Cheng, 
    Borui Jiang, Chaorui Deng, Yang Zhao, Dong Liu, Yadong Mu, Mingkui Tan, Xinggang Wang, Wenyu Liu, Bin Xiao. Accepted by TPAMI.  [download](https://arxiv.org/pdf/1908.07919.pdf)

