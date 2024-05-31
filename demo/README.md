# 期中作业-任务2：在VOC数据集上训练并测试目标检测模型Faster R-CNN和YOLO V3


## 环境配置
以下为项目所运行的环境：
```{bash}
python==3.8.10
torch==1.13.1+cu116
torchvision==0.14.1+cu116
pandas==2.0.2
matplotlib==3.7.1
tensorboard==2.13.0
```
## 数据准备

下载 [PASCAL VOC2007](http://host.robots.ox.ac.uk/pascal/VOC/voc2007/) 数据集和 [PASCAL VOC2012](http://host.robots.ox.ac.uk/pascal/VOC/voc2012/index.html) 数据集并解压到指定目录，本项目为`\ht-tmp\datasets\`。


## 模型训练
运行一下命令训练 Faster R-CNN 模型：
```{python}
python tools/train.py configs/pascal_voc/faster-rcnn_r50_fpn_1x_voc0712.py
```
运行一下命令训练 YOLOv3 模型：
```{python}
python tools/train.py configs/yolo/yolov3_d53_8xb8-ms-608-273e_coco_v3.py
```
## 权重下载
不同实验设置的最优模型的权重下载链接：https://pan.baidu.com/s/1DiMEfCJ4XldSBEWcruLxXA?pwd=dzry。
权重`best_coco_bbox_mAP_epoch_36.pth`放于`work_dirs/yolov3_d53_8xb8-ms-608-273e_coco_v3/`目录下。
权重`best_pascal_voc_mAP_epoch_4.pth`放于`work_dirs/faster-rcnn_r50_fpn_1x_voc0712/`目录下。

## 测试图像
相关代码和说明见`demo/main.ipynb`。