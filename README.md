# SwinResNeSt

### Clone this repo and first install the requirements using 
```pip install -r requirements.txt```

## Training
```python train.py ```
## Testing
```python test.py ```

- You can go to https://challenge.isic-archive.com/data/#2017 to acquire the ISIC-2017 dataset.
- Datasets to experiment on
    - ISIC2016
    - ISIC2017
    - ISIC2018
    - ISIC2019
    - ISIC2020
    - PH2
    - HAM10000
    - ### We can add other datasets for extra experiments later

* [Get pre-trained model in this link] (https://drive.google.com/drive/folders/1UC3XOoezeum0uck4KBVGa8osahs6rKUY?usp=sharing): Put pretrained weight into folder "pretrained/" and create dir 'chechpoint','test_log' in the root path.

- Download the csv for ISIC2017 on this link https://drive.google.com/drive/folders/19NVwsyOEqOOLocrF_VBr3YWXlaRBg4DV?usp=sharing

_Rest of the CSV files has to made as well. You can use a simple python pandas script to list all the image names in the CSV format provided at the end of this readme file._


## Dataset Structure
```
dataset/
    ISIC2017/
        csv/
            train.csv
            test.csv
            val.csv
        ImageTr/
            ISIC_0010858.jpg
            ISIC_0000519.jpg
            ...
        ImageTs/
            ...
        ImageVal/
            ...
        LabelTr/
            ISIC_0010858_segmentation.jpg
            ISIC_0000519_segmentation.jpg
            ...
        LabelTs/
            ...
        LabelVal/
            ...
    ISIC2016/
        ...
    ISIC2019/
        ...
    ...
    ...

```

### NOTE:
Whichever dataset you want to train, rename the dataset_name variable in train.py and test.py accordingly.
This way we can also make an experiment table on domain adaptation (i.e. training on one dataset and testing on another - this experiments we can review later on)

## CSV files
The .csv files in the dataset will contain all the image names in the below format:
| image_name | 
|:-----|
|ISIC_0010858.jpg|
|ISIC_0000519.jpg|
|ISIC_0002948.jpg|
|ISIC_0013249.jpg|
|ISIC_0000490.jpg|
|...|

All the csv files should be in the same format and the image name should be corresponding to the sets. The train.csv will have names of all the images in the training set similarly for val and test as well.