# 用yolo_v3模型批量检测图片，并生成新的数据集
*** 此代码只是改了yolov3中python文件夹下自带的darknet.py***

***自带的darknet.py是Python=2.\*，本项目是Python=3.7***
## 一、前期准备
1. 已经有训练好的模型了--假设是`yolov3-tiny_100.weights`
2. 下载好darknet了，没下好的点[这里](https://github.com/pjreddie/darknet.git)去下
3. 测试图片集

## 二、文件说明
1. `yolo_text_batch.py`文件是本项目的主文件，下面的操作步骤基于此文件
2. `yolo_text_batch_for_dibang.py`文件是专门为地磅项目做的（数字下移点的定框高度，数据集生成）`对自己有用，别人没用`
3. `darknet.py`yolo自带的，在Darknet/Python文件夹下


## 三、操作步骤
1. clone此项目
2. 参数设置 

	1.`cfg_path`="/XXX.cfg"---因为是做测试，所以一定要把`.cfg`改成**Testing**模式

    	2.`weight_path`="XXX.weights"--训练好的权重

    	3.`voc_data_path`="voc.data"--这里面的数据保持训练时就行，主要就是用个`classes`

    	4.`image_path`="文件夹"

    	5.`save_txt_path`="文件夹"

3. ran就行了 
