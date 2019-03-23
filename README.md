# To reproduce some important object detection experiment.

## To do list:
### Two stages:
| backbone | name | FPN | cascade | tricks | AP50:90 |
| :--- | :----: | :---: | :---: | :----: | :----: | 
| res50| Faster RCNN  | ✔ |   |   |  35.5 | 
| res50| Faster RCNN  | ✔ | ✔ |   |  40.5 |	
| res101| Faster RCNN | ✔ |   |   |       |
| res101| Faster RCNN | ✔ | ✔ |	  |       |

### One stage:
| backbone | name | tricks |AP50:90 |
| :--- | :----: | :---: | :---: | 
| res50  | RetinaNet |  |	35.6 |
| res101 | RetinaNet |  |   37.6 |
| VGG16  | SSD300    |  |	25.4 | 
| VGG16  | SSD512    |  |   29.5 |

### proposal
| backbone | name | tricks | AR100 | AR300 | AR1000 |
| :--- | :----: | :---: | :---: |:---: |:---: |
| res50  | RPN  |  | 0.4282 | 0.5144 | 0.5725 |
| res101  | RPN |  |        |        |        |


***
### 1. Faster RCNN(FPN)
| backbone | our AP 0.50:0.95(mmdetection) | training time |
| :--- | :----: | ---: |
| ResNet50 | 35.5(36.4) | 26h (4 titanxp , distributed) | 
| ResNet101 |  |
#### ResNet50
![faster_rcnn_r50](imgs/faster_rcnn_r50.png)

***

### 2. Cascade-RCNN(FPN)

| backbone | AP 0.50:0.95 | training time |
| :--- | :----: | ---: |
| ResNet50 | 40.5(40.3) | 34h (8 titanxp , nondistributed) |
| ResNet101 |  
|
#### ResNet50
![cascade_rcnn_r50](imgs/cascade_rcnn_r50.png)

***

### 3. RetinaNet
| backbone | AP 0.50:0.95 | training time |
| :--- | :----: | ---: |
| ResNet50 | 35.6(35.8)  | 25h(4 titanxp , distributed) |
| ResNet101 |  37.6(37.7)| 33h(4 titanxp , distributed) |
#### ResNet50
![retinaNet_r50](imgs/retinaNet_r50.png)

#### ResNet101
![retinaNet_r101](imgs/retinaNet_r101.png)

***

### 4. SSD
| image size | AP 0.50:0.95 | training time |
| :--- | :----: | ---: |
| 300 | 25.4(25.7)  | 71h(4 titanxp, distributed, 24epoch) |
| 512 | 29.5(29.3)  | 73h(4 titanxp, distributed, 24epoch) |
#### SSD300
![ssd300](imgs/ssd300.png)
#### SSD512
![ssd300](imgs/ssd512.png)