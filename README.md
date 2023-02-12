# 简介

本项目基于pytorch+python3.10 实现比较简单用于深度学习入门

由yolov5-face实现人脸检测，resnet+arcface实现人脸识别。

项目中不包含训练代码只有检测代码,yolov5s-face，yolov5m-face和arcface权重文件放在release中



# 运行

第一步是要先生成人物的特征

```
python gen_features.py 
```

- **--source**	指定要生成人物特征的照片目录，一般是文件名对应这个特征的标签，比如xxx.jpg的标签就是xxx
- **--yolo_weight**    指定已经训练好的yolo权重
- **--arcface_weight**    指定已经训练好的resnet+arcface权重
- **--out_dir**    指定人物特征的输出目录，可以理解为人物特征数据库



生成完特征就可以根据已有的特征去识别人物了

```
python detect.py 
```

- **--source**    指定要检测的目录，值为0时打开摄像头检测
- **--yolo_weight**    指定已经训练好的yolo权重（放在release中）
- **--arcface_weight**    指定已经训练好的resnet+arcface权重

- **--person_dir**    指定已生成的人物特征的目录
- **--view-img**    开启摄像头要启用这个参数，显示图片

