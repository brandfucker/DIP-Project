# DM2F-Net

由邓子俊、朱磊、胡晓伟、傅志文、徐雪苗、张庆、秦静和彭安恒共同编写。

这个代码库是“[单图像去雾的深度多模型融合](https://openaccess.thecvf.com/content_ICCV_2019/papers/Deng_Deep_Multi-Model_Fusion_for_Single-Image_Dehazing_ICCV_2019_paper.pdf)”（ICCV 2019）的实现，由华南理工大学的邓子俊编写。

## 结果

本人实验的部分测试图片去雾结果见百度网盘。

## 环境配置

基于`Python>=3.7`

1. 创建conda环境

       conda create -n dm2f
       source activate dm2f

2. 安装依赖项（测试过PyTorch 1.8.0）：

   1. 安装pytorch==1.8.0 torchvision==0.9.0（通过conda，推荐）。

   2. 安装其他依赖项

          pip install -r requirements.txt

* 准备数据集

  * 从[官方网页](https://sites.google.com/site/boyilics/website-builder/reside)下载RESIDE数据集。

  * 从[官方网页](https://data.vision.ee.ethz.ch/cvl/ntire18//o-haze/)下载O-Haze数据集。O-Haze的格式似乎有修改，

  * 创建一个目录`./data`并为未压缩的数据创建一个软链接，例如`./data/RESIDE`。

## 训练

2. 在tools/config.py中设置数据集路径
3. 运行`python train.py`

*训练的超参数*设置在*train.py*的顶部，你可以方便地根据需要更改它们。

在单个~~GTX 1080Ti~~ ~~TITAN RTX~~ RTX 3090 GPU上训练一个模型大约需要2小时。

## 测试

1. 在tools/config.py中设置五个基准数据集的路径。
2. 将训练好的模型放入`./ckpt/`。
3. 运行`python test.py`

*测试的设置*设置在`test.py`的顶部，你可以方便地根据需要更改它们。

## 许可

DM2F-Net在[MIT许可](LICENSE)下发布。

