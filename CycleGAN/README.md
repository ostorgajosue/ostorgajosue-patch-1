# CycleGAN
CycleGAN uses a cycle consistency loss to enable training without the need for paired data. In other words, it can translate from one domain to another without a one-to-one mapping between the source and target domain.
This opens up the possibility to do a lot of interesting tasks like photo-enhancement, image colorization, style transfer, etc. All you need is the source and the target dataset.

CycleGAN使用循环一致性损失函数来实现训练，而无需配对数据。换句话说，它可以从一个域转换到另一个域，而无需在源域和目标域之间进行一对一映射。
这开启了执行许多有趣任务的可能性，例如照片增强，图像着色，样式传输等。您只需要源和目标数据集。

Here, the CycleGAN neural network model is used to realize the four functions of photo style conversion, photo effect enhancement, landscape season change, and object conversion.

这儿，使用CycleGAN神经网络模型实现照片风格转换、照片效果增强、照片中风景季节变换、物体转换四大功能。

## 摘要 Abstract
> paper [Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks](https://arxiv.org/abs/1703.10593)
Image-to-image translation is a class of vision and graphics problems where the goal is to learn the mapping between an input image and an output image using a training set of aligned image pairs. However, for many tasks, paired training data will not be available. We present an approach for learning to translate an image from a source domain X to a target domain Y in the absence of paired examples. Our goal is to learn a mapping G: X → Y such that the distribution of images from G(X) is indistinguishable from the distribution Y using an adversarial loss. Because this mapping is highly under-constrained, we couple it with an inverse mapping F: Y → X and introduce a cycle consistency loss to push F(G(X)) ≈ X (and vice versa). Qualitative results are presented on several tasks where paired training data does not exist, including collection style transfer, object transfiguration, season transfer, photo enhancement, etc. Quantitative comparisons against several prior methods demonstrate the superiority of our approach.


## 代码用法 Code usage

The tasks that have already processed the data are as follows. For specific data content and experimental results, see the Task Name chapter.

已经处理好数据的任务如下，具体数据内容和实验效果见Task Name章节。

```
cycle_gan_dataset_name_list = ["apple2orange", "summer2winter_yosemite", "horse2zebra", "monet2photo",
                               "cezanne2photo", "ukiyoe2photo", "vangogh2photo", "maps",
                               "cityscapes", "facades", "iphone2dslr_flower", ]
```

### 0. Require

+ python 3+
+ tensorflow version 2


### 1. Train Model

```python
python train_image2text_model.py task_name
```


### 2. Model Inference

```python
python inference_by_image2text_model.py task_name
```


## 任务名称 Task Name

You can use the following task_name parameters directly, or you can define new tasks yourself.

可以直接选用以下task_name参数，也可以自行定义新的任务。

You can use the ```python cyclegan_model.py``` command to view the data requirements required by the model.


### 照片风格转换   Style Transfer

|任务名称|task_name|
|-|-|
|莫奈风格2照片|  monet2photo|
|梵高风格2照片|  vangogh2photo|
|塞尚风格2照片|  cezanne2photo|
|浮世绘风格2照片|  ukiyoe2photo|

![](https://junyanz.github.io/CycleGAN/images/photo2painting.jpg)


### 照片效果增强：虚化背景  Photo Enhancement: Narrow depth of field

|任务名称|task_name|
|-|-|
|智能手机效果2单反相机| iphone2dslr_flower|

![](https://junyanz.github.io/CycleGAN/images/photo_enhancement.jpg)


### 照片风景季节变换 Season Transfer

|任务名称|task_name|
|-|-|
|夏天2冬天| summer2winter_yosemite|

![](https://junyanz.github.io/CycleGAN/images/season.jpg)


### 物体转换 Object Transfiguration

|任务名称|task_name|
|-|-|
|马2斑马| horse2zebra|
|苹果2橘子| apple2orange|

![](https://junyanz.github.io/CycleGAN/images/objects.jpg)

### 其它 other

|任务名称|task_name|
|-|-|
|类标2街景图| cityscapes|
|类标2建筑物立面图| facades|
|地图2航拍图| maps|



