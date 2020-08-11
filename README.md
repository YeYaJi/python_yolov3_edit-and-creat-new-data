# 用yolo_v3模型批量检测图片，并生成新的数据集

***此代码只是改了yolov3中python文件夹下自带的darknet.py***

***自带的darknet.py是Python=2.\*，本项目是Python=3.7***

 **本项目就是为了扩充yolo-v3的训练集**
## 背景：
1. 有于再次得到了新的生产数据（图片），希望将上次训练的模型用新的数据进行检测。
2. 注意：新的数据只有图片，没有label………，所以也就没法算正确率啥的了。。。
3. 于是想要将新的数据加入训练集，但总不能一张一张自己标注吧，啊哈哈。
4. 于是乎就写了这个代码，目的是用旧的模型测试新的图片，把测试结果生成新的yolo数据样式（也就是准备把新图作为训练集）
5. 有了新的数据还要人工用labelimg筛查一遍，看看哪里有什么问题，比如框框有时候会比较大，咋样调整啥的直接就可以在`生成新的yolo数据样式`这一步改掉。
6. 人工检测之后，确保数据比较不错了就扔进去当训练集好了

## 一、前期准备
1. 已经有训练好的模型了--假设是`yolov3-tiny_100.weights`
2. 下载好darknet了，没下好的点[这里](https://github.com/pjreddie/darknet.git)去下
3. 测试图片集（只有图）

## 二、文件说明
1. `yolo_text_batch.py`文件是用来   `检测->生成新的数据集`
2. `yolo_text_batch_for_dibang.py`文件是专门为地磅项目做的，这个就是根据上一步的检测结果，适当调整新生成的数据集（这里的调整只针对地磅项目）（数字下移点的定框高度，数据集生成）
3. `darknet.py`yolo自带的，在Darknet/Python文件夹下，只能python2才能运行。


## 三、操作步骤
1. clone此项目
2. 参数设置 


	1.`cfg_path`="/XXX.cfg"---因为是做测试，所以一定要把`.cfg`改成**Testing**模式

   	2.`weight_path`="XXX.weights"--训练好的权重

   	3.`voc_data_path`="voc.data"--这里面的数据保持训练时就行，主要就是用个`classes`

   	4.`image_path`="文件夹"

   	5.`save_txt_path`="文件夹"


3. 参数设置好后运行就行了
4. 运行完了之后用labelimage看看结果咋样，有错的自己改改，当然也可以写程序批量改
5. 修改好了就可以作为新的数据集了，啊哈哈。 
