# mnist_fashion
从官网下载训练集和测试集[fashionmnist](https://www.kaggle.com/datasets/zalando-research/fashionmnist)
将fashion-mnist_test.csv和fashion-mnist_train.csv保存在input文件夹下，并新建model文件夹用于保存模型
## 训练部分
先根据大家电脑配置新建虚拟环境，python对应版本为3.10，具体方法google
启动虚拟环境，然后在虚拟环境下安装要用的包
先看pip 和python是否指向虚拟环境
```
which pip
which python
```
输出类似这个：
```
(py3.10) (base) jingqi_mei@PC:~/PPIP$ which pip
/home/jingqi_mei/anaconda3/envs/py3.10/bin/pip
(py3.10) (base) jingqi_mei@PC:~/PPIP$ which python
/home/jingqi_mei/anaconda3/envs/py3.10/bin/python
```
然后安装python包
```
pip install torch
pip install pandas
pip install numpy
pip install matplotlib
```
接下来安装jupyter和ipykernel，并将刚刚建的虚拟环境设为jupyter内核，具体方法google
这样就能在自己电脑上运行fashionmnist.ipynb了
## 测试部分
板子配置信息：
```
armv7l 32bit ubuntu22.04 
```
root下的终端里python和pip指向pynq_venv里的python3.10  
如果用vscode的ssh，需要选择jupyter内核时，就选择上述的python environment  
官方系统镜像中自带很多库，本次只需要安装torch  
有别于PC，需要用wheel文件来编译[torch cp310 armv7l](https://github.com/maxisoft/pytorch-arm/releases/download/v0.1.0/torch-1.13.0a0+git7c98e70-cp310-cp310-linux_armv7l.whl)
然后运行
```
pip install torch-1.13.0a0+git7c98e70-cp310-cp310-linux_armv7l.whl
```
验证是否安装torch(版本跟自己下载的对应)
```
(py3.10) (base) jingqi_mei@PC:~/PPIP$ python
Python 3.10.16 (main, Dec 11 2024, 16:24:50) [GCC 11.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import torch
>>> print(torch.__version__)
2.6.0+cu118
```
然后就能在PYNQ Z1上运行pynq_torch.ipynb
