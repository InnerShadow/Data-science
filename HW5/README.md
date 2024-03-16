# HW5

## [**1. Train on base dataset**](/HW5/README.md#we-need-to-train-the-yolov5-model-on-the-standard-dataset-coco128-as-well-as-to-check-the-performance-of-the-trained-model)

## 

## We need to train the yolov5 model on the standard dataset coco128 as well as to check the performance of the trained model.

### Setup

In order to work correctly with yolov5, let's create a virtual environment in python, clone the repository from yolov5, and install the necessary dependencies. To do this use [script](/HW5/setup.sh):

```bash
bash setup.sh
```

### Data investigation

Investigae coco128 datast. We get:

45 0.479492 0.688771 0.955609 0.5955   

The first column is the class label, the second column is the normalized x-coordinate of the top left corner, the third column is the normalized y-coordinate of the top left corner, the fourth column is the normalized width, and the fifth column is the normalized height.


### Model fitting

I will train yolov5 small version, get 2 images for each batch, set 64 epochs and confidence for object recognize in 0.25 and run *train.py* modul. To fit model use [script](/HW5/coco_train.sh): 

```bash
bash coco_train.sh
```

Best mAP_0.5 is 0.866.

I will test model on Sherlock video fragment. First of all we need grab this video from dropbox(script will do itself) and run *detect.py* modul with coefficients of model that we train in *coco_train.sh* script. To test model use [script](/HW5/coco_test.sh):

```bash
bash coco_test.sh
```

### Results

Model metrics on each epoch we can see [here](/HW5/Coco/coco_resualts.md).

#### Show low FPS gif fragment:
![](/HW5/Coco/video_res_gif.gif) 

#### The full video is available [here](https://www.dropbox.com/scl/fi/4gm51wsf362phe1jnypcd/video_res.mp4?rlkey=cyrcc38k5a0ij2nkmlrnkc5r4&dl=0)

#### Test batch detections:  
![](/HW5/Coco/coco_4.jpg)
![](/HW5/Coco/coco_10.jpg)

#### Results
![](/HW5/Coco/coco_1.jpg)

#### F1-confidence curve:  
![](/HW5/Coco/coco_6.jpg)

#### Labels
![](/HW5/Coco/coco_8.jpg)

####  Confusion matrix:
![](/HW5/Coco/coco_12.jpg)

#### Precision-Recall Curve:
![](/HW5/Coco/coco_13.jpg)

#### Recall-confidance Curve
![](/HW5/Coco/coco_14.jpg)

#### Labels correlogram
![](/HW5/Coco/coco_15.jpg)